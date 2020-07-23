# Air Lab Failure and Anomaly (ALFA) Dataset

![ALFA-Dataset](https://raw.githubusercontent.com/castacks/alfa-dataset/master/alfa.jpg)

The *Air Lab Failure and Anomaly* (*ALFA*) Dataset includes the data collected from tens of autonomous flights for failure detection and anomaly detection research. The data is provided in 4 collections:

***- Processed Data:*** 47 sequences of fully autonomous flight sequences with eight different types of faults happening during the flights. The files include the ground truth of the type and the time of the failure and are provided in the ROS **.bag** format, as well as in **.csv** and **.mat** formats. The original **.bag** files are recorded using the modified [mavros](http://wiki.ros.org/mavros) ROS package connected to the Pixhawk running the modified Ardupilot 3.9.0beta1 through [MAVLink 2.0](https://mavlink.io/en/) protocol. 

***- Raw Bag Files:*** The raw .bag files of the flights. It contains both the manual and autonomous flight sequences collected during the flights, without any processing. These files are recorded using the modified [mavros](http://wiki.ros.org/mavros) ROS package connected to the Pixhawk running the modified Ardupilot 3.9.0beta1 through [MAVLink](https://mavlink.io/en/) protocol.  

***- Telemetry Logs:*** The telemetry logs from the onboard NVidia TX2 computer connected to the Pixhawk autopilot.  

***- Dataflash Logs:*** The logs recorded on the Pixhawk during the flights. A supplemental code is provided for working with the dataset in C++, Python and MATLAB. The codes are written independent of ROS or any other external library and are cross-platform (tested in Linux, Mac OS and Windows). The dataset was collected during our research on a novel real-time anomaly detection method for autonomous aerial vehicles. More information about the project is available on the project page [(link)](http://theairlab.org/fault-detection/).

**<span style="color: #800000;">Please refer to the *Download* section below to download the dataset and the code.</span>**

Two publications provide the description of the dataset (including the structure, data collection, etc.). Please proceed to the citation section for more details. 

### Processed Sequences

The main focus of ALFA dataset is the processed data sequences. The list of the sequences is as followed: 

<div class="datatable-begin"></div>
<style>
	th { font-size: 13px; }
	td { font-size: 13px; }
</style>

\# | Sequence Name <span style="color: red;">*</span> | Failed Surface | Type of Failure | Emergency Reaction? <span style="color: red;">**</span> | Flight Time Pre-Failure (s) | Flight Time Post-Failure (s) | Total Time (s)
- | ------------------------------------------------------ | --- | --------------- | -- | --- | --- | -----
1 | 2018-07-18-12-10-11 <span style="color: red;">†</span> | N/A | Full Power Loss | No | N/A | N/A | 205.5
2 | 2018-07-18-15-53-31_1 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 116.3 | 16 | 132.3
3 | 2018-07-18-15-53-31_2 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 73.4 | 15.3 | 88.7
4 | 2018-07-18-16-22-01 | Engine | Full Power Loss | Yes | 116.6 | 15.9 | 132.5
5 | 2018-07-18-16-37-39_1 <span style="color: red;">†</span> | No Failure | - | No | 30.3 | 0 | 30.3
6 | 2018-07-18-16-37-39_2 | Engine | Full Power Loss | Yes | 114.2 | 16.3 | 130.5
7 | 2018-07-30-16-29-45 | Engine | Full Power Loss | Yes | 123.1 | 19.2 | 142.3
8 | 2018-07-30-16-39-00_1 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 116.7 | 14.9 | 131.6
9 | 2018-07-30-16-39-00_2 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 91.6 | 14.6 | 106.2
10 | 2018-07-30-16-39-00_3 <span style="color: red;">†</span> | No Failure | - | No | 79.1 | 0 | 79.1
11 | 2018-07-30-17-10-45 | Engine | Full Power Loss | Yes | 117.2 | 15.9 | 133.1
12 | 2018-07-30-17-20-01 | Engine | Full Power Loss | Yes | 87.7 | 19 | 106.7
13 | 2018-07-30-17-36-35 | Engine | Full Power Loss | Yes | 133.4 | 23.6 | 157
14 | 2018-07-30-17-46-31 | Engine | Full Power Loss | Yes | 90.3 | 22.4 | 112.7
15 | 2018-09-11-11-56-30 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 103.6 | 20.8 | 124.4
16 | 2018-09-11-14-16-55 <span style="color: red;">†</span> | No Failure | - | No | 33.5 | 0 | 33.5
17 | 2018-09-11-14-22-07_1 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 104.8 | 9.4 | 114.2
18 | 2018-09-11-14-22-07_2 <span style="color: red;">†</span> | Engine | Full Power Loss | No | 49.9 | 12.5 | 62.4
19 | 2018-09-11-14-41-38 <span style="color: red;">†</span> | No Failure | - | No | 43.3 | 0 | 43.3
20 | 2018-09-11-14-41-51 <span style="color: red;">†</span> | Elevator | Stuck at zero | No | 117.8 | 10.7 | 128.5
21 | 2018-09-11-14-52-54 <span style="color: red;">†</span> | Aileron | Left stuck at zero, then only right stuck at zero | No | 105.2 | 128.2 | 233.4
22 | 2018-09-11-15-05-11_1 <span style="color: red;">†</span> | Elevator | Stuck at zero | No | 63.4 | 12.8 | 76.2
23 | 2018-09-11-15-05-11_2 <span style="color: red;">†</span> | No Failure | - | No | 67.4 | 0 | 67.4
24 | 2018-09-11-15-06-34_1 <span style="color: red;">†</span> | Rudder | Stuck to the right | No | 55.5 | 14.8 | 70.3
25 | 2018-09-11-15-06-34_2 <span style="color: red;">†</span> | Rudder | Stuck to the right | No | 51.9 | 17.3 | 69.2
26 | 2018-09-11-15-06-34_3 <span style="color: red;">†</span> | Rudder | Stuck to the left | No | 60.1 | 9.3 | 69.4
27 | 2018-09-11-17-27-13_1 <span style="color: red;">†</span> | Rudder & Aileron | Left Aileron and Rudder stuck at zero | No | 116.3 | 27.2 | 143.5
28 | 2018-09-11-17-27-13_2 <span style="color: red;">†</span> | Aileron | Both stuck at zero | No | 65.8 | 35.9 | 101.7
29 | 2018-09-11-17-55-30_1 <span style="color: red;">†</span> | Aileron | Right stuck at zero | No | 111.9 | 21.3 | 133.2
30 | 2018-09-11-17-55-30_2 <span style="color: red;">†</span> | Aileron | Left stuck at zero | No | 50 | 31.4 | 81.4
31 | 2018-10-05-14-34-20_1 | No Failure | - | No | 66.8 | 0 | 66.8
32 | 2018-10-05-14-34-20_2 | Aileron | Right stuck at zero | Yes | 152.2 | 10 | 162.2
33 | 2018-10-05-14-37-22_1 | No Failure | - | No | 72.7 | 0 | 72.7
34 | 2018-10-05-14-37-22_2 | Aileron | Right stuck at zero | No | 73.4 | 71.5 | 144.9
35 | 2018-10-05-14-37-22_3 | Aileron | Left stuck at zero | No | 72.4 | 24 | 96.4
36 | 2018-10-05-15-52-12_1 | No Failure | - | No | 89.7 | 0 | 89.7
37 | 2018-10-05-15-52-12_2 | No Failure | - | No | 48.5 | 0 | 48.5
38 | 2018-10-05-15-52-12_3 | Engine | Full Power Loss | Yes | 49.1 | 17.5 | 66.6
39 | 2018-10-05-15-55-10 | Engine | Full Power Loss | Yes | 100.1 | 13.1 | 113.2
40 | 2018-10-05-16-04-46 | Engine | Full Power Loss | Yes | 76.2 | 16.1 | 92.3
41 | 2018-10-18-11-03-57 | Engine | Full Power Loss | Yes | 104.2 | 12.2 | 116.4
42 | 2018-10-18-11-04-00 | Engine | Full Power Loss | Yes | 111.1 | 11.4 | 122.5
43 | 2018-10-18-11-04-08_1 | Engine | Full Power Loss | Yes | 100.3 | 14.4 | 114.7
44 | 2018-10-18-11-04-08_2 | Engine | Full Power Loss | Yes | 98.2 | 19.7 | 117.9
45 | 2018-10-18-11-04-35 | Engine | Full Power Loss | Yes | 101.3 | 8 | 109.3
46 | 2018-10-18-11-06-06 | Engine | Full Power Loss | Yes | 102.5 | 14 | 116.5
47 | 2018-10-18-11-08-24 | No Failure | - | No | 26.4 | 0 | 26.4

<div class="datatable-end"></div> 

<span style="color: red;">*</span> The complete sequence name also includes *'carbonZ_' *at the beginning of the name in the table and the type of the failure at the end. Please refer to the dataset files for the complete names. 

<span style="color: red;">**</span> Some sequences include an emergency trajectory activated (a new trajectory replaces the previous one) as soon as the failure happens. 

<span style="color: red;">†</span> These sequences are published with the ICRA 2019 paper. Please cite the paper if you use them for research purposes. 

### Publications

The tools and the dataset are provided with a publication ([PDF available on arXiv](https://arxiv.org/abs/1907.06268)). Please use the following citation if you use either the tools or the dataset: 

*BibTeX:* 

```
@article{keipour:dataset:2019,
author={Azarakhsh Keipour and Mohammadreza Mousaei and Sebastian Scherer},
title={ALFA: A Dataset for UAV Fault and Anomaly Detection},
journal = {The International Journal of Robotics Research},
volume = {},
number = {},
pages = {},
year = {In press},
}
```

*IEEE Style:* 

```
A. Keipour, M. Mousaei, and S. Scherer, “ALFA: A dataset for UAV fault and anomaly detection,” The International Journal of Robotics Research, In press. 
```

<br/>

The sequences marked with <span style="color: red;">†</span> are released with another publication ([PDF available on arXiv](https://arxiv.org/abs/1907.00511) and [IEEE Xplore](https://ieeexplore.ieee.org/document/8794286)). If you use any of those sequences, please use the following citation: 

*BibTeX:* 

```
@inproceedings{keipour:detection:2019,
author={Azarakhsh Keipour and Mohammadreza Mousaei and Sebastian Scherer},
booktitle={2019 IEEE International Conference on Robotics and Automation (ICRA)},
title={Automatic Real-time Anomaly Detection for Autonomous Aerial Vehicles},
year={2019},
month={May},
pages={5679-5685},
doi={10.1109/ICRA.2019.8794286},
}
```

*IEEE Style:* 

```
A. Keipour, M. Mousaei, and S. Scherer, “Automatic Real-time Anomaly Detection for Autonomous Aerial Vehicles,” in 2019 IEEE International Conference on Robotics and Automation (ICRA), May 2019, pp.5679-5685. doi: 10.1109/ICRA.2019.8794286. 
```

Please contact us if you encounter issues or to ask additional questions. 

### Download

You can download the whole or a portion of the ALFA dataset from [here](https://cmu.box.com/s/u7vne29uiips4n5p1dl2k514s3j3ozby). The size of the complete dataset for download is **1.7 GB** (12.5 GB unzipped). Please check the Version History file inside the dataset to see if there are any changes since the last time you have downloaded the dataset. 

The supplemental code and the documentation are available at the following link: 

[https://github.com/castacks/alfa-dataset-tools](https://github.com/castacks/alfa-dataset-tools) 

In addition, the source code of an online fault detection method using this dataset can be accessed from [this page](http://theairlab.org/fault-detection/).

To access the publications please refer to the *Publications* section above or contact us. 

### Contact

Azarakhsh Keipour - (keipour [at] cmu [dot] edu) 

Mohammadreza Mousaei - (mmousaei [at] cmu [dot] edu) 

Sebastian Scherer - (basti [at] cmu [dot] edu)

### Acknowledgments 

This work was supported through NASA Grant Number NNX17CL06C.

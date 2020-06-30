# Benchmarks

This repository intoduces five  graph diagrams of real-life applications and profile information for each task.

| Applications|Priority |Number of Tasks|Run Type|Period(ms)|
|----------------|--|--|-------|------|
|LaneDetection|5|14|Time-driven|200|
|ResNet|4|28|Time-driven|500|
|KmeansClustering|3| 17|Time-driven|33|
|H264Decoder|2|5|Event-driven|500|
|CrpytoGraph|1|4|Best-effort|-|

The **LaneDetection** application detects the lane from an input image with a set of filters.

The **ResNet**  application is an image classification application, known as ResNet-152.

The **KmeansClustering** application performs K-means clustering algorithm. It contains a parallelizable task that can be mapped onto multiple processors, except GPU.

The **H264Decoder** application is a multi-mode SDF model that has two modes of operation for video decoding.

The **CrpytoGraphy** application is a cryptography algorithm based on RSA. The last three applications can be run only on CPU cores.

# Description

The black line in the graph diagram represents the edge and the red line represents the feedback edge.

The yellow block represents a general task, the blue block represents a set of tasks that can be run in parallel, and the orange block represents a set of tasks that runs iteratively.

The task execution time is profiled from Jetson TX2 that has two Denver CPUs, four ARM A57 CPUs, and one NVIDIA Pascal GPU. The minimum, average, and maximum values were obtained by running the task more than 100 times on the mappable core. In case the execution time varies too much, the maximum values are set 75\% of the profiled maximum to make all applications schedulable on Jetson TX2.

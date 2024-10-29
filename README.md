## Datasets for multi-robot pose graph merging

The g2o dataset, widely recognized in the SLAM community, provides a comprehensive set of benchmark data for graph-based optimization in SLAM. 

In single-robot SLAM, the g2o dataset is often used as a benchmark test to evaluate the performance of graph optimization algorithms[1]. The folder "single-robot 3D pose graph" provides single-robot pose datasets for three scenarios: grid3D, sphere2500, and torus3D.

![image](https://github.com/some66/UECP/blob/master/pose%20merging.png)

In multi-robot CSLAM, the g2o datasets can be used to validate collaborative pose estimation among different robots. We split the single-robot dataset into two-robot and three-robot scenarios, which include odometry and intra-robot loop closures. The split datasets are stored in the "split_pose_graph" folder. Then, the SE-Sync algorithm [2] is used to solve and obtain the optimized trajectory for each robot, with the optimized results saved in the "multi_robot_optimization" folder. Finally, based on the optimized poses of each robot (from the "multi_robot_optimization" folder) and the inter-robot loop closures (from the "inter-robot loop-closure" folder), the proposed pose merging algorithm is applied to obtain the final results. The overall process is shown in the figure above. The dataset "sphere2500" is split, optimized, and aligned, resulting in the merged pose graph.

[1] R. Kummerle, G. Grisetti, H. Strasdat, et al, "g2o: A general framework for graph optimization," IEEE Intl. Conf. on Robotics and Automation (ICRA), Shanghai, China, 2011, pp. 3607-3613.

[2] D. M. Rosen, L. Carlone, A. S. Bandeira, et al, "SE-Sync: A certifiably correct algorithm for synchronization over the special Euclidean group," Intl. J. of Robotics Research, vol. 38, no. 2, pp. 95-125, 2019.


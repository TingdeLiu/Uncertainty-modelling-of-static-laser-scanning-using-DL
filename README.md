# Uncertainty modelling of static laser scanning using DL
It's a project I finished at Leibniz University. Below is my proposed RePN architecture for modeling the uncertainty given to LIDAR. I use the idea of Pointnet to extract features from the point cloud, and then input the extracted features combined with some physically acquired features into MPL for regression prediction.
![image](https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL/assets/117039110/bdabb067-2ca9-4a4a-8bfb-c1afb44d165e)
The structure below shows that the architecture performs very well. It is far more effective than XGBoost.
![image](https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL/assets/117039110/8b33bc80-1663-42bb-b45d-7ababfe5ba47)
![image](https://github.com/TingdeLiu/Uncertainty-modelling-of-static-laser-scanning-using-DL/assets/117039110/dc81c2ac-3dfd-4c7d-a543-18cd5680a320)

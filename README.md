# robust-seed-classification
This project examines the robustness of deep learning models under domain shift.

A ResNet-18 classifier was trained for seed quality classification and evaluated under pose, scale, and lighting variations. Grad-CAM visualisation revealed reliance on spurious visual shortcuts rather than meaningful morphological features.

To address this issue, a Morphological and Photometric Decoupling augmentation pipeline was developed, resulting in substantial improvements in out-of-distribution performance while maintaining in-domain accuracy.

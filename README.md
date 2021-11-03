# Multi-Task-Deep-Learning
**A list of papers, codes and applications on multi-task deep learning. Comments and contributions are welcomed!**

And it's updating...

------
## Table of Contents:
- [Papers](#papers) 
  - [Survey](#survey)
  - [Theory](#theory)
  - [Architecture design](#archi)
  - [Task relationship learning](#trl)
  - [Optimization methods](#optim)
    - [Loss function](#loss)
    - [Optimization](#optimization)
  - [Novel Settings](#novel)
- [Datasets](#datasets)
- [Applications](#apps)
- [Related Areas](#related)
- [Trends](#trends)

<a name="papers"></a>

## Papers

<a name="survey"></a>
### Survey

- [1997] Caruana, R. Multitask Learning. *Machine Learning* **28,** 41–75 (1997). https://doi.org/10.1023/A:1007379606734.
- http://www.siam.org/meetings/sdm12/zhou_chen_ye.pdf Multi-Task Learning: Theory, Algorithms, and Applications (2012, SDM tutorial)
- A Survey on Multi-Task Learning. *arXiv*, jul 2017.
- An Overview of Multi-Task Learning in Deep Neural Networks. *arXiv*, jun 2017.
- A brief review on multi-task learning. *Multimedia Tools and Applications*, 77(22):29705–29725, nov 2018.
- Multi-task learning for dense prediction tasks: A survey. *arXiv*, apr 2020.
- A Brief Review of Deep Multi-task Learning and Auxiliary Task Learning. arXiv, jul 2020.
- Multi-task learning with deep neural networks: A survey, 2020.

<a name="theory"></a>

### Theory

- [NeurIPS 2018] Multi-task learning as multi-objective optimization. In *Advances in Neural Information Processing Systems*, pages 527–538, 2018.
- [2019] How to study the neural mechanisms of multiple tasks, [paper](https://www.sciencedirect.com/science/article/pii/S2352154619300695)
- [ICLR 2021] Deciphering and Optimizing Multi-Task Learning: a Random Matrix Approach, https://openreview.net/forum?id=Cri3xz59ga
- [ICML 2021] Bridging Multi-Task Learning and Meta-Learning: Towards Efficient Training and Effective Adaptation, [paper](https://arxiv.org/abs/2106.09017), [code](https://github.com/AI-secure/multi-task-learning)
- [bioRxiv 2021] Abstract representations emerge naturally in neural networks trained to perform multiple tasks, [paper](https://www.biorxiv.org/content/10.1101/2021.10.20.465187v1)

<a name="archi"></a>

### Architecture design

##### pure hard parameter sharing

- MultiNet: Real-time Joint Semantic Reasoning for Autonomous Driving. In *IEEE Intelligent Vehicles Symposium, Proceedings*, 2018.
- Multi-task Learning Using Uncertainty to Weigh Losses for Scene Geometry and Semantics. *Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition*, pages 7482–7491, 2018.
- UberNet: Training a universal convolutional neural network for Low-, Mid-, and high-level vision using diverse datasets and limited memory. *Proceedings - 30th IEEE Conference on Computer Vision and Pattern Recognition, CVPR 2017*, 2017-January:5454–5463, 2017.
- Modeling task relationships in multi-task learning with multi-gate mixture-of-experts. In *Proceedings of the 24th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining*, KDD ’18, page 1930–1939, New York, NY, USA, 2018. Association for Computing Machinery.
- [CVPR 2018] PackNet: Adding Multiple Tasks to a Single Network by Iterative Pruning, [Paper](https://arxiv.org/abs/1711.05769), [Code](https://github.com/arunmallya/packnet)
- [ECCV 2018] Piggyback: Adapting a Single Network to Multiple Tasks by Learning to Mask Weights, [Paper](https://arxiv.org/abs/1801.06519v2), [Code](https://github.com/arunmallya/piggyback)
  - learn to mask weights of an existing network
- [CCN 2019] Modulation of early visual processing alleviates capacity limits in solving multiple tasks, [Paper](https://arxiv.org/abs/1907.12309)
  - By associating neural modulations with task-based switching of the state of the network and characterizing when such switching is helpful in early processing, our results provide a functional perspective towards understanding why task-based modulation of early neural processes might be observed in the primate visual cortex.
- [CVPR 2019] Attentive Single-Tasking of Multiple Tasks, [paper](https://arxiv.org/abs/1904.08918), [code](http://vision.ee.ethz.ch/~kmaninis/astmt/)
  - We refine features with a task-specific residual adapter branch (RA) and attend to particular channels with task-specific Squeeze-and-Excitation (SE) modulation.
  - We also **enforce the task gradients to be statistically indistinguishable through adversarial training**.
- [AAAI 2020] Learning Sparse Sharing Architectures for Multiple Tasks, [paper](https://arxiv.org/abs/1911.05034)
- [ICML 2020] Learning to Branch for Multi-Task Learning, http://proceedings.mlr.press/v119/guo20e.html.
- [arXiv 2021] UniT: Multimodal Multitask Learning with a Unified Transformer, https://arxiv.org/abs/2102.10772, [Code](https://mmf.sh/)
- [arXiv 2021] You Only Learn One Representation: Unified Network for Multiple Tasks, [paper](https://arxiv.org/abs/2105.04206), [Code](https://github.com/WongKinYiu/yolor)
- [CVPR 2021] CompositeTasking: Understanding Images by Spatial Composition of Tasks, [paper](https://arxiv.org/abs/2012.09030), [Code](https://github.com/nikola3794/composite-tasking): One network for multiple tasks, but requires multiple inferences.
- [ICCV 2021] Multi-Task Self-Training for Learning General Representations, [paper](https://arxiv.org/abs/2108.11353)
  - Multi-task self-training with pseudo labels (generated by multiple single-task teachers)
  - Cross training on multiple vision datasets

##### pure soft parameter sharing

- Cross-Stitch Networks for Multi-task Learning. In *Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition*, 2016.
- Deep Multi-task Representation Learning: A Tensor Factorisation Approach. *5th International Conference on Learning Representations, ICLR 2017 - Conference Track Proceedings*, may 2016. [Code](https://github.com/wOOL/DMTRL)
- Latent multi-task architecture learning. In *33rd AAAI Conference on Artificial Intelligence, AAAI 2019, 31st Innovative Applications of Artificial Intelligence Conference, IAAI 2019 and the 9th AAAI Symposium on Educational Advances in Artificial Intelligence, EAAI 2019*, 2019. [Code](https://github.com/sebastianruder/sluice-networks)
- NDDR-CNN: Layerwise Feature Fusing in Multi-Task CNNs by Neural Discriminative Dimensionality Reduction. In *2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, pages 3200–3209. IEEE, jun 2019. [Code](https://github.com/ethanygao/NDDR-CNN)

##### a mix of hard and soft

- End-to-end multi-task learning with attention. *Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition*, 2019-June:1871–1880, 2019. [Code](https://github.com/lorenmt/mtan)
- Pad-net: Multi-tasks guided prediction-and-distillation network for simultaneous depth estimation and scene parsing. In *2018 IEEE/CVF Conference on Computer Vision and Pattern Recognition*, pages 675–684, 2018.
- Pattern-affinitive propagation across depth, surface normal and semantic segmentation. In *2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, pages 4101–4110, 2019.
- Mti-net: Multi-scale task interaction networks for multi-task learning. In *ECCV*, 2020. [Code](https://github.com/SimonVandenhende/Multi-Task-Learning-PyTorch)
- Attentive Single-Tasking of Multiple Tasks. In *2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, pages 1851–1860. IEEE, jun 2019. [Code](https://github.com/facebookresearch/astmt)
- [NeurIPS 2020] Adashare: Learning what to share for efficient deep multi-task learning. *ArXiv*, abs/1911.12423, 2020. [Code](https://github.com/sunxm2357/AdaShare)
- Mtl-nas: Task-agnostic neural architecture search towards general-purpose multi-task learning. In *IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*, 2020. [Code](https://github.com/bhpfelix/MTLNAS)
- Many Task Learning With Task Routing. In*2019IEEE/CVF International Conference on Computer Vision (ICCV)*, pages 1375–1384. IEEE, oct 2019.

<a name="trl"></a>
### Task relationship learning

- [CVPR 2018] Taskonomy: Disentangling Task Transfer Learning. 
- [CVPR 2017] Fully-Adaptive Feature Sharing in Multi-Task Networks with Applications in Person Attribute Classification.
- [arXiv 2020] Branched multi-task networks: Deciding what layers to share.
- [arXiv 2020] Automated Search for Resource-Efficient Branched Multi-Task Networks.
- [arXiv 2020] Learning to Branch for Multi-Task Learning. 
- [arXiv 2020] Measuring and harnessing transference in multi-task learning, [paper](https://arxiv.org/abs/2010.15413v3)
- [ICML 2020] Which Tasks Should Be Learned Together in Multi-task Learning?, http://proceedings.mlr.press/v119/standley20a.html, [Code](https://github.com/tstandley/taskgrouping)
- [ICLR 2021] AUXILIARY TASK UPDATE DECOMPOSITION: THE GOOD, THE BAD AND THE NEUTRAL, https://openreview.net/forum?id=1GTma8HwlYp
  - decompose auxiliary updates into directions which help, damage or leave the primary task loss unchanged
- [NeurIPS 2021] Efficiently Identifying Task Groupings for Multi-Task Learning, [paper](https://arxiv.org/abs/2109.04617)
  - Our method determines task groupings in a single run by training all tasks together and quantifying the effect to which one task's gradient would affect another task's loss.
  - based on the idea and concepts in *Measuring and harnessing transference in multi-task learning*.

<a name="optim"></a>

### Optimization Methods

<a name="loss"></a>

#### Loss function

- Multi-task Learning Using Uncertainty to Weigh Losses for Scene Geometry and Semantics. *Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition*, pages 7482–7491, 2018.
- Auxiliary Tasks in Multi-task Learning. *arXiv*, may 2018.
- GradNorm: Gradient normalization for adaptive loss balancing in deep multitask networks. *35th International Conference on Machine Learning, ICML 2018*, 2:1240–1251, 2018.
- Self-paced multi-task learning. *AAAI Conference on Artificial Intelligence*, pages 2175–2181, 2017.
- Dynamic task prioritization for multitask learning. ECCV 2018 - 15th European Conference, Munich, Germany, September 8-14, 2018.
- Focal Loss for Dense Object Detection. In *Proceedings of the IEEE International Conference on Computer Vision*, 2017.
- End-to-end multi-task learning with attention. *Proceedings of the IEEE Computer Society Conference on Computer Vision and Pattern Recognition*, 2019-June:1871–1880, 2019. [Code](https://github.com/lorenmt/mtan)
- MultiNet++: Multi-Stream Feature Aggregation and Geometric Loss Strategy for Multi-Task Learning. In *2019 IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)*, volume 2019-June, pages 1200–1210. IEEE, jun 2019.
- Dynamic Task Weighting Methods for Multi-task Networks in Autonomous Driving Systems. In *2020 IEEE 23rd International Conference on Intelligent Transportation Systems (ITSC)*, pages 1–8. IEEE, sep 2020.
- A Comparison of Loss Weighting Strategies for Multi task Learning in Deep Neural Networks. *IEEE Access*, 7:141627–141632, 2019.
- [ICRA 2021] OmniDet Surround View Cameras Based Multi-Task Visual Perception Network for Autonomous Driving, [paper](https://arxiv.org/abs/2102.07448)
- [CVPR 2021] Taskology: Utilizing Task Relations at Scale, [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Lu_Taskology_Utilizing_Task_Relations_at_Scale_CVPR_2021_paper.html)

<a name="optimization"></a>

#### Optimization

- [Neurips 2018] Multi-task learning as multi-objective optimization. 
- [Neurips 2019] Pareto multi-task learning. [Code](https://github.com/xi-l/paretomtl)
- [ICML 2020] Efficient continuous pareto exploration in multi-task learning. [Code](https://github.com/mit-gfx/ContinuousParetoMTL)
- [arXiv 2020] Gradient Surgery for Multi-Task Learning. [Code](https://github.com/tianheyu927/PCGrad)
- [ICML 2018] Deep asymmetric multi-task feature learning.
- [ICML 2020] Multi-Task Learning with User Preferences: Gradient Descent with Controlled Ascent in Pareto Optimization, http://proceedings.mlr.press/v119/mahapatra20a.html, [Code](https://github.com/dbmptr/EPOSearch)
- [ICML 2020] Efficient Continuous Pareto Exploration in Multi-Task Learning, http://proceedings.mlr.press/v119/ma20a.html, [Code](https://github.com/mit-gfx/ContinuousParetoMTL)
- [ICML 2020] Adaptive Adversarial Multi-task Representation Learning, http://proceedings.mlr.press/v119/mao20a.html
- [2020] Task uncertainty loss reduce negative transfer in asymmetric multi-task feature learning.
- [AISTATS 2021] High-Dimensional Multi-Task Averaging and Application to Kernel Mean Embedding, http://proceedings.mlr.press/v130/marienwald21a.html
- [ICLR 2021] Gradient Vaccine: Investigating and Improving Multi-task Optimization in Massively Multilingual Models, [paper](https://openreview.net/forum?id=F1vEjWK-lH_)
- [ICLR 2021] Towards Impartial Multi-task Learning, https://openreview.net/forum?id=IMPnRXEWpvr

<a name='novel'></a>

### Novel Settings

- [CVPR 2019] Deep Virtual Networks for Memory Efficient Inference of Multiple Tasks, [paper](https://ieeexplore.ieee.org/document/8954328/)
- [ICML 2020] Task Understanding from Confusing Multi-task Data, http://proceedings.mlr.press/v119/su20b.html
- [ECCV 2020] Multitask Learning Strengthens Adversarial Robustness, [paper](https://arxiv.org/abs/2007.07236v2), [Code](https://github.com/columbia/MTRobust)
- [ICLR 2021] The Traveling Observer Model: Multi-task Learning Through Spatial Variable Embeddings, https://openreview.net/forum?id=qYda4oLEc1
  - a machine learning framework in which seemingly unrelated tasks can be solved by a single model, by embedding their input and output variables into a shared space. 

Also I need to mention that many MTL approaches utilize not just one category of methods listed above but a combination instead. 

<a name="datasets"></a>

## Datasets

Commonly used in computer vision:

-  [Taskonomy](http://taskonomy.vision/) is currently the largest dataset specifically designed for multi-task learning. It has about 4.5 million images of indoor scenes from 3D scans of about 600 buildings and every image has an annotation for all 26 tasks.
-  [NYU v2](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html) is a large-scale dataset for indoor scenes understanding, which contains a variety of computer vision tasks. There are in total 1449 densely labeled RGBD images, capturing 464 diverse indoor scenes, with 35,064 distinct objects from 894 different classes.
- MultiMNIST is an MTL version of the [MNIST](http://yann.lecun.com/exdb/mnist/) dataset. It is formed by overlaying multiple handwrit- ten digit images together. One of these is placed at the top-left while the other at the bottom-right. The tasks are classifying simultaneously the digit on the top-left and on the bottom-right.
- [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset contains 10,000 identities, each has 20 images, which result a total number of 200,000 images. Since CelebA is annotated with 40 face attributes and 5 key points, it can be used in MTL setting by considering each attribute as a distinct classification task.
- [Cityscapes](https://www.cityscapes-dataset.com/) dataset is established for semantic urban scene understanding. It is comprised of 5000 images with high quality pixel-level annotations as well as 20,000 additional images with coarse annotations. Tasks like semantic segmentation, instance segmentation and depth estimation are able to be trained together on Cityscapes.
- [MS-COCO](http://mscoco.org/) is a widely used dataset in CV. It contains 382k images with a total of 2.5 million labeled instances spanning 91 objects types. It can be used for multiple tasks including image classification, detection and segmentation.
- [KITTI](www.cvlibs.net/datasets/kitti) is by far the most famous and commonly used dataset for autonomous driving. It provides benchmarks for multiple driving tasks: e.g. stereo matching, optical flow estimation, visual odometry/SLAM, semantic segmentation, object detection/orientation estimation and object tracking.
- [BDD100K](https://bdd-data.berkeley.edu/) is a recent driving dataset designed for heterogeneous multitask learning. It is comprised of 100K video clips and 10 tasks: image tagging, lane detection, drivable area segmentation, road object detection, semantic segmentation, instance segmentation, multi-object detection tracking, multi-object segmentation tracking, domain adaptation and imitation learning.
- [TransNAS-Bench-101](https://download.mindspore.cn/dataset/TransNAS-Bench-101): CVPR 2021, Improving Transferability and Generalizability of Cross-Task Neural Architecture Search. [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Duan_TransNAS-Bench-101_Improving_Transferability_and_Generalizability_of_Cross-Task_Neural_Architecture_Search_CVPR_2021_paper.html).
- [Omnidata](https://omnidata.vision/): ICCV 2021. Generating multi-task mid-level vision datasets from 3D Scans. [paper](https://arxiv.org/abs/2110.04994). 

<a name="apps"></a>
## Applications

#### Natural language processing

- [ICML 2008] A unified architecture for natural language processing: deep neural networks with multitask learning, https://dl.acm.org/doi/10.1145/1390156.1390177

- [ICLR 2021] Conditionally Adaptive Multi-Task Learning: Improving Transfer Learning in NLP Using Fewer Parameters & Less Data, https://openreview.net/pdf?id=de11dbHzAMF, [Code](https://github.com/CAMTL/CA-MTL)
- [ICLR 2021] HyperGrid Transformers: Towards A Single Model for Multiple Tasks, https://openreview.net/forum?id=hiq1rHO8pNT
- [ICML 2020] XTREME: A Massively Multilingual Multi-task Benchmark for Evaluating Cross-lingual Generalisation, http://proceedings.mlr.press/v119/hu20b.html, [Code](https://github.com/google-research/xtreme)

#### Speech processing

#### Computer vision

##### Medical Imaging

- [MIDL 2020] Extending Unsupervised Neural Image Compression With Supervised Multitask Learning, http://proceedings.mlr.press/v121/tellez20a.html

##### Autonomous Driving

- [ICML 2019] Multi-task learning in the wildness. https://slideslive.com/38917690/multitask-learning-in-the-wilderness
- [arXiv 2020] Efficient Latent Representations using Multiple Tasks for Autonomous Driving, [paper](https://arxiv.org/abs/2003.00695)
- [arXiv 2021] MonoGRNet: A General Framework for Monocular 3D Object Detection, https://arxiv.org/abs/2104.08797
- [CVPR 2021] Multi-task Learning with Attention for End-to-end Autonomous Driving. *ArXiv**, abs/2104.10753*.
- [ICRA 2021] OmniDet Surround View Cameras Based Multi-Task Visual Perception Network for Autonomous Driving, [paper](https://arxiv.org/abs/2102.07448)
- [CVPR 2021] Deep Multi-Task Learning for Joint Localization, Perception, and Prediction. [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Phillips_Deep_Multi-Task_Learning_for_Joint_Localization_Perception_and_Prediction_CVPR_2021_paper.html)

##### Others

- [SIGKDD 2019] Learning a Unified Embedding for Visual Search at Pinterest, [paper](https://arxiv.org/abs/1908.01707v1)
  - For every mini-batch, we **balance a uniform mix of each of the datasets** with an epoch defined by the iterations to iterate through the largest dataset. Each dataset has its own indepedent tasks so we **ignore the gradient contributions of images on tasks that it does not have data for**. The losses from all the tasks are assigned equal weights and are summed for backward propagation.
- [CVPR 2021] When Age-Invariant Face Recognition Meets Face Age Synthesis: A Multi-Task Learning Framework, [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Huang_When_Age-Invariant_Face_Recognition_Meets_Face_Age_Synthesis_A_Multi-Task_CVPR_2021_paper.html), [Code](https://github.com/Hzzone/MTLFace)
- [CVPR 2021] Three Birds with One Stone: Multi-Task Temporal Action Detection via Recycling Temporal Annotations, [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Li_Three_Birds_with_One_Stone_Multi-Task_Temporal_Action_Detection_via_CVPR_2021_paper.html)
- [CVPR 2021] Anomaly Detection in Video via Self-Supervised and Multi-Task Learning, [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Georgescu_Anomaly_Detection_in_Video_via_Self-Supervised_and_Multi-Task_Learning_CVPR_2021_paper.html)

#### Reinforcement learning

- [arXiv 2021] MT-Opt: Continuous Multi-Task Robotic Reinforcement Learning at Scale, https://arxiv.org/abs/2104.08212
- [ICML 2020] CoMic: Complementary Task Learning & Mimicry for Reusable Skills, http://proceedings.mlr.press/v119/hasenclever20a.html
- [AISTATS 2021] On the Effect of Auxiliary Tasks on Representation Dynamics, http://proceedings.mlr.press/v130/lyle21a.html
- [ICML 2021] Multi-Task Reinforcement Learning with Context-based Representations, [paper](https://arxiv.org/abs/2102.06177)

#### Recommendation

- [AISTATS 2021] Decision Making Problems with Funnel Structure: A Multi-Task Learning Approach with Application to Email Marketing Campaigns, http://proceedings.mlr.press/v130/xu21a.html

#### Multi-modal

- [CVPR 2014] https://sites.google.com/site/deeplearningcvpr2014/DL-Multimodal_multitask_learning.pdf Multimodal learning and multitask learning 
- [arXiv 2020] Multimodal Continuous Emotion Recognition using Deep Multi-Task Learning with Correlation Loss, https://arxiv.org/abs/2011.00876

- [arXiv 2021] Towards General Purpose Vision Systems, https://arxiv.org/pdf/2104.00743.pdf
- [arXiv 2021] UniT: Multimodal Multitask Learning with a Unified Transformer, https://arxiv.org/abs/2102.10772, [Code](https://mmf.sh/)

<a name="related"></a>

## Related Areas

- Transfer Learning
  - [CVPR 2021] Can We Characterize Tasks Without Labels or Features? [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Wallace_Can_We_Characterize_Tasks_Without_Labels_or_Features_CVPR_2021_paper.html), [code](https://github.com/BramSW/)
  - [CVPR 2021] OTCE: A Transferability Metric for Cross-Domain Cross-Task Representations, [paper](https://arxiv.org/abs/2103.13843)
- Auxiliary Learning
  - [CVPR 2021] Image Change Captioning by Learning From an Auxiliary Task, [paper](https://openaccess.thecvf.com/content/CVPR2021/html/Hosseinzadeh_Image_Change_Captioning_by_Learning_From_an_Auxiliary_Task_CVPR_2021_paper.html)
- Multi-label Learning
- Multi-modal Learning
- Meta Learning
- Continual Learning
  - [CVPR 2021] KSM: Fast Multiple Task Adaption via Kernel-wise Soft Mask Learning, [paper](https://arxiv.org/abs/2009.05668)
  - [ICLR 2021] Linear Mode Connectivity in Multitask and Continual Learning, https://openreview.net/forum?id=Fmg_fQYUejf, [Code](https://github.com/imirzadeh/MC-SGD)
- Curriculum Learning
- Ensemble, Distillation and Model Fusion

<a name="trends"></a>

# Trends

- [Pathways](https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/): multi-task, multi-modal, sparse activated
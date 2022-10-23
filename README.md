# Cut-in Maneuver Detection with Self-supervised Contrastive Video Representation Learning

## Abstract

The detection of the maneuvers of the surrounding vehicles is important for autonomous vehicles to
act accordingly to avoid possible accidents. This study proposes a framework based on contrastive
representation learning to detect potentially dangerous cut-in maneuvers that can happen in front of
the ego vehicle. First, the encoder network is trained in a self-supervised fashion with contrastive loss
where two augmented videos of the same video clip stay close to each other in the embedding space,
while augmentations from different videos stay far apart. Since no maneuver labeling is required in
this step, a relatively large dataset can be used. After this self-supervised training, the encoder is fine-
tuned with our Berkeley Deep Drive cut-in/lane-pass labeled dataset. Instead of using original video
frames, we simplified the scene by highlighting surrounding vehicles and ego-lane. We have investigated
the use of several classification heads, augmentation types, and scene simplification alternatives. The
most successful model outperforms the fully supervised model by ∼2% with an accuracy of 92.52%.

Proposed method architecture:
![pipeline](https://github.com/ynalcakan/segment-and-predict-maneuver/blob/main/mcrl-overview_1200dpi.png?raw=true)

## Information about the repository:

Proposed pipeline's code is available in "**R3D_18_contrastive_learning_model.py**".

About the data we used:<br/>

We created unlabeled, and labeled datasets from Berkeley Deep Drive Dataset [6]. Originally this dataset consisted of 100K driving videos labeled
for ten tasks (road object detection, instance segmentation, drive-able area, etc.). The videos were collected from the front camera of the vehicles at
various times of the day in New York, Berkeley, San Francisco, and Tel Aviv. For both datasets, we selected videos that happened on highways. 1220
video clips with unknown maneuver information were extracted to be used in the self-supervised learning phase. 875 video clips were cut for the
fine-tuning phase, containing 405 cut-in and 470 lane-pass samples. Unlabeled versions of all 2095 video clips were used in self-supervised learning,
while the labeled 875 video clips were used in the fine-tuning phase.

Note: You can find labeled dataset in this Google Drive ![link](https://drive.google.com/drive/folders/1pk0zUFGD4C_iSvtATWTIlVP7u_3xzn4i) and for the unlabeled dataset you can create an account at Berkeley Deep Drive Dataset portal (https://bdd-data.berkeley.edu/) than randomly download highway labeled videos. 

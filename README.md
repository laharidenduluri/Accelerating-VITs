# Accelerating-VITs



Pruning the Vit's to achieve better performance

The swin model architecture which is generally used in the computer vision tasks ,we use it in the image classification task has higher computational complexity because of its architectural requirements. So we implement the process of pruning which can enable the model to perform better. The pruning methodology mainly involves to first prune the heads , that is done on the multi head attention layers and then the SVD combined with the IHT helps to prune the linear layers of the swin model. We extract the weights from the pretrained Swin model and perform the pruning.We train the model initailly with the datatsets ( 1. cifar10 and 2. Caltech-101) , get the weights, prune the model and then finetune the model by trainiing it again. At last wet test the model and measure its accuracy with the test dataset before and after pruning. The main metrics for the measure of our pruning technique is the flop reeduction, total number of non zero parameters and the model size.

How to execute : 

we are implementing image classification task for the swin vision transformer and calculating the accuracies before and after pruning
for which we start with the execution of the file Cifar_svd_iht4training which is the implementation of the pruning method svd and iht on the dataset cifar( image classification task ) and perform training without first implementing our pruning , later we can see the execution of pruning based implementation
next we implement the cifar_train_prune_test_accuracies file
later we can follow the execution of only_params_cifar and caltech_params_flops_size file .



Steps which can be followed 

- install certain dependencies like thop, timm and other required libraries which have been initially mentioned in each code file
- run the pretrained swin model for image classification  before pruning
- apply the pruning methodology and calculate the metrics
- apply the task again on the pruned swin model and calculate the accuracies and metrics required.

in detail : 
- take pretrained models which can be specifically used for certain tasks, here we selected a swin pretrained model which has been already pretrained on imagenet Dataset, selet a prominent dataset which can do the task, here we selected CIFAR10 and CALTECH101 datset divided into test and train datasets

-apply the model on the specified task and calculate the accuracy ( before pruning accuracy ) and also calculate some measures like total number of flops, model size like nuber of non zero [arameters.

- now do prune heads method to prune the layers of multii head attention and do svd along with iht for the linear layers of the swin transformer model

- the required codes for training , extracting the weights, pruning and again finetuninng, are all specified in the codes.


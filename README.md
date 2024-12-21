# era_v3_assignment_7

## Model-1 execution

## Target:
- Make setup ready
- Make sure, defined model get trained
- Limit the 20 epoch

## Result:
- Parameters: 6.3M (6,379,786)
- Best Training Accuracy: 100.00%
- Best Test Accuracy: 99.39%

## Analysis:
- model containg many parameters
- model is Over fitting (training accuracy: 100% test accuracy: 99.38%)

## Model-1 Summary
```
Requirement already satisfied: torchsummary in /usr/local/lib/python3.10/dist-packages (1.5.1)
cpu
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1           [-1, 32, 28, 28]             320
            Conv2d-2           [-1, 64, 28, 28]          18,496
         MaxPool2d-3           [-1, 64, 14, 14]               0
            Conv2d-4          [-1, 128, 14, 14]          73,856
            Conv2d-5          [-1, 256, 14, 14]         295,168
         MaxPool2d-6            [-1, 256, 7, 7]               0
            Conv2d-7            [-1, 512, 5, 5]       1,180,160
            Conv2d-8           [-1, 1024, 3, 3]       4,719,616
            Conv2d-9             [-1, 10, 1, 1]          92,170
================================================================
Total params: 6,379,786
Trainable params: 6,379,786
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 1.51
Params size (MB): 24.34
Estimated Total Size (MB): 25.85
----------------------------------------------------------------
```

------------------------------------------------------------------------------------

## Model-2 execution

## Target:
- Reduce parameters bellow 20k count
- Make sure, defined model get trained
- Limit the 20 epoch

## Result:
- Parameters: 12,854
- Best Training Accuracy: 99.26%
- Best Test Accuracy: 98.97%%

## Analysis:
- model trained with 12k parameters
- Added Batch Normalization, MaxPool2d and dropout = 0.1
- Model is Over fitting from 14th epoch (training accuracy: 99.10% test accuracy: 98.93%)

## Model-2 Summary
```
Requirement already satisfied: torchsummary in /usr/local/lib/python3.10/dist-packages (1.5.1)
cpu
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1           [-1, 10, 26, 26]              90
              ReLU-2           [-1, 10, 26, 26]               0
       BatchNorm2d-3           [-1, 10, 26, 26]              20
           Dropout-4           [-1, 10, 26, 26]               0
            Conv2d-5           [-1, 32, 24, 24]           2,880
              ReLU-6           [-1, 32, 24, 24]               0
       BatchNorm2d-7           [-1, 32, 24, 24]              64
           Dropout-8           [-1, 32, 24, 24]               0
            Conv2d-9           [-1, 10, 22, 22]           2,880
             ReLU-10           [-1, 10, 22, 22]               0
      BatchNorm2d-11           [-1, 10, 22, 22]              20
          Dropout-12           [-1, 10, 22, 22]               0
        MaxPool2d-13           [-1, 10, 11, 11]               0
           Conv2d-14           [-1, 10, 11, 11]             100
             ReLU-15           [-1, 10, 11, 11]               0
           Conv2d-16             [-1, 10, 9, 9]             900
             ReLU-17             [-1, 10, 9, 9]               0
           Conv2d-18             [-1, 10, 7, 7]             900
             ReLU-19             [-1, 10, 7, 7]               0
           Conv2d-20             [-1, 10, 7, 7]             100
             ReLU-21             [-1, 10, 7, 7]               0
           Conv2d-22             [-1, 10, 1, 1]           4,900
================================================================
Total params: 12,854
Trainable params: 12,854
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 0.97
Params size (MB): 0.05
Estimated Total Size (MB): 1.02
```

------------------------------------------------------------------------------------

## Model-3 execution

## Target:
- Reduce parameters bellow 10k count
- Make sure, defined model get trained, also add GAP, MaxPool,
- Achive test accuracy > 99.40%
- Limit the 20 epoch

## Result:
- Parameters: 9,180
- Best Training Accuracy: 99.32%
- Best Test Accuracy: 99.42%

## Analysis:
- model trained with 9k parameters
- Added Batch Normalization, MaxPool2d and dropout = 0.1
- skip added
- Model test accuracy achieved 99.42% on 15th epoch
- Model is Good fitting from 19th epoch (training accuracy: 99.32% test accuracy: 99.35%)
- After adding image augmentations and StepLR, model is looks good on epoch 13th  (training accuracy: 99.16% test accuracy: 99.46%)

## Model-3 Summary
```
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: torchsummary in /Users/sawan.darekar/Library/Python/3.9/lib/python/site-packages (1.5.1)
cpu
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1           [-1, 12, 26, 26]             108
              ReLU-2           [-1, 12, 26, 26]               0
       BatchNorm2d-3           [-1, 12, 26, 26]              24
           Dropout-4           [-1, 12, 26, 26]               0
            Conv2d-5           [-1, 16, 24, 24]           1,728
              ReLU-6           [-1, 16, 24, 24]               0
       BatchNorm2d-7           [-1, 16, 24, 24]              32
           Dropout-8           [-1, 16, 24, 24]               0
            Conv2d-9           [-1, 12, 22, 22]           1,728
             ReLU-10           [-1, 12, 22, 22]               0
      BatchNorm2d-11           [-1, 12, 22, 22]              24
          Dropout-12           [-1, 12, 22, 22]               0
        MaxPool2d-13           [-1, 12, 11, 11]               0
           Conv2d-14             [-1, 16, 9, 9]           1,728
             ReLU-15             [-1, 16, 9, 9]               0
      BatchNorm2d-16             [-1, 16, 9, 9]              32
          Dropout-17             [-1, 16, 9, 9]               0
           Conv2d-18             [-1, 16, 7, 7]           2,304
             ReLU-19             [-1, 16, 7, 7]               0
      BatchNorm2d-20             [-1, 16, 7, 7]              32
          Dropout-21             [-1, 16, 7, 7]               0
           Conv2d-22             [-1, 10, 5, 5]           1,440
        AvgPool2d-23             [-1, 10, 1, 1]               0
================================================================
Total params: 9,180
Trainable params: 9,180
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 0.78
Params size (MB): 0.04
Estimated Total Size (MB): 0.82
----------------------------------------------------------------
```

## Logs from local model run
```
EPOCH:0 Loss=0.050359949469566345 Batch_id=937 Accuracy=93.87 LR=0.01: 100%|██████████| 938/938 [01:05<00:00, 14.37it/s]

Test set: Average loss: 0.0531, Accuracy: 9840/10000 (98.40%)

EPOCH:1 Loss=0.14306209981441498 Batch_id=937 Accuracy=98.08 LR=0.01: 100%|██████████| 938/938 [01:07<00:00, 13.93it/s]  

Test set: Average loss: 0.0456, Accuracy: 9864/10000 (98.64%)

EPOCH:2 Loss=0.011142509058117867 Batch_id=937 Accuracy=98.32 LR=0.01: 100%|██████████| 938/938 [01:07<00:00, 14.00it/s] 

Test set: Average loss: 0.0315, Accuracy: 9900/10000 (99.00%)

EPOCH:3 Loss=0.055059969425201416 Batch_id=937 Accuracy=98.54 LR=0.01: 100%|██████████| 938/938 [01:02<00:00, 14.93it/s] 

Test set: Average loss: 0.0324, Accuracy: 9895/10000 (98.95%)

EPOCH:4 Loss=0.09678667783737183 Batch_id=937 Accuracy=98.59 LR=0.01: 100%|██████████| 938/938 [01:08<00:00, 13.77it/s]  

Test set: Average loss: 0.0268, Accuracy: 9919/10000 (99.19%)

EPOCH:5 Loss=0.02437777630984783 Batch_id=937 Accuracy=98.76 LR=0.01: 100%|██████████| 938/938 [01:01<00:00, 15.32it/s]  

Test set: Average loss: 0.0260, Accuracy: 9918/10000 (99.18%)

EPOCH:6 Loss=0.005321050062775612 Batch_id=937 Accuracy=99.03 LR=0.001: 100%|██████████| 938/938 [01:04<00:00, 14.44it/s] 

Test set: Average loss: 0.0213, Accuracy: 9939/10000 (99.39%)

EPOCH:7 Loss=0.12339828908443451 Batch_id=937 Accuracy=99.09 LR=0.001: 100%|██████████| 938/938 [01:02<00:00, 15.08it/s]  

Test set: Average loss: 0.0227, Accuracy: 9935/10000 (99.35%)

EPOCH:8 Loss=0.0072998171672225 Batch_id=937 Accuracy=99.07 LR=0.001: 100%|██████████| 938/938 [01:02<00:00, 15.08it/s]   

Test set: Average loss: 0.0205, Accuracy: 9942/10000 (99.42%)

EPOCH:9 Loss=0.020701149478554726 Batch_id=937 Accuracy=99.12 LR=0.001: 100%|██████████| 938/938 [01:03<00:00, 14.72it/s] 

Test set: Average loss: 0.0216, Accuracy: 9941/10000 (99.41%)

EPOCH:10 Loss=0.003521702717989683 Batch_id=937 Accuracy=99.10 LR=0.001: 100%|██████████| 938/938 [01:08<00:00, 13.64it/s] 

Test set: Average loss: 0.0200, Accuracy: 9941/10000 (99.41%)

EPOCH:11 Loss=0.0066545079462230206 Batch_id=937 Accuracy=99.11 LR=0.001: 100%|██████████| 938/938 [01:01<00:00, 15.21it/s]

Test set: Average loss: 0.0198, Accuracy: 9944/10000 (99.44%)

EPOCH:12 Loss=0.04731645807623863 Batch_id=937 Accuracy=99.08 LR=0.0001: 100%|██████████| 938/938 [01:02<00:00, 15.05it/s]  

Test set: Average loss: 0.0195, Accuracy: 9944/10000 (99.44%)

EPOCH:13 Loss=0.014920426532626152 Batch_id=937 Accuracy=99.16 LR=0.0001: 100%|██████████| 938/938 [01:02<00:00, 15.05it/s] 

Test set: Average loss: 0.0196, Accuracy: 9946/10000 (99.46%)

EPOCH:14 Loss=0.012708238326013088 Batch_id=937 Accuracy=99.10 LR=0.0001: 100%|██████████| 938/938 [01:05<00:00, 14.28it/s] 

Test set: Average loss: 0.0194, Accuracy: 9944/10000 (99.44%)

EPOCH:15 Loss=0.009212363511323929 Batch_id=937 Accuracy=99.12 LR=0.0001: 100%|██████████| 938/938 [01:05<00:00, 14.42it/s] 

Test set: Average loss: 0.0203, Accuracy: 9942/10000 (99.42%)

EPOCH:16 Loss=0.021923506632447243 Batch_id=937 Accuracy=99.16 LR=0.0001: 100%|██████████| 938/938 [01:01<00:00, 15.29it/s] 

Test set: Average loss: 0.0199, Accuracy: 9942/10000 (99.42%)

EPOCH:17 Loss=0.0035537886433303356 Batch_id=937 Accuracy=99.12 LR=0.0001: 100%|██████████| 938/938 [01:02<00:00, 15.02it/s]

Test set: Average loss: 0.0203, Accuracy: 9943/10000 (99.43%)

EPOCH:18 Loss=0.014232362620532513 Batch_id=937 Accuracy=99.17 LR=1e-05: 100%|██████████| 938/938 [01:04<00:00, 14.47it/s] 

Test set: Average loss: 0.0200, Accuracy: 9944/10000 (99.44%)

EPOCH:19 Loss=0.004888974595814943 Batch_id=937 Accuracy=99.16 LR=1e-05: 100%|██████████| 938/938 [01:04<00:00, 14.47it/s] 

Test set: Average loss: 0.0195, Accuracy: 9943/10000 (99.43%)
```

------------------------------------------------------------------------------------

## Model-4 execution

## Target:
- Reduce parameters bellow 8k count
- Achive test accuracy > 99%
- Limit the 15 epoch

## Result:
- Parameters: 7,616
- Best Training Accuracy: 99.34%
- Best Test Accuracy: 98.94%

## Analysis:
- model trained with 7,616 parameters
- Added Batch Normalization, MaxPool2d, skip and dropout = 0.25
- Model test accuracy achieved 99.34% on 7th epoch
- Model is Good fitting from 14th epoch (training accuracy: 98.94% test accuracy: 99.29%)

## Model-4 Summary
```
Requirement already satisfied: torchsummary in /Users/sawan.darekar/Library/Python/3.9/lib/python/site-packages (1.5.1)
cpu
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Conv2d-1            [-1, 8, 26, 26]              72
              ReLU-2            [-1, 8, 26, 26]               0
       BatchNorm2d-3            [-1, 8, 26, 26]              16
            Conv2d-4           [-1, 16, 24, 24]           1,152
              ReLU-5           [-1, 16, 24, 24]               0
       BatchNorm2d-6           [-1, 16, 24, 24]              32
            Conv2d-7           [-1, 16, 24, 24]             256
            Conv2d-8           [-1, 16, 22, 22]           2,304
              ReLU-9           [-1, 16, 22, 22]               0
      BatchNorm2d-10           [-1, 16, 22, 22]              32
          Dropout-11           [-1, 16, 22, 22]               0
        MaxPool2d-12           [-1, 16, 11, 11]               0
           Conv2d-13             [-1, 12, 9, 9]           1,728
             ReLU-14             [-1, 12, 9, 9]               0
      BatchNorm2d-15             [-1, 12, 9, 9]              24
           Conv2d-16             [-1, 10, 7, 7]           1,080
             ReLU-17             [-1, 10, 7, 7]               0
      BatchNorm2d-18             [-1, 10, 7, 7]              20
          Dropout-19             [-1, 10, 7, 7]               0
           Conv2d-20             [-1, 10, 5, 5]             900
        AvgPool2d-21             [-1, 10, 1, 1]               0
================================================================
Total params: 7,616
Trainable params: 7,616
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 0.70
Params size (MB): 0.03
Estimated Total Size (MB): 0.73
----------------------------------------------------------------
```

## Logs from local model run
```
EPOCH:0 Loss=0.18715344369411469 Batch_id=937 Accuracy=93.59 LR=0.01: 100%|██████████| 938/938 [00:46<00:00, 20.23it/s] 

Test set: Average loss: 0.0690, Accuracy: 9795/10000 (97.95%)

EPOCH:1 Loss=0.19505208730697632 Batch_id=937 Accuracy=97.92 LR=0.01: 100%|██████████| 938/938 [00:46<00:00, 20.14it/s]  

Test set: Average loss: 0.0416, Accuracy: 9883/10000 (98.83%)

EPOCH:2 Loss=0.007006138097494841 Batch_id=937 Accuracy=98.37 LR=0.01: 100%|██████████| 938/938 [00:44<00:00, 20.85it/s] 

Test set: Average loss: 0.0319, Accuracy: 9909/10000 (99.09%)

EPOCH:3 Loss=0.017481563612818718 Batch_id=937 Accuracy=98.52 LR=0.01: 100%|██████████| 938/938 [00:45<00:00, 20.81it/s] 

Test set: Average loss: 0.0379, Accuracy: 9879/10000 (98.79%)

EPOCH:4 Loss=0.022609738633036613 Batch_id=937 Accuracy=98.61 LR=0.01: 100%|██████████| 938/938 [00:44<00:00, 21.05it/s] 

Test set: Average loss: 0.0307, Accuracy: 9904/10000 (99.04%)

EPOCH:5 Loss=0.14657919108867645 Batch_id=937 Accuracy=98.78 LR=0.01: 100%|██████████| 938/938 [00:45<00:00, 20.62it/s]  

Test set: Average loss: 0.0270, Accuracy: 9913/10000 (99.13%)

EPOCH:6 Loss=0.005493962671607733 Batch_id=937 Accuracy=99.03 LR=0.001: 100%|██████████| 938/938 [00:45<00:00, 20.42it/s] 

Test set: Average loss: 0.0221, Accuracy: 9933/10000 (99.33%)

EPOCH:7 Loss=0.011255555786192417 Batch_id=937 Accuracy=99.14 LR=0.001: 100%|██████████| 938/938 [00:46<00:00, 20.33it/s] 

Test set: Average loss: 0.0216, Accuracy: 9935/10000 (99.35%)

EPOCH:8 Loss=0.014437520876526833 Batch_id=937 Accuracy=99.19 LR=0.001: 100%|██████████| 938/938 [00:44<00:00, 21.14it/s] 

Test set: Average loss: 0.0226, Accuracy: 9931/10000 (99.31%)

EPOCH:9 Loss=0.01441136747598648 Batch_id=937 Accuracy=99.22 LR=0.001: 100%|██████████| 938/938 [00:44<00:00, 21.26it/s]  

Test set: Average loss: 0.0209, Accuracy: 9933/10000 (99.33%)

EPOCH:10 Loss=0.008322898298501968 Batch_id=937 Accuracy=99.20 LR=0.001: 100%|██████████| 938/938 [00:43<00:00, 21.56it/s] 

Test set: Average loss: 0.0210, Accuracy: 9934/10000 (99.34%)

EPOCH:11 Loss=0.01440573763102293 Batch_id=937 Accuracy=99.17 LR=0.001: 100%|██████████| 938/938 [00:45<00:00, 20.75it/s]  

Test set: Average loss: 0.0210, Accuracy: 9933/10000 (99.33%)

EPOCH:12 Loss=0.0017709368839859962 Batch_id=937 Accuracy=99.21 LR=0.0001: 100%|██████████| 938/938 [00:46<00:00, 20.17it/s]

Test set: Average loss: 0.0209, Accuracy: 9933/10000 (99.33%)

EPOCH:13 Loss=0.03472159057855606 Batch_id=937 Accuracy=99.24 LR=0.0001: 100%|██████████| 938/938 [00:45<00:00, 20.67it/s]  

Test set: Average loss: 0.0212, Accuracy: 9932/10000 (99.32%)

EPOCH:14 Loss=0.006048769690096378 Batch_id=937 Accuracy=99.26 LR=0.0001: 100%|██████████| 938/938 [00:43<00:00, 21.35it/s] 

Test set: Average loss: 0.0209, Accuracy: 9935/10000 (99.35%)
```


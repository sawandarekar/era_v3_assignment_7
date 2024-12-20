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
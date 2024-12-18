# era_v3_assignment_7

# Model-1 execution

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

------------------------------------------------------------------------------------

# Model-2 execution

## Target:
- Reduce parameters count
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

------------------------------------------------------------------------------------
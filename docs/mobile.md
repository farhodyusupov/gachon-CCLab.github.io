---
layout: default
title: FedOps Mobile
nav_order: 5
---
# FedOps Mobile

## Mobile Components
![FedOps Mobile Image](../img/mobile_detail.png)

### FedOps Mobile based on Flutter

- Design FedOps Mobile UI with Flutter
- Android: on-device training based on Tensorflow Lite
- iOS: on-device training based on CoreML
API
### FedOps Flutter Documentation (Android) - v1.0

Classes:

```dart
FedOps{}
```

```dart
TrainingConfiguration{
	int round;
	int epoch;
}
```

```dart
TrainingProccessInfo{
	int currentRound;
	int currentEpoch;
}
```

```dart
TrainingResults{
	List<double> accuracy = [];
	List<double> loss = [];
}
```

Methods:

getDataset(String source) → Future<bool> - this methods loads dataset from given source. For now, load the dataset from only assets from app assets. More features coming!

example:

```dart
bool? datasetResult = await getDataset("assets"); 
```

getModel(String source) →Future<bool> - this method loads model from given source. For now loads model from only cloud. More features coming!

```dart
bool? modelResult = await getModel("sourceLink");
```

connectServer(String serverIp) → Future<bool> - this method checks connection channel between server and client. 

```dart
bool? connectionResult = await connectServer("yourServerIp);
```

startTrain() → void - if the setup is a good start training process. 

```dart
startTrain();
```

getConfigurations() →TrainingConfiguration trainingConfiguration - if training has been started successfully, returns configurations of the current training session.

```dart
TrainingConfiguration? trainingConfigurations = await getConfigurations();
```

getTrainProccessInfo() → Stream<TrainingProccessInfo> trainingProccessInfo - returns current epoch and round as a stream data.

```dart
StreamListener<TrainingProccessInfo>(
stream: getTrainProccessInfo(),
child: YourChildWidgetOfUI(),
);
```

getTrainResults() → Future<TrainingResults> trainingResults - when training is finished, returns results (accuracy and lost).

```dart
TrainingResults? trainingResults = await getTrainResults();
```

## FedOps Mobile Scenario
![FedOps Mobile Scenario](../img/mobile_scenario.png)<br>
- [FedOps Mobile Guide](https://gachon-cclab.github.io/docs/user-guide/mobile-guide/)

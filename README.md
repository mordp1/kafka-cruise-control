# kafka-cruise-control

View [CHANGELOG](CHANGELOG.md) for important changes.

# Docker image

https://hub.docker.com/r/adobe/cruise-control

# Kafa Cruise Control

https://github.com/linkedin/cruise-control

# References from Amazon AWS Support :

[1] Best Practices - Reassign partitions - https://docs.aws.amazon.com/msk/latest/developerguide/bestpractices.html#bestpractices-balance-cluster

[2] Amazon MSK customers can now use Cruise Control to more easily scale and balance resource utilization within clusters
https://aws.amazon.com/about-aws/whats-new/2020/11/amazon-msk-customers-can-now-use-cruise-control-to-more-easily-scale-and-balance-resource-utilization-within-clusters/

[3] Using LinkedIn's Cruise Control for Apache Kafka with Amazon MSK
https://docs.aws.amazon.com/msk/latest/developerguide/cruise-control.html

[4] Cruise Control workshop - https://amazonmsk-labs.workshop.aws/en/cruisecontrol.html

# Topics 

We must create this topic in the Kafka Cluster.

`__CruiseControlMetrics`

`__KafkaCruiseControlModelTrainingSamples`

`__KafkaCruiseControlPartitionMetricSamples`

# Help

### Before install, change the [values-dev.yaml](helm/values-dev.yaml) with your Kafka cluster configurations.


Install
```bash
helm install cruise-control helm -f helm/values.yaml -f helm/values-dev.yaml
```

Generate all manifest
```bash
helm template -f values.yaml -f values-dev.yaml --output-dir "/tmp" "./" --debug
```

uninstall
```bash
helm uninstall cruise-control
```
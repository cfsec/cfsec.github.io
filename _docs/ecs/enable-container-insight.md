---
title: ECS clusters should have container insights enabled
shortcode: enable-container-insight
summary: ECS clusters should have container insights enabled 
permalink: /docs/ecs/enable-container-insight/
---

### Explanation

Cloudwatch Container Insights provide more metrics and logs for container based applications and micro services.

### Possible Impact
Not all metrics and logs may be gathered for containers when Container Insights isn't enabled

### Suggested Resolution
Enable Container Insights


### Insecure Example

The following example will fail the  check.

```yaml
---
Resources:
  BadExample:
    Type: 'AWS::ECS::Cluster'
    Properties:
      ClusterName: MyCluster

```



### Secure Example

The following example will pass the  check.

```yaml
---
Resources:
  GoodExample:
    Type: 'AWS::ECS::Cluster'
    Properties:
      ClusterName: MyCluster
      ClusterSettings:
        - Name: containerInsights
          Value: enabled

```




### Related Links


- [https://cfsec.dev/docs/ecs/enable-container-insight/#ecs](https://cfsec.dev/docs/ecs/enable-container-insight/#ecs)

- [https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ContainerInsights.html](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/ContainerInsights.html)



# fractal
A thin library for building auto-scalable services

AWS Auto Scaling and CloudWatch services work well in combination. A CloudWatch alarm, when triggered, requests Auto Scaling to scale up/down your service.

There are limits to these in-house technologies however: The business logic of your service is opaque to AWS, thus commodity metrics related to memory, disk, network, etc. are not enough to define an auto scaling strategy if the latter depends on the logic.

Though CloudWatch offers a way to integrate a service by defining custom metrics and alarms, this can add another layer of complexity especially when the service is already using another metrics sink. More importantly that this, the solution does not cover stateful scaling (sharding, highly customisable services, etc.)

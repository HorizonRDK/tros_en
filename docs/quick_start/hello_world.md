---
sidebar_position: 4
---
# 1.4 Hello World

Prerequisite: TogetheROS.Bot has been successfully installed via deb package or source code.

Open two terminals and ssh login to the horizon RDK device.

In the first terminal, run:

```shell
source /opt/tros/setup.bash
ros2 run examples_rclcpp_minimal_subscriber subscriber_member_function
```

In the second terminal, run:

```shell
source /opt/tros/setup.bash
ros2 run examples_rclcpp_minimal_publisher publisher_member_function
```

The running effect is shown in the following image:

![hello world](./image/hello_world/hello_world.png "hello world")

As you can see, the left terminal acts as the publisher, continuously sending "Hello, world! N", and the right terminal acts as the subscriber, continuously receiving "Hello, world! N".

OK, tros.b has been successfully installed and verified!
# Getting Started With ROS

> There's work and there's your best work. The kind of work that has your fingerprints all over it. The kind of work you'd never compromise on. That you can't stop thinking about.

Now it's time to do that kind of work.

## ROS Tutorial

As a first step, follow [ROS tutorial](https://wiki.ros.org/ROS/Tutorials). Reading alone is not enough. Make sure to block a few hours, sit tight in front of a computer, and actually try out each command and example yourself.

While doing it, pay attention to **concepts** and **tools**. They are important not only because you need to apply them frequently in your project, but also they give you an overview of how modern robotics software is designed and built. As someone who knows ROS, things will look familiar to you even in the most ambitious robotics project today.

## Use A Container

[Container](https://www.docker.com/resources/what-container) is industry standard for maintaining consistent environment. We benefit in various ways by running ROS in containers for development and production:

- ROS has many dependencies and also requires a corresponding version of Ubuntu. Container makes changing ROS distribution easy.
- You can easily break ROS installation or encounter conflicting dependencies if you develop and deploy the project on a robot directly. Container provides the isolation that gives you a clean and consistent environment every time.
- Container allows your project to run on any machine. So you can develop at the comfort of your home knowing it will work just as expected on the robot.

Follow these steps to run ROS tutorial with Docker container:

1. [Install Docker](https://docs.docker.com/engine/install) on the machine you want to run ROS tutorial. Docker helps you manage containers.
1. Running node `turtlesim_node` in the tutorial needs GUI. Install X11 server [XQuartz](https://www.xquartz.org) on Mac or [VcXsrv](https://sourceforge.net/projects/vcxsrv) on Windows. You may need to change `docker-compose.yaml` according to your X11 server setup. It is OK to defer this step.
1. [Clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this repository or download zip.
1. Open command line (Terminal on Mac or Powershell on Windows), change directory to where this file is with `cd` command.
1. Run the container. You will get an interactive shell session where ROS commands, `turtlesim` package, and everything else you need is available. Now go ahead and complete ROS tutorial.
    ```
    docker compose run --rm --name ros-tutorial ros-tutorial
    ```
1. While the container is running, run this command in another command line window to get another shell session to the container. It is helpful for example when you run `roscore` in one window and want to do something else in another.
    ```
    docker exec -it ros-tutorial bash
    ```

1. Use [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) in [Visual Studio Code](https://code.visualstudio.com) to write code in the container. Place the code under `/code` in the container and find it in `code` under the same directory as this file on the host machine. Files will not be saved if placed anywhere else.

Have fun.

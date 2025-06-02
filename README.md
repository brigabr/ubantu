# Docker安装Ubantu

在 Docker 中运行一个 Linux 容器，实际上就是在 Docker 容器内运行一个 Linux 发行版的镜像。以下是如何在 Docker 中安装并运行 Linux 发行版的步骤，通常我们直接使用官方提供的 Linux 镜像（如 Ubuntu、CentOS 等）来创建容器。

### 1. **确保 Docker 已安装**

首先确保你已经在主机系统上正确安装并配置好了 Docker。

运行以下命令来检查 Docker 是否正常安装：

```
docker --version
```

如果尚未安装 Docker，请根据你使用的操作系统进行安装。你可以参考我之前提供的在 Windows 或 Linux 上安装 Docker 的步骤。

### 2. **下载并运行 Linux 镜像**

Docker Hub 提供了许多 Linux 发行版的官方镜像。你可以使用 `docker pull` 命令来下载相应的镜像，并使用 `docker run` 来启动一个容器。

### 以 Ubuntu 为例：

```
# 下载最新的 Ubuntu 镜像
docker pull ubuntu

# 运行 Ubuntu 容器并进入交互模式
docker run -it ubuntu /bin/bash
```

### 3. **在容器内进行操作**

运行 `docker run -it` 命令后，容器将启动，你会进入 Linux 系统的终端环境。此时你可以像操作正常的 Linux 系统一样，在容器内执行命令。

例如，更新软件包并安装一些工具：

```
# 更新包列表
apt-get update  # Ubuntu 容器
yum update      # CentOS 容器

# 安装 vim 编辑器
apt-get install vim  # Ubuntu 容器
yum install vim      # CentOS 容器
```

### 4. **退出容器**

如果你想退出容器的交互模式，可以输入 `exit`：

```
exit
```

这将停止并退出容器。

### 5. **查看运行中的容器**

你可以使用以下命令查看当前运行的容器：

```
docker ps
```

如果你想查看所有（包括已停止的）容器，可以使用：

```
docker ps -a
```

### 6. **重启已停止的容器**

如果你已经退出了容器，但想要重新启动它，可以使用以下命令：

```
# 重新启动已停止的容器
docker start <容器ID>

# 进入容器交互模式
docker exec -it <容器ID> /bin/bash
```

### 7. **删除容器**

如果不再需要某个容器，你可以将其删除：

```
docker rm <容器ID>
```

### 8. **删除镜像**

如果你不再需要某个 Linux 镜像，可以将其删除以释放空间：

```
docker rmi <镜像ID>
```

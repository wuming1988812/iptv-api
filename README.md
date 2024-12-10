<div align="center">
  <img src="./static/images/logo.png" alt="logo"/>
  <h1 align="center">IPTV-API</h1>
</div>

<div align="center">自定义频道，自动获取直播源接口，测速验效后生成可用的结果</div>
<div align="center">默认结果包含：央视频道、央视付费频道、卫视频道、港·澳·台频道、电影频道、体育频道、动画频道、游戏频道</div>

</details>
<br>
<p align="center">
  <a href="https://github.com/Guovin/iptv-api/releases/latest">
    <img src="https://img.shields.io/github/v/release/guovin/iptv-api" />
  </a>
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/python-%20%3D%203.13-47c219" />
  </a>
  <a href="https://github.com/Guovin/iptv-api/releases/latest">
    <img src="https://img.shields.io/github/downloads/guovin/iptv-api/total" />
  </a>
  <a href="https://hub.docker.com/repository/docker/guovern/iptv-api">
    <img src="https://img.shields.io/docker/pulls/guovern/iptv-api?label=docker:iptv-api" />
  </a>
  <a href="https://hub.docker.com/repository/docker/guovern/tv-requests">
    <img src="https://img.shields.io/docker/pulls/guovern/tv-requests?label=docker:requests" />
  </a>
  <a href="https://hub.docker.com/repository/docker/guovern/tv-driver">
    <img src="https://img.shields.io/docker/pulls/guovern/tv-driver?label=docker:driver" />
  </a>
  <a href="https://github.com/Guovin/iptv-api/fork">
    <img src="https://img.shields.io/github/forks/guovin/iptv-api" />
  </a>
</p>

[English](./README_en.md) | 中文



## 最新结果

- 接口源：

```bash
https://ghp.ci/raw.githubusercontent.com/wuming1988812/iptv-api/gd/output/result.m3u
```

```bash
https://ghp.ci/raw.githubusercontent.com/wuming1988812/iptv-api/gd/output/result.txt
```

- 数据源：

```bash
https://ghp.ci/raw.githubusercontent.com/Guovin/iptv-api/gd/source.json
```

## 配置

[配置参数](./docs/config.md)

## 快速上手

### 方式一：工作流

Fork 本项目并开启工作流更新，具体步骤请见[详细教程](./docs/tutorial.md)

### 方式二：命令行

```python
pip install pipenv
```

```python
pipenv install --dev
```

启动更新：

```python
pipenv run dev
```

启动服务：

```python
pipenv run service
```

### 方式三：GUI 软件

1. 下载[IPTV-API 更新软件](https://github.com/Guovin/iptv-api/releases)，打开软件，点击更新，即可完成更新

2. 或者在项目目录下运行以下命令，即可打开 GUI 软件：

```python
pipenv run ui
```

<img src="./docs/images/ui.png" alt="IPTV-API更新软件" title="IPTV-API更新软件" style="height:600px" />

### 方式四：Docker

- iptv-api（完整版本）：性能要求较高，更新速度较慢，稳定性、成功率高；修改配置 open_driver = False 可切换到 Lite 版本运行模式（推荐酒店源、组播源、关键字搜索使用此版本）
- iptv-api:lite（精简版本）：轻量级，性能要求低，更新速度快，稳定性不确定（推荐订阅源使用此版本）

1. 拉取镜像：

- iptv-api：

```bash
docker pull guovern/iptv-api:latest
```

- iptv-api:lite：

```bash
docker pull guovern/iptv-api:lite
```

2. 运行容器：

- iptv-api：

```bash
docker run -d -p 8000:8000 guovern/iptv-api
```

- iptv-api:lite：

```bash
docker run -d -p 8000:8000 guovern/iptv-api:lite
```

卷挂载参数（可选）：
实现宿主机文件与容器文件同步，修改模板、配置、获取更新结果文件可直接在宿主机文件夹下操作

以宿主机路径/etc/docker 为例：

- iptv-api：

```bash
docker run -v /etc/docker/config:/iptv-api/config -v /etc/docker/output:/iptv-api/output -d -p 8000:8000 guovern/iptv-api
```

- iptv-api:lite：

```bash
docker run -v /etc/docker/config:/iptv-api-lite/config -v /etc/docker/output:/iptv-api-lite/output -d -p 8000:8000 guovern/iptv-api:lite
```

3. 更新结果：

- 接口地址：ip:8000
- M3u 接口：ip:8000/m3u
- Txt 接口：ip:8000/txt
- 接口内容：ip:8000/content
- 测速日志：ip:8000/log

## 更新日志

[更新日志](./CHANGELOG.md)


## 免责声明

本项目仅供学习交流用途，接口数据均来源于网络，如有侵权，请联系删除

## 许可证

[MIT](./LICENSE) License &copy; 2024-PRESENT [Govin](https://github.com/guovin)

<div align="center">
  <img src="./static/images/logo.png" alt="logo"/>
  <h1 align="center">IPTV-API</h1>
</div>

<div align="center">Customize channels, automatically obtain live source interface, and generate usable results after speed test</div>
<div align="justify">Default results include: CCTV Channel, CCTV Pay Channel, Satellite TV Channel,  Hong Kong · Macao · Taiwan Channel, Sports Channel, Animation channel, Game channel</div>
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

## Latest results

- Interface source:

```bash
https://ghp.ci/raw.githubusercontent.com/wuming1988812/iptv-api/gd/output/result.m3u
```

```bash
https://ghp.ci/raw.githubusercontent.com/wuming1988812/iptv-api/gd/output/result.txt
```

- Data source:

```bash
https://ghp.ci/raw.githubusercontent.com/Guovin/iptv-api/gd/source.json
```

## Config

[Config parameter](./docs/config_en.md)

## Quick Start

### Method 1: Workflow

Fork this project and initiate workflow updates, detailed steps are available at [Detailed Tutorial](./docs/tutorial_en.md)

### Method 2: Command Line

```python
pip install pipenv
```

```python
pipenv install --dev
```

Start update:

```python
pipenv run dev
```

Start service:

```python
pipenv run service
```

### Method 3: GUI Software

1. Download [IPTV-API update software](https://github.com/Guovin/iptv-api/releases), open the software, click update to complete the update

2. Or run the following command in the project directory to open the GUI software:

```python
pipenv run ui
```

<img src="./docs/images/ui.png" alt="IPTV-API update software" title="IPTV-API update software" style="height:600px" />

### Method 4: Docker

- iptv-api (Full version): Higher performance requirements, slower update speed, high stability and success rate. Set open_driver = False to switch to the lite running mode (recommended for hotel sources, multicast sources, and online searches)
- iptv-api:lite (Condensed version): Lightweight, low performance requirements, fast update speed, stability uncertain (recommend using this version for the subscription source)

It's recommended to try each one and choose the version that suits you

1. Pull the image:

- iptv-api

```bash
docker pull guovern/iptv-api:latest
```

- iptv-api:lite

```bash
docker pull guovern/iptv-api:lite
```

2. Run the container:

- iptv-api

```bash
docker run -d -p 8000:8000 guovern/iptv-api
```

- iptv-api:lite

```bash
docker run -d -p 8000:8000 guovern/iptv-api:lite
```

Volume Mount Parameter (Optional):
This allows synchronization of files between the host machine and the container. Modifying templates, configurations, and retrieving updated result files can be directly operated in the host machine's folder.

Taking the host path /etc/docker as an example:

- iptv-api：

```bash
docker run -v /etc/docker/config:/iptv-api/config -v /etc/docker/output:/iptv-api/output -d -p 8000:8000 guovern/iptv-api
```

- iptv-api:lite：

```bash
docker run -v /etc/docker/config:/iptv-api-lite/config -v /etc/docker/output:/iptv-api-lite/output -d -p 8000:8000 guovern/iptv-api:lite
```

3. Update results:

- API address: ip:8000
- M3u api：ip:8000/m3u
- Txt api：ip:8000/txt
- API content: ip:8000/content
- Speed test log: ip:8000/log

## Changelog

[Changelog](./CHANGELOG.md)



## Disclaimer

This project is for learning and communication purposes only. All interface data comes from the internet. If there is any infringement, please contact us for removal.

## License

[MIT](./LICENSE) License &copy; 2024-PRESENT [Govin](https://github.com/guovin)

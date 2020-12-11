# Docker image: Ansible on Jupyter Notebook

[![Docker Hub](https://img.shields.io/badge/docker-ansible--jupyter-blue.svg)](https://hub.docker.com/r/chusiang/ansible-jupyter/) [![microbadger](https://images.microbadger.com/badges/image/chusiang/ansible-jupyter.svg)](https://microbadger.com/images/chusiang/ansible-jupyter "Get your own image badge on microbadger.com")

A Docker image for run [Ansible][ansible_official] 2.x on [Jupyter Notebook][jupyter_official] 4.x (ipython notebook) with Browsers.

[ansible_official]: https://www.ansible.com/
[jupyter_official]: http://jupyter.org/

## Supported tags and respective `Dockerfile` links

- `alpine-3`, `latest` [*(alpine-3/Dockerfile)*][dockerfile_alpine-3]
- `archlinux` [*(archlinux/Dockerfile)*][dockerfile_archlinux]
- `centos-7` [*(centos-7/Dockerfile)*][dockerfile_centos-7]
- `debian-9` [*(debian-9/Dockerfile)*][dockerfile_debian-9]
- ~~`gentoo`~~ [*(gentoo/Dockerfile)*][dockerfile_gentoo]
- `opensuse-42.3` [*(opensuse-42.3/Dockerfile)*][dockerfile_opensuse-42.3]
- `ubuntu-18.04` [*(ubuntu-18.04/Dockerfile)*][dockerfile_ubuntu-18.04]

[dockerfile_alpine-3]:      https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/alpine-3/Dockerfile
[dockerfile_archlinux]:     https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/archlinux/Dockerfile
[dockerfile_centos-7]:      https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/centos-7/Dockerfile
[dockerfile_debian-9]:      https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/debian-9/Dockerfile
[dockerfile_gentoo]:        https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/gentoo/Dockerfile
[dockerfile_opensuse-42.3]: https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/opensuse-42.3/Dockerfile
[dockerfile_ubuntu-18.04]:  https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/ubuntu-18.04/Dockerfile

## Build image

1. Get this project.

    ```
    $ git clone https://github.com/chusiang/ansible-jupyter.dockerfile.git
    ```

1. Go to workspace.

    ```
    $ cd ansible-jupyter.dockerfile/<IMAGE_TAG>/
    ```

1. Bunild the image.

    ```
    $ docker build -t chusiang/ansible-jupyter .
    ```

## Run container

1. Get image.

    ```
    $ docker pull chusiang/ansible-jupyter
    ```

1. Run the container with daemon mode.

    ```
    $ docker run --name ansible-jupyter -P -d chusiang/ansible-jupyter
    be8a15b9d4da5d24610c1fc738cb13086f01101e90f94640360d8d84892de772
    ```

1. Check container process.

    ```
    $ docker ps
    CONTAINER ID        IMAGE                      COMMAND                  CREATED             STATUS              PORTS                     NAMES
    be8a15b9d4da        chusiang/ansible-jupyter   "docker-entrypoint.sh"   12 seconds ago      Up 11 seconds       0.0.0.0:32808->8888/tcp   ansible-jupyter
    ```

1. Enter container with command line.

    ```
    $ docker exec -it ansible-jupyter sh
    / #
    ```

## Play Ansible on Jupyter

Now, you can play the Ansible on Jupyter.

1. Go jupyter web.

    ```
    # GNU/Linux
    $ firefox http://localhost:32786

    # macOS
    $ open http://localhost:32786
    ```

    ![2016-11-20-ansible-jupyter1]

1. Attach my example ==> [`ansible_on_jupyter.ipynb`][ansible_on_jupyter.ipynb].

    ![2016-11-20-ansible-jupyter2]

1. Remember use the `!` prefix to trigger system command.

You can see more detail at [怎麼用 Jupyter 操控 Ansible？(localhost) | 現代 IT 人一定要知道的 Ansible 自動化組態技巧](https://chusiang.gitbooks.io/automate-with-ansible/07.how-to-practive-the-ansible-with-jupyter1.html) .

Enjoy it !

[ansible_on_jupyter.ipynb]: https://github.com/chusiang/ansible-jupyter.dockerfile/blob/master/ipynb/ansible_on_jupyter.ipynb
[2016-11-20-ansible-jupyter1]: https://cloud.githubusercontent.com/assets/219066/20463322/218f0c4a-af6b-11e6-9a95-2411ec7acb5f.png
[2016-11-20-ansible-jupyter2]: https://cloud.githubusercontent.com/assets/219066/20463319/fa8c047c-af6a-11e6-96d6-f985096c9c8c.png

## History

### 2020

* 12/12 Fixed Python 3 dependency problem on Alpine Linux v3.12, and stop support some EOL images.

### 2018

* 07/11 Add new images of `alpine-3.8`. Stop automated build image of `alpine-3.4`, `alpine-3.6` and `opensuse-42.2`.
* 06/18 Add new images of `alpine-3.7`, `ubuntu-18.04`. Stop automated build image of `ubuntu-14.04`.
* 01/10 Stop automated build images of `centos-6`, `debian-7` and `alpine-3.4_ansible-2.1`.

### 2017

* ??/?? Stop automated build images of `gentoo`, `opensuse-42.1` and `alpine-3.4`.

## License

Copyright (c) chusiang from 2016-2020 under the MIT license.

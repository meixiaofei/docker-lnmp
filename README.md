# docker-lnmp
本来是为了在windows下跑一个得在linux环境下跑的应用，奈何本地开发的时候容器与宿主之间似乎有磁盘读写性能问题，虽然再弄个容器将宿主目录项目自动同步到些容器，
会好一丢丢，但体验还是惨不忍睹。。跟扣群里的一些大佬交流了下，似乎他们都只在linux下跑docker, 没遇着这毛病，QaQ


### Usage
1. Install `git`, `docker` and `docker-compose` (on windows you can use [cmder](http://cmder.net/))
2. Clone project:
    ```
    git clone git@github.com:meixiaofei/docker-lnmp.git
    ```
4. Start docker containers:
    ```
    docker-compose up
    ```
    You may need run this with 'docker cli', I forget whether need...
5. Have fun~

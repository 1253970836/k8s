# docker私有仓库
## 镜像启动docker registry123
><code>docker run -d -p 5000:5000 --restart=always --name registry -v /mnt/registry:/var/lib/registry --privileged=true registry:2</code>
>
>需使用私有仓库的主机打开/etc/sysconfig/docker，OPTIONS里添加 --insecure-registry=10.109.252.72:5000
## 上传镜像到私有仓库
>例：
>
><code>docker tag my_image 10.109.252.72:5000/my_image2:v1</code>
>
> <code>docker push 10.109.252.72:5000/my_image2:v1</code>
## 查看私有仓库镜像 
><code>curl 10.109.252.72:5000/v2/_catalog</code>
>
>查看挂载文件：<code>ll /mnt/registry/docker/registry/v2/repositories/</code>

  
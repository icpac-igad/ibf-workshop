# ibf-workshop



Link for docker images, https://hub.docker.com/r/datascience4ibf/climada_x64


To get the docker image

sudo docker pull datascience4ibf/climada_x64



After getting the docker image, use following codes to run the docker and start jupyter from the docker

```
sudo docker run -dit -p 8889:8889 datascience4ibf/climada_x64:version05
conda activate climada_env
jupyter notebook --ip 0.0.0.0 --port=8889 --no-browser --allow-root
```



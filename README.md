# ibf-workshop



Link for docker images, https://hub.docker.com/r/datascience4ibf/climada_x64


To get the docker image in pen drive, the file name is ds4ibf_climadav01.tar.gz
```
In linux
docker load < ds4ibf_climadav01.tar.gz
In windows
docker load -i ds4ibf_climadav01.tar.gz
```
After getting the docker image, use following codes to run the docker and start jupyter from the docker

```
sudo docker run -dit -p 8889:8889 datascience4ibf/climada_x64:v01
```
Once the docker is ran with contianer id printed, use that id to enter into the docker VM
```
sudo docker exec -it CONTAINERID bash
```
Next install some softwares needed for our workshop
```
conda activate climada_env
apt install git
apt install wget 
conda install -c conda-forge jupyter
conda install -c conda-forge lmoments3
python -m pip install climada
```
Now we have jupyter and git installed, get the workshop repo in docker VM home folder
```
cd /home
git clone https://github.com/icpac-igad/ibf-workshop.git
```
We recived the ibf-worshop folder in `/home` do `ls` to view the avialbality of folder
Now enter into the ibf-workshop folder and run jupyter notebook
```
jupyter notebook --ip 0.0.0.0 --port=8889 --no-browser --allow-root
```
To copy files and folder from local computer to inside the docker, run following command

```
sudo docker cp /home/ibf_workshop_data $CONTAINERID:/home/
```
To rectify error related to no tiff file availabel in Climada asset exposure data
```
mkdir /root/climada/data/gpw-v4-population-count-rev11_2020_30_sec_tif/
cp /home/ibf_workshop_data/exposure_data/asset/gpw_v4_population_count_rev11_2020_30_sec.tif /root/climada/data/gpw-v4-population-count-rev11_2020_30_sec_tif/

```





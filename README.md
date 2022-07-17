# Docker-To-GCR




Important commands to build a small nginx app in local docker desktop and push it to GCR
gcloud auth list
gcloud projects list
gcloud projects create my-gcp-labs-ace
gcloud beta billing accounts list
gcloud beta billing projects link my-gcp-labs-ace --billing-account=01331A-0D5EDC-A2596F

gcloud config set project my-gcp-labs-ace
gcloud config list project

docker pull nginx
docker images
docker cp index.html ee7d925cc555:/usr/share/nginx/html/
docker commit ee7d925cc555 sanweb:version2
docker run -d -p 82:80 sanweb:version2
http://localhost:82/  -- Accessing from Browser

docker tag sanweb:version1 asia.gcr.io/ace-gcp-labs/santosh-site:version1

Create a service account add compute storage admin permission
Generate a .json key and place it under /Users/sa302227/.docker 
Run the below command 
gcloud auth configure-docker
docker push asia.gcr.io/ace-gcp-labs/santosh-site:version1
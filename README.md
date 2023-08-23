# upload-docker-image-to-gcr-repo

**Step 1: Create Artifactory GCR repo:**

![image](https://github.com/tushardashpute/upload-docker-image-to-gcr-repo/assets/74225291/01188971-1bdf-48a2-b94b-fdcf5cd04b85)


![image](https://github.com/tushardashpute/upload-docker-image-to-gcr-repo/assets/74225291/9ff79a96-9c1a-4591-8cf1-92766a1bc7c0)


![image](https://github.com/tushardashpute/upload-docker-image-to-gcr-repo/assets/74225291/78228176-935e-49be-95d7-fbc0541480ec)


**Step 2: Configure Docker**
Run the following command to configure gcloud as the credential helper for the Artifact Registry domain associated with this repository's location:

    $ docker pull k8s.gcr.io/kubernetes-dashboard-amd64:v1.10.1
    v1.10.1: Pulling from kubernetes-dashboard-amd64
    9518d8afb433: Pull complete 
    Digest: sha256:0ae6b69432e78069c5ce2bcde0fe409c5c4d6f0f4d9cd50a17974fea38898747
    Status: Downloaded newer image for k8s.gcr.io/kubernetes-dashboard-amd64:v1.10.1
    k8s.gcr.io/kubernetes-dashboard-amd64:v1.10.1
    
    $ docker image ls
    REPOSITORY                                                                             TAG       IMAGE ID       CREATED       SIZE
    k8s.gcr.io/kubernetes-dashboard-amd64                                                  v1.10.1   f9aed6605b81   4 years ago   122MB
    southamerica-east1-docker.pkg.dev/murali-k-396216/k8s-dashboard/kubernetes-dashboard   v1.10.1   f9aed6605b81   4 years ago   122MB
    
    $ docker tag k8s.gcr.io/kubernetes-dashboard-amd64:v1.10.1 southamerica-east1-docker.pkg.dev/murali-k-396216/k8s-dashboard/kubernetes-dashboard:v1.10.1
    
    $ gcloud auth configure-docker southamerica-east1-docker.pkg.dev
    
    $ docker push southamerica-east1-docker.pkg.dev/murali-k-396216/k8s-dashboard/kubernetes-dashboard:v1.10.1
    The push refers to repository [southamerica-east1-docker.pkg.dev/murali-k-396216/k8s-dashboard/kubernetes-dashboard]
    fbdfe08b001c: Pushed 
    v1.10.1: digest: sha256:0ae6b69432e78069c5ce2bcde0fe409c5c4d6f0f4d9cd50a17974fea38898747 size: 529


![image](https://github.com/tushardashpute/upload-docker-image-to-gcr-repo/assets/74225291/52efb185-2772-40fc-9132-86716c353001)

    

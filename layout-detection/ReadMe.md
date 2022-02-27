# Docker container for Layout Detection troubleshooting.

1. `docker build . -t layout-detection-troubleshoot:1.0-latest`

2. `docker run -p 8888:8888 --name layout-detection-troubleshoot -v /Users/dileep.gadiraju/projects/deep-learning-tools/layout-detection/troubleshoot:/home/jovyan/work -it layout-detection-troubleshoot:1.0-latest`

3. `docker rm layout-detection-troubleshoot`

4. `docker exec -it layout-detection-troubleshoot /bin/bash`

###### Once the container is up , copy the URL in below pattern from container logs to Google Colab "Connect to local runtime" dialog and replace 127.0.0.1 with localhost. Should be able to connect Google colab to local docker container with all dependencies.

`http://127.0.0.1:8888/lab?token=8d55859d55c83fdc6813567220ca43ac471a7f915b73c299`
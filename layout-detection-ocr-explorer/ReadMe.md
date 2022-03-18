# Docker container for Layout Detection troubleshooting.

1. `docker build . -t layout-detection-ocr-explorer:1.0-latest`

2. `docker run -p 8888:8888 --name layout-detection-ocr-explorer -v <root_dir_full_path>/deep-learning-tools/layout-detection-ocr-explorer/troubleshoot:/home/jovyan/work -it layout-detection-ocr-explorer:1.0-latest`

3. `docker rm layout-detection-ocr-explorer`

4. `docker exec -it layout-detection-ocr-explorer /bin/bash`

###### Once the container is up , copy the URL in below pattern from container logs to Google Colab "Connect to local runtime" dialog and replace 127.0.0.1 with localhost. Should be able to connect Google colab to local docker container with all dependencies.

###### Open the jupyter notebook URL directly to browser and use the notebook for troubleshooting.
>> Example: `http://127.0.0.1:8888/lab?token=8d55859d55c83fdc6813567220ca43ac471a7f915b73c299`
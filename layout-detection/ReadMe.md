# Docker container for Layout Detection troubleshooting

1. `docker build . -t layout-detection-troubleshoot:1.0-latest`

2. `docker run -p 8888:8888 --name layout-detection-troubleshoot -it layout-detection-troubleshoot:1.0-latest`

3. `docker rm layout-detection-troubleshoot`

4. `docker exec -it layout-detection-troubleshoot /bin/bash`
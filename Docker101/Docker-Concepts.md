1. Port Mapping:
- Mapping/Expose the Port of a running container to outside Machine.

- Run Below command at Machine CLI.

> docker run -it -p Port_Number(Outside Machine):Port_Number(Container) Img_Name

eg. docker run -it -p 9000:9000 Img_Name

2. Environment Variables:
Use to set the parameters to Docker App & can be pass like key-value pair.

> docker run -it - PortC:PortVM -e key=value Img_Name

eg. docker run -it -p 1025:1025 -e key=value Img_Name


3. Dockerization of An App:
- Require a file called "Dockerfile" with configuration like Base Image, Dependencies, Libraries etc.

- 
FROM (To run in a Image)
RUN (To execute the commands)
COPY (To copy application code etc)
ENTRYPOINT (Execute Parameters within it,Whenever the Image get executed)







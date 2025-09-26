1. Port Mapping:
- Mapping/Expose the Port of a running container to outside Machine.

- Run Below command at Machine CLI.

> docker run -it -p Port_Number(Outside Machine):Port_Number(Container) Img_Name

eg. docker run -it -p 9000:9000 Img_Name

2. Environment Variables:
Use to set the parameters to Docker App.

eg. docker run -it - PortC:PortVM -e key=value Img_Name

3. 


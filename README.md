# Docker Container for Google BigTable emulator

The gcloud suite has an emulator for Google BigTable, which is great for testing locally how to run code against their APIs. 

However, it is not very useful if you want to run in a containerized environment, and want to test how the whole thing behaves. Hence this container. 

# How to use

```
$ docker pull lucasamorim/bigtable
$ docker run -it --name bitable-emulator -p 8621:8621 lucasamorim/bigtable
```

Now you need to run the equivalent of the ```$(gcloud beta emulators bigtable env-init)``` command

```
$ export BIGTABLE_EMULATOR_HOST=localhost:8621
```

Now you can use the standard APIs such as [gcloud-python](https://github.com/googlecloudplatform/gcloud-python) to interact with it. 

# ENV VARIABLES / TWEAKS

## Port

You can also change the port where the emulator runs by editing the HOST_PORT environment variable. 

## Logs

You can check the emulator logs with `docker logs`





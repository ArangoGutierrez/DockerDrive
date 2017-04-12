# A Linux Container implementation of the grive client

## Singularity Drive
A Singularity imlementation for the Google Drive Client

### Usage
Pealse refer to http://yourcmc.ru/wiki/Grive2#Installation

For a first time Drive sync
```bash
$ sudo singularity create /some/path/grive.img 
```
and

```bash
$ sudo singularity bootstrap /some/path/grive.img grive.def
```
In your host 
```bash
$ mkdir /home/MyGoogleDriveFoldeName
```
```bash
$ cd /home/MyGoogleDriveFoldeName
```
```bash
$ singularity exec /some/path/grive.img grive -a
```

After this, for Sync only
```bash
$ cd /home/MyGoogleDriveFoldeName
```
```bash
$ singularity exec /some/path/grive.img grive
```
## Docker Drive
A Docker imlementation for the Google Drive Client

### Usage
Pealse refer to http://yourcmc.ru/wiki/Grive2#Installation

For a first time Drive sync
```bash
$ docker pull ashael/dockerdrive 
```
or 
```bash
$docker build Dockerfile (after git clone)
```
```bash
$ mkdir /home/MyGoogleDriveFoldeName
$ cd /home/MyGoogleDriveFoldeName
$ docker run -it -v $PWD:/home/grive -w /home/grive grive
```

Then inside the Container
```bash
$ grive -a
```

After this, for Sync only
```bash
$ docker run --rm -v $PWD:/home/grive -w /home/grive --name "Gdrive" grive grive
```

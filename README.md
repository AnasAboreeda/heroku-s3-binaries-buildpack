# Heroku S3 Binaries Buildpack

### This is a Heroku Buildpack that can download binaries from private Amazon S3-buckets.
### It will create a folder called *plugins* in your root directory and download binaries inside it.
### If your binary's extension is .tar.gz it will uncompress it and put the result in the same file.


## Usage
  - In your project root directory create a file and call it `.plugins` and put inside it all binaries you want to download from your bucket (one at each line)
  
```shell
    > binary1.exe
    > binary2.tar.gz
    > binary3.dll
```
  
  - In your heroku toolbelt client 

```shell
    > $ heroku config:add AWS_KEY_ID=xxxxxxxxxxxxxxxxxxxxxxx
    > $ heroku config:add AWS_SECRET_KEY=xxxxxxxxxxxxxxxxxxxxxxx
    > $ heroku config:add AWS_REGION_NAME=xxxxxxxxxxxxxxxxxxxxxxx
    > $ heroku config:add AWS_BUCKET_NAME=xxxxxxxxxxxxxxxxxxxxxxx
```

  - In most cases you'll use this buildpack in conjunction with other buildpacks using [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi):
  

    $ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
    

  - In this case, you will create a file called `.buildpacks` and add this line to it together with all your buildpacks
  

    https://github.com/AnasFullStack/heroku-s3-binaries-buildpack.git

### Licence

MIT license


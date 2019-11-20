# example-sidecar-buildpack

To use this repo on a cloudfoundry instance simply zip it up and provide it to as a supply buildpack to a `cf push`
Ex:

1) Zip it up
```
# from the root of this repo
zip -r my-bp-name.zip .
```
2) upload the buildpack to cloudfoundry
```
cf create-buildpack <uploaded-buildpack-name> my-bp-name.zip <index>
```
3) push an app
```
# note the buildpack created above cannot be the final buildpack
cf push my-app -b <uploaded-buildpack-name> -b <final-buildpack>  
```


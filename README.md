# NGINX cache images and free PURGE method

## Usage
1. Try to get image form `/images` folder with GET request 2 times. You can see status `MISS and HIT` in nginx logs to track cached file 
2. Use `PURGE` method to delete single file cache `example: curl -X PURGE http://localhost:4510/cat.jpg` 

We use this package to enable purge functionality via Lua - `https://github.com/magiclen/nginx-cache-purge`
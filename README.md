# Hentai@Home with vnstat on Docker

## Support platforms:

	linux/amd64
	linux/arm64
	linux/arm
	linux/ppc64le


## Deploy

Replace `/YOUR/HATH/DATA` `/YOUR/HATH/DL` `/YOUR/HATH/VNSTAT` `YOUR_CLIENT_KEY` `YOUR_PORT` with yours.

### The format of `YOUR_CLIENT_KEY`

You can find your `Client ID#` and `Client Key` [here](https://e-hentai.org/hentaiathome.php)

`"$Client ID"-"$Client Key"` like this: `123456-ABCDEFGHIJKLMN1234OP`

### About `YOUR_PORT`

https://ehwiki.org/wiki/Technical_Issues#Ports 

## Run command below:
- Pull image  
  ```
  docker pull ghcr.io/sakuyamaij/hathv:latest
  ```
  中国大陆用户可使用[Docker Proxy](https://dockerproxy.com/)镜像加速

- Run it  
  ```
  docker run -d --name hath -p YOUR_PORT:YOUR_PORT -v /YOUR/HATH/DATA:/hath/data -v /YOUR/HATH/DL:/hath/download -v /YOUR/HATH/VNSTAT:/var/lib/vnstat -e HatH_KEY=YOUR_CLIENT_KEY ghcr.io/sakuyamaij/hathv
  ```

- Check vnstat statistics  
  ```
  docker exec -it hath vnstat -d
  ```

### About `Port:`
	(Container Port) and (Host Port) should be identical, 
	or you could just switch to (Advanced View), and set (Network Type) to (Host).

## Bing Wallpaper API

A RESTful API to fetch daily wallpaper from Bing.com

## Usage

### API 
* API Address: [https://bing.biturl.top](https://bing.biturl.top/)
* Method: `HTTP GET`

### Parameters

* `resolution` The resolution of wallpaper image. `1920` is the default value, you can also use `1366` and `3840`(4K resolution).
* `format` The response format, can be `json` or `image`. __If response format is set as `image`, you will be redirected to the wallpaper image directly__.
* `index` The index of wallpaper, starts from 0.
* `mkt` The region parameter, default is `zh-CN`, you can also use `en-US`, `ja-JP`, `en-AU`, `en-UK`, `de-DE`, `en-NZ`, `en-CA`.

### Example

* Request

```text
https://bing.biturl.top/?resolution=1920&format=json&index=0&mkt=zh-CN
```

* Response

```json
{
  "start_date": "20181118",
  "end_date": "20181119",
  "url": "https://www.bing.com/az/hprichbg/rb/NarrowsZion_ZH-CN9686302838_1920x1080.jpg",
  "copyright": "锡安国家公园内的维尔京河，美国犹他州 (© Justinreznick/Getty Images)",
  "copyright_link": "http://www.bing.com/search?q=%E9%94%A1%E5%AE%89%E5%9B%BD%E5%AE%B6%E5%85%AC%E5%9B%AD\\u0026form=hpcapt\\u0026mkt=zh-cn"
}
```

### CSS background image

You can also use this API to set CSS background image:

```text
background-image: url(https://bing.biturl.top/?resolution=1920&format=image&index=0&mkt=zh-CN);
height: 100%;
background-position: center;
background-repeat: no-repeat;
background-image: url("img_girl.jpg");
background-size: cover;
```

__Demo__  

[https://biturl.top](https://biturl.top)

![https://github.com/TimothyYe/biturl/blob/master/screenshots/1.jpg?raw=true](https://github.com/TimothyYe/biturl/blob/master/screenshots/1.jpg?raw=true)

## Run with docker

Get the code and build docker image:

```bash
git clone https://github.com/TimothyYe/bing-wallpaper.git
make release
```

Start the container with the image name & tag (YYYYMMDD), for example:

```bash
docker run -d --name=bing-wallpaper --restart=always -p 9000:9000 timothyye/bing:latest
```

## For development

### Build it
```bash
git clone https://github.com/TimothyYe/bing-wallpaper.git
make build
```

### Run it

```bash
bw/bw run
```

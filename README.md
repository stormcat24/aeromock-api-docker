aeromock-api-docker
===================

# Aeromock in Docker

[Aeromock](https://github.com/CyberAgent/aeromock) is Lightweight mock web server on JVM. This docker image was made for starting up Aeromock quickly.

# Usage
You will only have to prepare data file directory for API reponse. Data file directory should include json format file or yaml format file.

## Example
Firstly, create data file directory (e.g. /path-to-path/api).
Then create data file (e.g. /path-to-path/api/test.json'), as follows.

```JSON
{
  "result": true
}
```

## Run
Run with binding local data file directory. Bind `/path-to-path/api` (Host) to `/project/api` (in container).

Listening port of Aeromock is 3183. Do port mapping 3183(Optional) to 3183.

```
$ docker run -t -i -p 3183:3183 -v /path-to-path/api:/project/api stormcat24/aeromock-api
```

## Request
Please access `http://localhost:3183/test` ! Server will respond json response.

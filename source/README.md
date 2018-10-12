> widdershins swagger.yaml index.html.md

> swagger-to-slate swagger.yaml index.html.md

> bundle exec middleman build

> bundle exec middleman server

> go to localhost:4567  

# This project build three different version of our documentation all from the swagger.yaml file.

## For widdershins documentation: navigate to /SLATE_BASE/source/ and run: https://github.com/Mermade/widdershins
$ widdershins swagger.yaml index.html.md
The navigate to /SLATE_SKIN/ and run:
$ grunt localBuild:GS
$ grunt server
These steps basically rebuild to index.html.md file, then creates the build files in the /SLATE_BASE/build/ folder, then starts a local server:
You can now navigate to localhost:4567

## For swagger-to-slate documentation: navigate to /SLATE_BASE/source/ and run: https://www.npmjs.com/package/swagger-to-slate
$ swagger-to-slate swagger.yaml index.html.md
The navigate to /SLATE_SKIN/ and run:
$ grunt localBuild:GS
$ grunt server
These steps basically rebuild to index.html.md file, then creates the build files in the /SLATE_BASE/build/ folder, then starts a local server:
You can now navigate to localhost:4567

## For Redoc: https://github.com/Rebilly/ReDoc

List of available languages https://github.com/github/linguist/blob/master/lib/linguist/popular.yml
list of detailed vendor extensions: https://github.com/Rebilly/ReDoc/blob/master/docs/redoc-vendor-extensions.md#x-traitTag

### CDN
Simply get the url of your smagger file and insert it into the "url" field inside the indesx_redoc.html file, then load the file in a browser:

There is much more customization to do in redoc so, more documentation to come.

### CLI

navigate to /SLATE_BASE/source and run: 
$ redoc-cli serve swagger.yaml
open localhost http://127.0.0.1:8080

### bundle

To create a zero dependency html file for redoc. run:
$ redoc-cli bundle swagger.yaml 



This image is built from `ruby:2.1`, with `node`, `grunt` and `bower` added.
The purpose of this image is to build front-end codes on server without installing the whole dev environments such `node`, `grunt` and `bower`.

### Usage
after `cd` to your project root: `$ cd path/to/project`

- to do `npm install`: 
```
docker run -it --rm \
-v $(pwd):/app \
-v $(pwd)/node_modules:/app/node_modules \
-w /app \
yeoman-builder:latest \
npm install
```

- to do `bower install`:
 ```
docker run -it --rm \
-v $(pwd):/app \ 
-v $(pwd)/bower_components:/app/bower_components \
-w /app yeoman-builder:latest \
bower --allow-root --config.interactive=false install
```

- to do `grunt build`:
```
docker run -it --rm \
-v $(pwd):/app \ 
-v $(pwd)/node_modules:/app/node_modules \
-v $(pwd)/bower_components:/app/bower_components \
-w /app yeoman-builder:latest \
bower --allow-root --config.interactive=false install
```

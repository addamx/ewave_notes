# grunt / gulp scripts
## Magento grunt script
1. install package.json
2. create `grunt-config.json` and `dev/tools/grunt/configs/local-themes.js`;
3. create theme config in local-themes.js
**commands:**
- `grunt exec:magento` (run if any file created/renamed, it will clean pub/static, and create symlink for less files)
- `grunt less:magento`
- `grunt watch:magento`

## gulp script (gulpfile.js)
```
"gulp": "3.9.1",
"gulp-cssmin": "^0.2.0",
"gulp-if": "^2.0.2",
"gulp-less": "^4.0.1",
"gulp-livereload": "^4.0.1",
"gulp-sourcemaps": "^2.6.5",
```
**commands:**
- `gulp less --magento --map`
- `gulp watch --magento --map --live`

## babel, svg, base64
1 . install packages
```
"babel-plugin-add-module-exports": "^0.2.1",
"babel-preset-es2015": "^6.24.1",
"babel-preset-stage-0": "^6.24.1",
"escape-string-regexp": "^2.0.0",
"grunt-babel": "7",
"grunt-contrib-uglify": "^4.0.1",
"grunt-legacy-util": "^1.1.1",
"grunt-svgmin": "^6.0.0",
"grunt-svgstore": "^2.0.0",
"grunt-writefile": "^0.1.4",
```
2 . create/modfy config/task file:
PATH: dev/tools/grunt/config/
Files: babel.js, clean.js, path.js, svgmin.js, svgstore.js, svgtobase64.js, uglify.js, writefile.js
**command:**
- `grunt babel` (compile js from es6 to es5)
- `grunt svg` (svg sprite, svg base64 variable)

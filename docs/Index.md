# SamsonPHP Resource module documentation
All assets management are performed automatically 
External assets types that needed preprocessing like ```LESS``` are handled via [SamsonPHP/event](https://github.com/SamsonPHP/event)
for examples please see [SamsonPHP/less module](https://github.com/SamsonPHP/less).

## Module logic
On module initialization stage all modules paths are scanned for assets of supported types:
 * ```css```
 * ```less```
 * ```sass```
 * ```scss```
 * ```js```
 * ```ts```
 * ```coffee```
 
And being processed and stored in module cache folder in project web root accordingly to original location.
On template rendering stage all gathered assets are injected into template. 

## CSS urls rewriting
Module is bundeled with [CSS management class](https://github.com/SamsonPHP/resource/blob/master/src/CSS.php) which
rewrites all ```url(path/to/asset.jpg)``` through internal optimized controller route ```/resourcer/?p=/path/to/asset```. 
This paths should be specified relatively to project root.

## HTML template CSS & JS injection
Module automatically injects all gathered ```css``` and ```js``` resources in current template.
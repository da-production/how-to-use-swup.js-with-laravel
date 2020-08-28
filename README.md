# how-to-use-swup.js-with-laravel

First install swup.js by flowwing the swup instruction
### 1-Installtion:
```
$run: npm install swup
```
$run: npm install

### 2-import swup to your project:
add the following code to your resources/js/app.js
```
import Swup from 'swup';
window.swup = new Swup(); 
```
than make sure you are importing the app.js in your layout

### 3- basic use:
if you have a new script to execute:
wrappe your code with function named as like you want for exemple:
```
function init(){
  your code
}
swup.on('contentReplaced', init);

than if you want to import new css rule or new scripts juste created inside init with javascript exemple:
function init(){
  // code to import nes css
  var newstyle = function (param) {
      var headID = document.getElementsByTagName('head')[0];
      var link = document.createElement('link');
      link.type = 'text/css';
      link.rel = 'stylesheet';
      headID.appendChild(link);
      link.href = param;
  };
  newstyle("{{ asset('style.css') }}");
}
```

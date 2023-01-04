---
marp: true
theme: gaia
paginate: true
orientation: portrait
size: 16:9




---
# Usage of SweetAlert2 with PHP

[]: # (https://sweetalert2.github.io/)


## Requirements
- PHP >= 7.0
- sweetalert2 >= 7.0 (cdn ou npm)
- Optional: jQuery >= 1.8.0 (cdn ou npm)
---
# Step 1: 
Import sweetalert2 into your project
### CDN
```html
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@7"></script>
```
### NPM
```bash
npm install sweetalert2
```
```html
<script src="node_modules/sweetalert2/dist/sweetalert2.all.min.js"></script>
```
---
# Step 2: 
1. Create a PHP file which will be called by the JavaScript and contains the template of the alert
2. Create a JavaScript file which will be called by the HTML and contains the code to call the PHP file
```js
function modal(){
    Swal.fire({
  template: '#my-template'
})
} 
modal();
```
---
```html
<!-- template.php -->
<template id="my-template">
  <swal-title>
    Save changes to "Untitled 1" before closing?
  </swal-title>
  <swal-icon type="warning" color="red"></swal-icon>
  <swal-button type="confirm">
    Save As
  </swal-button>
  <swal-button type="cancel">
    Cancel
  </swal-button>
  <swal-button type="deny">
    Close without Saving
  </swal-button>
  <swal-param name="allowEscapeKey" value="false" />
  <swal-param
    name="customClass"
    value='{ "popup": "my-popup" }' />
  <swal-function-param
    name="didOpen"
    value="popup => console.log(popup)" />
</template>
```
---
# Step 3:
include the template in your php file

```php
// index.php
include 'template.php';
```

include the JavaScript file in your php file

```php
// index.php
<script src="js/modal.js"></script>
```










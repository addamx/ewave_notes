# Layout
## infinity/dev
1. install `infinity/dev`
2. enable template hint
```
php bin/magento config:set dev/debug/template_hints_storefront 1
php bin/magento config:set dev/debug/template_hints_blocks 1
```
functions of `infinity/dev`
- show template path hint in html comment tag
- show container/block name if add url query `?debug`
- download whole layout file if add url query `?debug=layout`

# Js
## requirejs config
- requirejs: `require.s.contexts._.config`

## customdata
```js
cd = require('Magento_Customer/js/customer-data')
cd.set('messages',{messages:[
{type: "info", text:"info: Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam lectus justo, vulputate eget mollis sed, tempor sed magna. Praesent dapibus. Fusce suscipit libero eget elit. Cum sociis natoque "},
{type: "warning", text:"warning: Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam lectus justo, vulputate eget mollis sed, tempor sed magna. Praesent dapibus. Fusce suscipit libero eget elit. Cum sociis natoque "},
{type: "error", text:"error: Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam lectus justo, vulputate eget mollis sed, tempor sed magna. Praesent dapibus. Fusce suscipit libero eget elit. Cum sociis natoque "},
{type: "success", text:"success: Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam lectus justo, vulputate eget mollis sed, tempor sed magna. Praesent dapibus. Fusce suscipit libero eget elit. Cum sociis natoque "},
{type: "notice", text:"notice: Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam lectus justo, vulputate eget mollis sed, tempor sed magna. Praesent dapibus. Fusce suscipit libero eget elit. Cum sociis natoque "}
]})
```

# Less
- chrome liverealod plugin + grunt/gulp script


# PHP
PHP-debug
# Developer enviroment

```
# deploy
php bin/magento deploy:mode:set developer

# misc
## disable js/css/html merge/bundle/minification;
## extend session lifetime
php bin/magento config:set dev/template/minify_html 0
php bin/magento config:set dev/debug/debug_logging 1
php bin/magento config:set dev/js/merge_files 0
php bin/magento config:set dev/js/enable_js_bundling 0
php bin/magento config:set dev/js/minify_files 0
php bin/magento config:set dev/css/merge_css_files 0
php bin/magento config:set dev/css/minify_files 0
php bin/magento config:set dev/static/sign 0
php bin/magento config:set admin/security/session_lifetime 31536000
php bin/magento config:set admin/security/password_lifetime ''

php bin/magento config:set catalog/recently_products/recently_viewed_lifetime 31536000
php bin/magento config:set catalog/recently_products/recently_compared_lifetime 31536000

# if infinity/dev is enable
php bin/magento config:set dev/debug/template_hints_storefront 1
php bin/magento config:set dev/debug/template_hints_blocks 1

# Cache
php bin/magento cache:disable block_html
php bin/magento cache:disable full_page
php bin/magento cache:disable layout
php bin/magento cache:disable translate

# If migrate a database from other site

## reset base_url
php bin/magento config:set web/unsecure/base_url http://motic.local/
php bin/magento config:set web/secure/base_url https://motic.local/

## disable the redirect from http to https
## enable insecure url(http://...) for adminhtml and webapi
php bin/magento config:set security/access/enabled 0
php bin/magento config:set web/secure/use_in_adminhtml 0
php bin/magento config:set webapi/webapisecurity/allow_insecure 1

## reset CDN configurations
php bin/magento config:set web/secure/base_static_url ''
php bin/magento config:set web/secure/base_media_url ''
```



# IDE

## vscode
- install **stylelint**
    - 1. install stylelint extension;
    - 2. install plugin(if any)  in local project (eg `npm install -D stylelint-config-standard`);
    - 3. add related settings (refer to `project settings`)
- install **eslint**
    - 1. install eslint extension;
    - 2. install eslint and plugins(if any) in local project (eg `npm install -D eslint eslint-config-standard`);
    - 3. add related settings (refer to `project settings`)
- Project settings: `./.vscode/settings.json`
```json
{
     // stylelint
     "css.validate": false,
     "less.validate": false,
     "scss.validate": false,
     // eslint
    "javascript.validate.enable": false,
    "editor.formatOnPaste":true,
    "editor.formatOnSave":false,
    "eslint.autoFixOnSave": false
}
```
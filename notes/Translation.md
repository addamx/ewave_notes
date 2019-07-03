# Translation of php
## The order of dictionary
- Db > Theme > Package > Module
```php
# vendor/magento/framework/Translate.php
$this->_loadModuleTranslation();
$this->_loadPackTranslation();
$this->_loadThemeTranslation();
$this->_loadDbTranslation();
```


# Translation of js

## Where is js-translation comes from?
1. ajax request for js-translation dictionary: `vendor/magento/module-translation/view/base/templates/translate.phtml`;
    1. That's why somtimes a translation is missing at cold start, because the target script runs before the ready of translation.
2. check file-version `lib/web/mage/translate-init.js`; (version by `sha1_file($translationFile)` $translationFile is the absolute path of js-translation.json, so the version will never change unless you change its path);
3. fetch the content of js-translaton.json, save them in js variable `lib/web/mage/translate.js`;
4. add cache in localStorage;

## How is js-translation.json generated?
1. collect files matched type: `.html/.js` `vendor/magento/module-translation/Model/Js/DataProvider.php`;
    1. the html tpl under **web/template** would be collected. However, if the html tpl under **web/templates**(there's additional "s"), it should only be included in a module folder, otherwise, it will be ignored if locals at a theme folder. 
2. search word matched patterns declared in `module-translation\etc\di.xml`, eg. `i18n: "str"` / `translate="str"` / `$.mage.__("str")`/ `jQuery.mage.__("str")` / `$t("str")`;
    1. **According to above process, you shouldn't use a variable in above patterns, eg. `$.mage.__($str)`(!wrong), `$.mage.__('Hello' + ' world')`(!wrong)**


## How to clear js-translation cache(dev & prod)?
1. clear cache & delete js-translation.json: `php bin/magento cache:flush translate && find pub/static/frontend -name 'js-translation.json' -delete`
2. clear locastorage in browser: 
```js
localStorage.removeItem('mage-translation-file-version');
```


# Translation in cms template
```
{{trans "Welcome to %store_name." store_name=$store.getFrontendName()|raw}}
```

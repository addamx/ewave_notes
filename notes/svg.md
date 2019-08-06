# SVG
`grunt svg`

## svg sprite
```
web\svg\src\sprite\*.svg
||
V
web\svg\sprite.svg
```


- sprite-demo.html
http://magento.local/static/frontend/Ewave/magento/en_US/svg/sprite-demo.html
- sprite svg has cache in localstorage;
- You need to change the value of svg_revision in layout.xml before running git commit;
```xml
//Magento_Theme\layout\default.xml

<referenceBlock name="svg_sprite">
    <arguments>
        <argument name="svg_revision" xsi:type="string">0.0.1</argument>
    </arguments>
</referenceBlock>
```

## base64
`grunt svg`
```
web\svg\src\base64\*.svg
||
V
web\css\source\variables-new\generated\_base64.less
```


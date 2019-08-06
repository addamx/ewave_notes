# Disable component
- We can't remove a component unless modifying `LayoutPreprocess.php`
- dsiable a component by change its config:
```xml
<item name="config" xsi:type="array">
    <item name="componentDisabled" xsi:type="boolean">true</item>
</item
```
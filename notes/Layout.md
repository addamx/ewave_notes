# Add body class
```xml
<body>
    <attribute name="class" value="page-with-filter"/>
</body>
```

# modify the title of page / head
```xml
<referenceBlock name="page.main.title">
    <!-- modify page title -->
    <action method="setPageTitle">
        <argument translate="true" name="title" xsi:type="string">Reset password</argument>
    </action>
    <!-- modify head title -->
    <arguments>
        <argument name="title" xsi:type="string" translate="true">Forgot Your Password</argument>
    </arguments>  
</referenceBlock>
```

# Add static text
```xml
<block class="Magento\Framework\View\Element\Template" name="checkout.cart.summary.title" before="-" template="Magento_Theme::text.phtml">
    <arguments>
        <argument translate="true" name="text" xsi:type="string">Summary</argument>
        <argument name="tag" xsi:type="string">strong</argument>
        <argument name="css_class" xsi:type="string">summary title</argument>
    </arguments>
</block>
```

# change template file
```xml
<referenceBlock name="sample_name">
    <action method="setTemplate">
        <argument name="template" xsi:type="string">Magento_CatalogSearch::product/list/toolbar.phtml</argument>
    </action>
</referenceBlock>
```

# Add cms block
<block class="Magento\Cms\Block\Block" name="footer.social.block">
    <arguments>
        <argument name="block_id" xsi:type="string">footer-social</argument>
    </arguments>
</block>

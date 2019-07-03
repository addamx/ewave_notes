# API
```php
# modify data
$block->setData(['key1' => $val1, ...]);   // (careful!)override the whole data
$block->addData(['key1' => $val1, ...]);  // just add
$block->setData($key, $val); // add or rewite a value

/*-------------------- Get name or object -----------------------*/

# get name in block
$block->getNameInLayout();

# get child name in block
$childName = $block->getLayout()->getChildName($block->getNameInLayout(), $alias);

# get Children Names
$block->getChildNames();
// or
$block->getLayout()->getChildNames($BlockName);

# get Block(object)
$block = $block->getLayout()->getBlock($BlockName);

# get ChildBlock(object)
$block->getChildBlock($childName);

# get Children Blocks(object[])
$block->getChildBlocks($block->getNameInLayout());

/*-------------------- Render -----------------------*/

# create Block
$block->getLayout()->createBlock('Magento\Catalog\Block\Category\View');
$block->getLayout()->getBlockSingleton('Magento\Catalog\Block\Category\View'); // The block has been created in same layout, here it just reuse same instance

# render CMS block
$block->getLayout()->createBlock('Magento\Cms\Block\Block')->setBlockId(CMS_BLOCK_ID)->toHtml();

# render child Block
echo $left->getChildHtml($childName) 

# render Children Block
$block->getChildHtml();
// or
foreach ($block->getChildNames() as $childName) {
    echo $block->getLayout()->renderElement($childName, false);
}

```

# Most common Block
- `Magento\Catalog\Block\Category\View`
```php
# category's cms content
$category_text = $categoryView->getCmsBlockHtml();
```

- ``
```php
$this->_urlBuilder->getBaseUrl(['_type' => \Magento\Framework\UrlInterface::URL_TYPE_MEDIA]);
$this->storeManager->getStore()->getBaseUrl(UrlInterface::URL_TYPE_MEDIA);
```

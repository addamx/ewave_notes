# Base 

# Installation
```
php bin/magento setup:install --base-url=http://magento.local/ \
--db-host=db --db-name=magento --db-user=root --db-password=root \
--admin-firstname=Magento --admin-lastname=User --admin-email=user@example.com \
--admin-user=admin --admin-password=admin123! --language=en_US \
--currency=USD --timezone=America/Chicago --use-rewrites=1
```

# Create User
```
php bin/magento admin:user:create --admin-user='addams' --admin-password='admin123!' --admin-email='info@domain.com' --admin-firstname='addams' --admin-lastname='xu
```

# cache
```
php bin/magento cache:flush
php bin/magento c:f
php bin/magento cache:disable layout
php bin/magento cache:disable translate
```

# Config
```
php bin/magento config:show
php bin/magento config:show [path]
php bin/magento config:set [path] [value]

php bin/magento config:set web/unsecure/base_url http://magento.local/
php bin/magento config:set web/secure/base_url https://magento.local/
```

# module
```
php bin/magento setup:upgrade
php bin/magento module:enable
php bin/magento module:disable
php bin/magento module:status

## modify the version of module in mysql
update setup_module set schema_version='1.1.0', data_version='1.1.0' where module="Ewave_AbstractEntityData";
```

# deploy
```
## production mode
php bin/magento setup:static-content:deploy (default language)
php bin/magento setup:static-content:deploy [langage code]
php bin/magento setup:static-content:deploy zh_Hant_HK

## devloper mode
rm -rf ./pub/static/frontend/*
rm -rf ./var/view_preprocessed/*
php bin/magento setup:static-content:deploy -f
php bin/magento setup:static-content:deploy -f --area frontend --theme Ewave/durban --language en_US
```



# reindex
```
php bin/magento indexer:reindex
```

# Ewave module
```
# cms_upgrade
php bin/magento ewave:cms_upgrade


## update cms_version
update ewave_cms_upgrade_data_version set data_version="0.0.3" where id="1";
select * from ewave_cms_upgrade_installed_files;
delete from ewave_cms_upgrade_installed_files where id>2;
```


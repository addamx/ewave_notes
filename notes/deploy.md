#=Deploy
- Less compile: 1. server compile; 2. less.js compile; 3. grunt task

## developer mode
- enable:`php bin/magento deploy:mode:set developer`
(2) features
- js files generates symlinks in pub/static
`js -- soft link --> pub/static/**/*.js`
- less files will be compiled to css in pub/static (server compile) 
`less -- view_preprocessed(cache) -- (server render) --> pub/static/**/*.css`

## product mode
- deploy static files
`php bin/magento setup:static-content`
- force to deploy static files even on developer mode:
`php bin/magento setup:static-content:deploy -f`

## other
- If deploy command fail due to less error in dev site,  you need to run `php bin/magento setup:static-content:deploy -f` in you local env to check if any bug by server compile.
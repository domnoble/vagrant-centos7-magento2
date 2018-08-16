# vagrant-centos7-magento2

Download magento2 from magento.com and create html directory

`mkdir html`

to install dependencies and run vagrant vm run the following two commands:

`vagrant plugin install vagrant-vbguest`

`vagrant up`

As a quick fix for the installer failing you can set app/etc/env.php, (will still hang on 66% when installing SampleData successfully):
```
array (
  'save' => 'files',
  'save_path' => '/tmp',
),
```

to remove SampleData use the folling 3 commands :

'vagrant ssh'

'cd /srv/html'

'php bin/magento sampledata:remove'

you may also need to run:

`php bin/magento setup:static-content:deploy`

`php bin/magento indexer:reindex`
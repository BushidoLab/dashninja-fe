dashninja-fe :
git clone
install static dependencies :
- bootstrap 3.3.6
- font-awesome 4.6.3
- jquery


configure nginx and php-fpm for PHP /api/
copy libs/config.inc.php.sample to libs/config.inc.php and set up the dashninja-fe


dashninja-be / cmd :
- install easy-rsa (or create/use your existing CA)
- you will need the CA, a server key/cert (for the dashninja-be API) and at least one client key/cert (for dashninja-ctl)
- setup your server with the CA to verify clients certs and server key
- PHP FPM pointing to dashninja-be api/index.php folder
- copy libs/config.inc.php.sample to libs/config.inc.php and set up the dashninja-be
- once set up, use curl to fill correctly the cmd_hub table, go the cert/keys folder :
curl -vvvvv --tlsv1.2 --cacert ./ca.crt --cert ./test-client.crt --key ./test-client.key https://test.cmd.dashninja.pl


dashninja-ctl :
- copy cp dmn.config.inc.php.sample dmn.config.inc.php
- configure dmn.config.inc.php to your liking
- git clone EasyDash-PHP in the main folder:
https://github.com/elbereth/EasyDash-PHP

adding nodes :
You need at least 2 :
- a masternode (no need to be a masternode, can be a normal node)
- a p2pool (no need for p2pool, but will need txindex=1 and will be used for blocks)
This needs to be done manually.
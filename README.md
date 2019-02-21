# nanobox-phpmyadmin

Use PhpMyAdmin with Nanobox

## Installation

Clone this project into a new empty directory.

Run this to add a local DNS: 

```bash
nanobox dns add local phpmyadmin.local
```
Run the container for the first time:

```bash
nanobox run 
```
And once in the container, execute the following instructions: 

```bash
cd /tmp
composer create-project phpmyadmin/phpmyadmin
shopt -s dotglob
cp -a phpmyadmin/* /app
cd /app
cp config.sample.inc.php config.inc.php
exit
```

## Usage

Edit the `config.inc.php` file: 

```php

/* Server parameters */
$cfg['Servers'][$i]['host'] = 'localhost'; //Replace 'lcoalhost' with the host you want to connect

```

and then run 
```bash 
nanobox run php-server
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Authors

* **Lenin Paulino** - *Initial work* - [leninpaulino](https://github.com/leninpaulino)

## Acknowledgments

* Inspiration: https://content.nanobox.io/using-phpmyadmin-to-manage-local-databases/


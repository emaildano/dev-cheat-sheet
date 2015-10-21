# Developer Cheat Sheet

## Premissions

#### NPM/ Node.js Premissions Errors (EACCES)
##### Set owner to current user
`sudo chown -R $(whoami) ~/.npm /usr/local/lib/node_modules`

## DNS

#### Map IP Address
`nslookup example.com`

#### Name Server Info
`host -t ns example.com`

#### Flush DNS

##### Yosemite v10.10.x
`dscacheutil -flushcache`

##### Mavericks v10.9.x
`dscacheutil -flushcache; sudo killall -HUP mDNSResponder`

##### Mountian Lion v10.8.x or Lion v10.7.x
`sudo killall -HUP mDNSResponder`

##### Snow Leopard v10.6.x or v10.5.x Leopard
`dscacheutil -flushcache`

## Zip

#### Compress

`zip -r archive_name.zip folder_to_compress`

#### Compress without _MACOSX

`zip -r -X archive_name.zip folder_to_compress`

#### Uncompress

`unzip archive_name.zip`

## Tar

#### Creating a Tar.gz Archive

`tar -zcvf example.tar.gz folder_to_compress`

> z = Zip the archive <br>
> c = Create new archive <br>
> v = Verbose, meaning show me the processes <br>
> f = file name to be created <br>

#### Un-tar to current directory

`tar -zxvf example.tar.gz`

#### Un-tar to a different directory

`tar -C /folder -zxvf example.tar.gz`

#### Uncompressing multiple tar.gz files from one directory to another

`for i in *.tar.gz; do tar xvzf $i -C ../folder; done`
> Destination folder must already exist

#### Create Tar.gz of all folders within current directory

`for dir in */; do   base=$(basename "$dir");   tar -czf "${base}.tar.gz" "$dir"; done`

## Linux Search and Replace

### Search and Replace with Sed

`find . -type f -print -exec sed -i 's/old/new/g' {} \;`

## Linux Disk Usage Info

#### Get size of each folder in current directory

`du -sh */`

#### Get size of specific folder

`du -sh example/`

#### Get size of specific file

`du -sh example.mp4`

## Rename

#### Renaming file extensions

`rename 's/.m4v$/.mp4/' *.m4v`
> Run to rename all `.m4v` extensions to `.mp4`

## Composer

#### Clear Composer cache
`rm -rf ~/.composer/cache`

#### Install Composer on Shared Hosting
##### 1and1
1. Make Composer Directory and Move There `mkdir ~/.composer && cd ~/.composer`
2. Download Composer `curl -sS https://getcomposer.org/installer | /usr/bin/php5.5-cli`
3. Create Alias to Run Composer `alias composer='/usr/bin/php5.5-cli ~/.composer/composer.phar'`
4. Enjoy! `composer` should now run from any directory

##### GoDaddy
1. Make Composer Directory and Move There `mkdir ~/.composer && cd ~/.composer`
2. Download Composer `php -r "readfile('https://getcomposer.org/installer');" | php5`
3. Add alias `echo "alias composer='php ~/.composer/composer.phar'" > ~/.bash_profile`
4. Load profile `source ~/.bash_profile`

## Creating Symbolic Links
`ln -s /path/to/original /path/to/symlink`

## Git

#### Clear Git Cache
- `git rm -r --cached .`
- `git add .`
- `git commit -m ".gitignore is now working"`

## Common MySQL Commands

#### Login as user with password
`mysql -u 'username' -p`

#### Create Database
`CREATE DATABASE 'databasename';`

#### Use Database
`USE DATABASE databasename';`

## Import Databse Dump to Existing Database
`mysql -u 'username' -p -h 'host' 'database' < 'path/to/database.sql'`

#### Show Current MySQL Info
STATUS;

#### Export Database
`mysqldump database_name > database_name.sql`

#### Export All DBs
`mysqldump --all-databases > all_dbs.sql`

## Apache

#### List Virtual Hosts
`httpd -S`

## AWS CLI

#### Move folder contents from ec2 to s3

`aws s3 cp folder s3://bucket/folder/ --recursive`

#### Move file from ec2 to s3

`aws s3 cp file.tar.gz s3://bucket/folder/` <-- note the forward slash

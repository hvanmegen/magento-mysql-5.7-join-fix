# magento-mysql-5.7-join-fix
This patch fixes an issue with Magento bizarre way of constructing queries to join all data required for category listings causing MySQL's table indexes to fail and queries to take 5 to 40 times longer than normal when using MySQL/MariaDB/Percona 5.6 and up.

# Is this just for Magento 1.9.x ?
I've only tested it on Magento 1.9.x. After installing this fix and flushing all your caches, your category pages (and other things that use category listings (think Megamenu or other stuff) will become really fast (again).

# Does Magento 2.x have this issue?
I'm pretty sure the problem still exists in Magento 2.x.. feel free to correct me if I'm wrong.

# How to use?
Either copy the contents of the src folder to your Magento installation folder or deploy this module with [modman](https://github.com/colinmollenhour/modman).

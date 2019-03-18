# Magento 1 fix for slow category pages or listings using MySQL 5.7

## magento-mysql-5.7-join-fix
This patch fixes an issue with Magento bizarre way of constructing queries to join all data required for category listings causing MySQL's table indexes to fail and queries to take 5 to 40 times longer than normal when using MySQL / MariaDB / Percona equivalent to MySQL 5.7 and up, compatible with Magento 1.x.

## How does it work?
This bugfix short-circuit's the query by checking if category_id IS NOT null in the first place, before going on to a like query where this category_id is used.

## Is this just for Magento 1.9.x ?
I've only tested it on Magento 1.9.x. After installing this fix and flushing all your caches, your category pages (and other things that use category listings (think Megamenu or other stuff) will become really fast (again).

## Are you telling me the bug still exists in 1.9.4.x ?!
Yes, as of Magento 1.9.4.x, this category_id short circuiting has not been included Magento's Core 'Url.php'.

## Does Magento 2.x have this issue?
I'm pretty sure the problem still exists in Magento 2.x if they build their queries the same way as in one, for which I have no reason to believe that they don't.. feel free to correct me if I'm wrong.

## How to use?
Either copy the contents of the src folder to your Magento installation folder or deploy this module with [modman](https://github.com/colinmollenhour/modman).

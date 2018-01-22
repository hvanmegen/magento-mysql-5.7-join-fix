# magento-mysql-5.7-join-fix
This patch fixes an issue with Magento bizarre way of constructing queries to join all data required for category listings causing MySQL's table indexes to fail and queries to take 5 to 40 times longer than normal.

# How to use?
Either copy the contents of the src folder to your Magento installation folder or deploy this module with modman.


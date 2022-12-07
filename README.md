# wp-rocket
**Level 2 Technical Assessment**
====================================================================================================
*1. The customer disabled WP Rocket’s automatic cache clearing system. They want you to provide them with a way to clear the following cache files at a specific time they select, e.g. when the site has the least traffic:*

- HTML
- Combined/minified CSS/JavaScript files

*Using WP Rocket’s existing functions:*

- Explain how they should implement the requirement to clear the cache at a specific time.
- Provide any piece of code necessary to perform the cache clearing task.

**Answer:**

Hello! Thanks so much for contacting us. I understand you'd like to clear only certain files in your cache, at a certain time. To do so manually, you can find a guide for that here:

https://docs.wp-rocket.me/article/133-manually-clear-wp-rocket-cache

If you want this to be done automatically, though, you will need to use a cron job. If you don't know what a cron job is, you can read more about this here:

https://docs.wp-rocket.me/article/1279-cron-and-wp-rocket

To clear your cache via a cron job, you can use this guide as a reference:

https://docs.wp-rocket.me/article/494-how-to-clear-cache-via-cron-job

You can find which specific files to delete here:

https://docs.wp-rocket.me/article/1135-when-does-wp-rocket-delete-which-files

====================================================================================================

*2. Your teammate sent your instructions and code to the customer.*
*They implemented them but the cache isn’t cleared.*

*Provide the steps that you’d follow to troubleshoot this, based on the solution you provided in A.*

*Assume that:*
*you have tested your code on your environment and it works fine and*
*the customer has provided you access to their site/server.*

**Answer:**
My process would be as follows:

1. Make sure the customer has a recent backup of their site available.
2. If they give me accesss to their site to test, create a semi-staging site with a plugin like Health Check & Troubleshooting.
3. If they don't have a staging site available or are unable to create a backup, I use UpdraftPlus to create a copy of the site to install locally.
4. If they are okay with me with testing it in their site, use a plugin like PHP Snippets so I don't have to mess directly with the files of the site.
5. Otherwise, use the copy I got from their site and test it on my local environment.
6. Check if the cron job was added correctly, in the correct place.
7. Use an uptime monitor to ping the site.
8. Otherwise, check if define( 'DISABLE_WP_CRON', true ); is available in the wp-config.php file.
9. Check that wp-cron.php exists and has the correct permissions.

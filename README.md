# Back End Web Assignment 3
## Kate, Olly and Shane
Repo for Back End Web Assignment 3

This git repo is in sync with dev.sockbrew.design.

If you push from your local to this git repo's main branch it will update the dev.sockbrew.design site automatically. (Danger - don't push your local database.)

The server is also in sync with Github. Any content you add to the server will be automatically added. The sync happens every five minutes, so if you need some files locally, wait five minutes and try pulling from the repo again.

Work on a different branch to main and open up PR's rather than pushing directly to the main branch.

## Running Locally - Each time
If you haven't done setup yet - go down to that first.
This looks like a lot but its just fairly broken down.
1. Make any changes to posts etc as required on the dev.sockbrew.design site.
2. When ready, login to the dev site admin.
3. Go to Tools > Migrate DB > Export Database
4. Under Replace for the URL input `http://localhost` (or whatever your MAMP stack is)
5. Under replace for `/var/www/html` insert the absolute path for where your MAMP Wordpress folder is (e.g. /Users/shane/Development/http)
6. Leave other settings the same and export the database.
7. On your local machine pull down the latest changes from Github.
8. Log into phpMyAdmin
9. Select the Wordpress database that corresponds to your Wordpress install. Create a new one if you don't have one.
10. Select the import tab and import the file you just exported (can still be zipped). Disable partial import.
11. Go to localhost and refresh (or finish setup if you haven't yet). The page should be working (yay!).

## Running Locally - Setup - Once Only
Each person has their own custom wp-config.php in the wordpress folder.
1. Pull this repo to your local machine. 
2. Either point your MAMP stack at the wordpress directory in this folder or copy the files where you need them (more difficult later).
3. Skip down to the run each time setup part below.
4. Copy the wp-config.php file at the root of this folder to the wordpress folder.
5. Update the wp-config.php file to point at your database under the MySQL settings.
6. Try and load the page (hopefully it works first time....)

## Troubleshooting

If your CSS is blank / aren't loading / redirecting to admin properly - in your wp-config.php set the following lines (near the bottom of the file) to:

```
define( 'WP_SITEURL', 'http://localhost:<your port e.g. 8080>/path/wordpress/folder/' );
define( 'WP_HOME', 'http://localhost:<your port e.g. 8080>/path/wordpress/folder/' );
```

If your permalinks are broken (i.e. main page works but children don't):
First, go to /wp-admin > Settings > Permalinks. Don't change anything and press save changes a few times. Go and check if the links are fixed.

If not - check you have a .htaccess file in your Web Root (wherever your MAMP folder is.) If not, you might need to copy the details on the permalink page into a .htaccess file.

On Linux with Apache you will need to set up mod_rewrites.



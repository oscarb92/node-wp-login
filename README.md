### IMPORTANT: 

Authentication is only done on the WP frontend, therefore the user will not have access to /wp-admin and any attempt to enter that directory will destroy the cookie and log off. 
<br>This is because WordPress creates a dynamic SALT for /wp-admin, it is not defined in wp-config.php and therefore the cookie from /wp-admin cannot be authenticated.

### CONFIG

The application must run on the same domain as Wordpress

#### SECRET KEYS
Add the secret keys found in <code>wp-config.php</code>
<pre>
	//DEFINE SALT WP
	const AUTH_KEY = 'WP CONFIG';
	const SECURE_AUTH_KEY = 'WP CONFIG';
	const LOGGED_IN_KEY = 'WP CONFIG';
	const AUTH_SALT = 'WP CONFIG';
	const SECURE_AUTH_SALT = 'WP CONFIG';
	const NONCE_KEY = 'WP CONFIG';
	const LOGGED_IN_SALT = 'WP CONFIG';
	const NONCE_SALT = 'WP CONFIG';
</pre>


#### DATABASE
Configure the database, this can be found in <code>wp-config.php</code>

<pre>
	const connection = mysql.createConnection({
	  host     : 'localhost',
	  user     : 'root',
	  password : '',
	  database : 'node_test',
	});
</pre>
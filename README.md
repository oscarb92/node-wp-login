### IMPORTANT: 

Authentication is only done on the WP frontend, therefore the user will not have access to /wp-admin and any attempt to enter that directory will destroy the cookie and log off. 
<br>This is because WordPress creates a dynamic SALT for /wp-admin, it is not defined in wp-config.php and therefore the cookie from /wp-admin cannot be authenticated.

### CONFIG

The application must run on the same domain as Wordpress.

#### PATH

Replace with the path where the app is running, if you are running it in the root, do not modify it.


Example 1: <code>http://localhost:8000/</code> or <code>http://localhost/</code>
<pre>
	const PATH_APP = '/';
</pre>

Example 2: <code>http://localhost/login:8000</code> or <code>http://localhost/login</code>
<pre>
	const PATH_APP = '/login/';
</pre>

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
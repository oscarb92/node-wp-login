### CONFIG

The application must run on the same domain as Wordpress

#### SECRET KEYS
Add the secret keys found in <code>wp-config.php</code>
<code>
	//DEFINE SALT WP
	const AUTH_KEY = 'WP CONFIG';
	const SECURE_AUTH_KEY = 'WP CONFIG';
	const LOGGED_IN_KEY = 'WP CONFIG';
	const AUTH_SALT = 'WP CONFIG';
	const SECURE_AUTH_SALT = 'WP CONFIG';
	const NONCE_KEY = 'WP CONFIG';
	const LOGGED_IN_SALT = 'WP CONFIG';
	const NONCE_SALT = 'WP CONFIG';
</code>


#### DATA BASE
Configure the database, this can be found in <code>wp-config.php</code>

<code>
	const connection = mysql.createConnection({
	  host     : 'localhost',
	  user     : 'root',
	  password : '',
	  database : 'node_test',
	});
</code>
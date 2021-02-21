### IMPORTANT: 

The application must be running on the same WordPress domain.

### CONFIG

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
	const DB_NAME = 'node_test';
	const table_prefix = 'wp_';

	const connection = mysql.createConnection({
	  host     : 'localhost',
	  user     : 'root',
	  password : '',
	  database : DB_NAME,
	});
</pre>

#### LOGIN LIMITER
counts and limits number of actions by key and protects from DDoS and brute force attacks at any scale.
* Counter of failed attempts <code>maxConsecutiveFailsByUsername</code>
<pre>

	const maxConsecutiveFailsByUsername = 5; //Limit login fails

	const opts = {
	  storeClient: connection,
	  dbName: DB_NAME,
	  tableName: table_prefix+'node_app_limiter_login', // all limiters store data in one table
	  points: maxConsecutiveFailsByUsername, // Number of points
	  duration: 60 * 5, // Store number for 5min since first fail
	  blockDuration: 60 * 15, // Block for 15 minutes
	};
</pre>
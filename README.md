# php-script-to-fetch-db-details



```
<?php
$servername = "localhost";
$username = "mysqlusername";
$password = "mysqluserpassword";
$dbname = "databasename";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

$sql = "SELECT * FROM <tablename>";
$result = $conn->query($sql);

if ($result->num_rows > 0) {
  // output data of each row
  while($row = $result->fetch_assoc()) {
    echo "firstName: " . $row["firstname"]. " - lastname: " . $row["Lastname"]. " - Age " . $row["age"]. "<br>";
  }
} else {
  echo "0 results";
}
$conn->close();
?>
```

# login.php2
<?php
  $con = mysqli_collect ("databas", "sql", "password", "user");
  
  $userame = $_POST("username");
  $password = $_POST("password");
  
  $statement = mysqli_prepare($con, "SELECT * FROM user WHERE username = ? AND password =?");
  msqli_stmt_bind_param($statement, "ss", $username, $password);
  msqli_stmt_execute(statement);
  
  msqli_stmt_store_result($statement);
  msqli_stmt_bind_result($statement, $userID, $name, $age, $username, $password);
  
  $response = array();
  $response["success"] = false;
  
  while(msqli_stmt_fetch($statement)){
    $response["success"] = true;
    $response["name"] = name;
    $response["age"] = age;
    $response["username"] = username;
    $response["password"] = password;
    
  echo json_encode($response);
?>
    
    

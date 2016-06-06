# login.php2
<?php
  $con = mysqli_collect ("a5676971_rateAPP", "a5676971_chay21", "music7EEE", "mysql8.000webhost.com");
  
  $userame = $_POST("username");
  $password = $_POST("password");
  
  $statement = mysqli_prepare($con, "SELECT * FROM user WHERE username = ? AND password =?");
  msqli_stmt_bind_param($statement, "ss", $username, $password);
  msqli_stmt_execute(statement);
  
  msqli_stmt_store_result($statement);
  msqli_stmt_bind_result($statement, $userID, $name, $email, $age, $username, $password);
  
  $response = array();
  $response["success"] = false;
  
  while(msqli_stmt_fetch($statement)){
    $response["success"] = true;
    $response["name"] = name;
    $response["username"] = username;
    $response["email"] = email; 
    $response["age"] = age;
    $response["password"] = password;
    
  echo json_encode($response);
?>
    
    

# 1. 基本格式 
```php
<?php // php file所有都要加这个开头
  include '../database.php'; //在开头include要用到的其他的php
  session_start();
  
  if (isset($_POST['submit'])) {
        $username = trim(mysqli_real_escape_string($connection, $_POST['username']));
        $password = trim(mysqli_real_escape_string($connection, $_POST['password']));

?> // php file所有都要加这个结尾
```

```html
<form method="post" action="../../login.php">
<input type="text" id="username" name="username" placeholder="Enter Your Username"/>
<input type="password" id="password" name="password" placeholder="Enter Your Password"/>
<input id="show-btn" type="submit" name="submit" value="Login"/>
</form>
```

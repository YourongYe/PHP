# 1. 基本格式 
```php
<?php // php file所有都要加这个开头
  include '../database.php'; //在开头include要用到的其他的php
  session_start(); //跟上面的statement没关系，表示这个文件可以access global variables
  
  if (isset($_POST['submit'])) { //isset相当于isnull check， $_POST 会连接到下面的html里的form然后get name=submit，
                                  //如果click了，就会有value
        $username = trim(mysqli_real_escape_string($connection, $_POST['username'])); // trim函数移除字符串两侧的空白字符或其他预定义字符
        $password = trim(mysqli_real_escape_string($connection, $_POST['password'])); 
?> // php file所有都要加这个结尾
```
$ 所有的variable都要加这个符号在前面
$_POST 这个格式的variable说明是global variable
mysqli_real_escape_string(connection,escapestring) 第一个connection会指向include的database， 第二个参数是一个string  
mysqli_real_escape_string 转义在 SQL 语句中使用的字符串中的特殊字符

```html
<form method="post" action="../../login.php">
<input type="text" id="username" name="username" placeholder="Enter Your Username"/>
<input type="password" id="password" name="password" placeholder="Enter Your Password"/>
<input id="show-btn" type="submit" name="submit" value="Login"/>
</form>
```

# 2. If statement & throw Error message
```php
if (!isset($username) || $username == '' || !isset($password) || $password == '') {
    $error = "Please fill in your username and password to log in"; // 这个是一个string variable
    header("Location: ../../frontend/Validate/new/loginForm.php?error=" . urlencode($error)); // 显示error message
    exit(); // 如果call了一个网站，要记得exit
}
```
$item_id = mysqli_insert_id($connection) 返回最后一次查询中的 ID，connection参数指向连接的database

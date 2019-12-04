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
mysqli_real_escape_string(connection,escapestring) 第一个connection会指向include的database， 第二个参数是一个string  
mysqli_real_escape_string 转义在 SQL 语句中使用的字符串中的特殊字符

```html
<form method="post" action="../../login.php">
<input type="text" id="username" name="username" placeholder="Enter Your Username"/>
<input type="password" id="password" name="password" placeholder="Enter Your Password"/>
<input id="show-btn" type="submit" name="submit" value="Login"/>
</form>
```

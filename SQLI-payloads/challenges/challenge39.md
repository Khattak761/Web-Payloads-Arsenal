# Challenge 39 - SQL Injection with 15 Character Limit

## Challenge Overview

**Source Code Analysis:**
```php
<?php
    include "../config.php";
    if($_GET['view_source']) view_source();
?>
<html>
<head>
<title>Challenge 39</title>
</head>
<body>
<?php
    $db = dbconnect();
    if($_POST['id']){
    $POST['id'] = str_replace("\\","",$_POST['id']);
    $POST['id'] = str_replace("'","",$_POST['id']);
    $POST['id'] = substr($POST['id'],0,15);
    $result = mysql_fetch_array(mysql_query($db,"select 1 from member where length(id)<14 and id='{$_POST['id']}'"));
    if($result[0] == 1){
    solve(39);
    }
    }
?>
<form method=post action=index.php>
<input type=text name=id maxlength=15 size=30>
<input type=submit>
</form>
<a href=view_source=1>view_source</a>
</body>
</html>

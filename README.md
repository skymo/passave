Save username and password in your Phonegap apps

I have created a script that allows you to save username and password on forms in Phonegap apps.

<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>Save login information</title>
<script language="javascript">
function logi()
{
var eg = $("#email").val();
var pa = $("#pass").val();
localStorage.setItem("email", eg);
localStorage.removeItem("email");
localStorage.setItem("pass", pa);
localStorage.removeItem("pass");
try {
localStorage.setItem("email", eg);
localStorage.setItem("pass", pa);
} catch (e) {
if (e == QUOTA_EXCEEDED_ERR) {
}
}
if (typeof(localStorage) == 'undefined' ) {
alert('Your browser does not support HTML5 localStorage. Try upgrading.');
} else {
try {
localStorage.setItem("email", eg);
localStorage.setItem("pass", pa);
} catch (e) {
if (e == QUOTA_EXCEEDED_ERR) {
alert('Quota exceeded!');
}
}
}
}
</script>
</head>
<body>
<form method="post">
<script language="javascript">
if(localStorage.getItem("email"))
{
document.write('<input type="text" class="text" id="email" value="'+localStorage.getItem("email")+'" />');
}
else
{
document.write('<input type="text" class="text" id="email" placeholder="Email" />');
}
if(localStorage.getItem("pass"))
{
document.write('<input type="password" class="text" id="pass" value="'+localStorage.getItem("pass")+'" />');
}
else
{
document.write('<input type="password" class="text" id="pass" placeholder="Password" />');
}
</script>
<input type="button" onClick="logi()" class="text" style="background: #35b88f;color:#FFF;font-weight:bold" value="Sign In">
</form>
</body>
</html>

http://www.giveawaystoday.info/tutorials/how-you-can-save-login-information-with-phonegap-on-android-and-ios-apps/

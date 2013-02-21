PHP-Script-File-for-Contact-Form-Mail
=====================================

This is a PHP script for Contact Form Mail, containing a hard coded email address in the code that does not rely on Hosting Account Form Mail Handler Tools, also containing code for a redirect to a "Thank You" html page that contains your graphics, rather than a non-graphic success comment


THIS IS THE PHP THAT YOU CAN COPY AND PASTE INTO NOTEPAD, AND SAVE WITH ENCODING UTF-8

<?php $name = $_POST['name'];
$phone = $_POST['phone'];
$email = $_POST['email'];
$brief_message = $_POST['brief_message'];
$formcontent="From: $name \n Message: $brief_message $phone $checked";
$recipient = "YOUREMAIL@YOURDOMAIN.COM";
$subject = "Website Form Submission";
$mailheader = "From: $email \r\n";
mail($recipient, $subject, $formcontent, $mailheader) or die("Error!");
echo "<script>location.href='thankyou.html';</script>"
?>

THIS IS A SNIPET OF THE FORM CODE OF THE HTML FILE [VIEW IN RAW BY CLICKING RAW LINK IN UPPER RIGHT CORNER]

<form action="php_formmail_handler.php" method="post" ><table width="255" height="30"><TR><TD width="50">Name:</td><td width="125"><div align="right"><input type="text" name="name" text size="18" max length="20"/></div></TD></TR></table><table width="255" height="30"><TR><TD width="50">Phone:</td><td width="125"><div align="right"><input type="text" name="phone" text size="18" max length="20"/></div></TD></TR></table><table width="255" height="30"><TR><TD width="50">Email:</TD><td width="125"><div align="right"><input type="text" name="email" text size="18" max length="20"/></div></TD></TR></table><br><b><i><font><font face="arial black" color="ff0000">Send Us A Message:</font></b></i><textarea cols="23" rows="2" name="brief_message">
</textarea><br><font size="2"><i>We Appreciate Your Interest In Our Services!</i></font><br><div align="right"><input type="submit" value="Submit" /></div></form>

YOU WILL ALSO NEED TO CREATE ANOTHER HTML FILE BESIDES THE ONE THAT CONTAINS THE FORM CODE
BE SURE TO CREATE A "thankyou.html" DOCUMENT, THANKING THE USER FOR THEIR REQUESTS.
THIS CAN CONTAIN THE SAME LOOK AND GRAPHICS AS YOUR OTHER PAGES, AND CONTAIN TEXT SUCH AS:
"Thank you for your request. We will be in contact within 48 hours."

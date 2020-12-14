Ori
<?php
error_reporting(0);



function acak($panjang)
{
$karakter= 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890';
$string = '';
for ($i = 0; $i < $panjang; $i++) {
  $pos = rand(0, strlen($karakter)-1);
  $string .= $karakter{$pos};
 }
return $string;
}
function juanz($panjang)
{
$karakter= 'a123456789bcdefghijklmnopqrstuvwxyz';
$string = '';
for ($i = 0; $i < $panjang; $i++) {
  $pos = rand(0, strlen($karakter)-1);
  $string .= $karakter{$pos};
 }
return $string;
}




echo " ini $time \n";
while(true){

$d = rand (10, 16);
//cara memanggilnya
$juan30= juanz(34);
$juan34= juanz(34);
$juan12= juanz(12);
$juanzz= juanz(16);
$juan16= juanz($d);
$juan10= acak(10);
$juan19= acak(19);
$juan8= juanz(8);
$juan4= juanz(4);
$juanz= juanz(4);
$rand = rand (100000, 900000);
$okeh = rand (1, 90);
$okeh1 = rand (1, 90);
$okeh3 = rand (1,90);
$okeh4 = rand (1,90);
$kim = rand (1000, 9000);


$res="\033[0m";
$hitam="\033[0;30m";
$abu2="\033[1;30m";
$putih="\033[0;37m";
$putih2="\033[1;37m";
$red="\033[0;31m";
$red2="\033[1;31m";
$green="\033[0;32m";
$green2="\033[1;32m";
$yellow="\033[0;33m";
$yellow2="\033[1;33m";
$blue="\033[0;34m";
$blue2="\033[1;34m";
$purple="\033[0;35m";
$purple2="\033[1;35m";
$lblue="\033[0;36m"; 
$lblue2="\033[1;36m";
$cyan = "\e[1;96m";


$rand = rand (10000000, 90000000);
$kim = rand (30, 90);
$oke = rand (1, 10);






echo " \033[1;32m[\033[1;35m?\033[1;32m] Nomer => \033[1;33m";
	$nope = trim(fgets(STDIN));
$data = '{"device":"'.$juanzz.'","login_method":"manual","phone_number":"'.$nope.'"}';
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://ca6cl11co4ja5se6.https://juaranutrimenu.royco.co.id');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
$headers = array();
$headers[] ="ost: ca6cl11co4ja5se6.juaranutrimenu.royco.co.id";
$headers[] ="authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyb2xlIjoiZ3Vlc3QiLCJwbGF0Zm9ybSI6ImFuZHJvaWQiLCJpYXQiOjE2MDY2NjEzNzAsImV4cCI6MTYwOTI1MzM3MH0.OzGbvcE3cxRSyonwQY3skXKHCrS86jFPiDKS_1jk7YI";
$headers[] ="content-type: application/json; charset=UTF-8";
//$headers[] ="content-length: 83";
//$headers[] ="accept-encoding: gzip";
$headers[] ="user-agent: okhttp/4.3.0";
  curl_setopt($ch, CURLOPT_HTTPHEADER,$headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
var_dump($result);
$tuken = $json["data"]["regis_device_id"];
$regis = $json["data"]["regis_phone_number_id"];
$phone = $json["data"]["phone_number"];
$otep = $json["data"]["otp_id"];
echo "ini $tuken \n";


echo " \033[1;32m[\033[1;35m?\033[1;32m] Otp => \033[1;33m";
	$otpp = trim(fgets(STDIN));
$data1 = '{"failed_count":0,"firebase_token":"","login_method":"manual","otp_code":"'.$otpp.'","otp_id":"'.$otep.'","regis_device_id":"'.$tuken.'","regis_phone_number_id":"'.$regis.'"}';
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://ca6cl11co4ja5se6.juaranutrimenu.royco.co.id/api/camden/v1/check-register-otp');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS, $data1);
  curl_setopt($ch, CURLOPT_HTTPHEADER,$headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);
$tukens = $json["data"]["token"];

$time = mktime(hour, minute, second, month, day, year);
$data3 = '{"device_model":"Redmi Note '.$oke.'","device_android":"1'.$oke.'","screen_name":"sign_up_verify_screen","device_sdk":"29","device_manufacture":"Xiaomi","event_date":"'.$time.'","event_name":"sign_up_verify_screen","device_android_version":"1'.$oke.'"}';
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://ca6cl11co4ja5se6.juaranutrimenu.royco.co.id/api/camden/v1/add-user-screen-tracking');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS, $data3);
$headers = array();
$headers[] ="ost: ca6cl11co4ja5se6.dealio.co.id";
$headers[] ="authorization: $tukens";
$headers[] ="content-type: application/json; charset=UTF-8";
//$headers[] ="content-length: 83";
//$headers[] ="accept-encoding: gzip";
$headers[] ="user-agent: okhttp/4.3.0";
  curl_setopt($ch, CURLOPT_HTTPHEADER,$headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);
$email = "$juan16";
//echo " \033[1;32m[\033[1;35m?\033[1;32m] email => $juan16 \033[1;33m";
	
	
	

echo " \033[1;32m[\033[1;35m?\033[1;32m] Kode Reff => \033[1;33m";
	$reff = trim(fgets(STDIN));

$data2 = '{"email":"'.$email.'@vomoto.com","firebase_token":"","login_method":"manual","name":"'.$juan8.'","password":"'.$juan8.'","refcode":"'.$reff.'","regis_device_id":"'.$tuken.'","regis_phone_number_id":"'.$regis.'"}';
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://ca6cl11co4ja5se6.juaranutrimenu.royco.co.id/api/camden/v1/register-user');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS, $data2);
$headers = array();
$headers[] ="ost: ca6cl11co4ja5se6.juaranutrimenu.royco.co.id";
$headers[] ="authorization: $tukens";
$headers[] ="content-type: application/json; charset=UTF-8";
//$headers[] ="content-length: 83";
//$headers[] ="accept-encoding: gzip";
$headers[] ="user-agent: okhttp/4.3.0";
  curl_setopt($ch, CURLOPT_HTTPHEADER,$headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
var_dump($result);

$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://getnada.com/api/v1/u/'.$email.'@vomoto.com/1606666218');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$headers = array();
$headers[] ="Host: getnada.com";
$headers[] ="save-data: on";
$headers[] ="user-agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.125 Safari/537.36";
$headers[] ="accept: */*";
$headers[] ="sec-fetch-site: same-origin";
$headers[] ="sec-fetch-mode: cors";
$headers[] ="sec-fetch-dest: empty";
$headers[] ="referer: https://getnada.com/";
//$headers[] ="accept-encoding: gzip, deflate, br";
//$headers[] ="accept-language: id-ID,id;q=0.9,en-US;q=0.8,en;q=0.7";
//$headers[] ="cookie: __gads=ID=cb217659af0d0ece:T=1599053857:S=ALNI_MYwPpwLGxi2RB_A3SX399wBQpKRoQ";
//$headers[] ="cookie: tarteaucitron=!adsense=wait!gajs=wai";
  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);
sleep (10);
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://getnada.com/api/v1/u/'.$juan16.'@vomoto/0');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);


$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://getnada.com/api/v1/inboxes/'.$email.'@vomoto.com');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);
$uidd = $json["msgs"][0]["uid"];


$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://getnada.com/api/v1/messages/html/'.$uidd.'');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
$headers = array();
$headers[] ="Connection: keep-alive";
$headers[] ="Upgrade-Insecure-Requests: 1";
$headers[] ="Save-Data: on";
$headers[] ="User-Agent: Mozilla/5.0 (Linux; Android 9; Redmi Note 7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/84.0.4147.125 Mobile Safari/537.36";
$headers[] ="Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9";
$headers[] ="Sec-Fetch-Site: cross-site";
$headers[] ="Sec-Fetch-Mode: navigate";
$headers[] ="Sec-Fetch-User: ?1";
$headers[] ="Sec-Fetch-Dest: document$";
$headers[] ="Referer: https://getnada.com/api/v1/messages/html/$uidd";
//$headers[] ="Accept-Encoding: gzip, deflate, br";
//$headers[] ="Accept-Language: id-ID,id;q=0.9,en-US;q=0.8,en;q=0.7";
  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
//var_dump($result);
$a = explode('<a href="https://webstatic.juaranutrimenu.royco.co.id/verify-email?token=', $result);
$b = explode('&amp;email='.$email.'@vomoto.com" target="_blank"><img height="auto" src="https://s3-eu-west-1.amazonaws.com/topolio/uploads/5f9f97e32b938/1604305178.jpg" style="border:0;display:block;outline:none;text-decoration:none;height:auto;width:100%;font-size:13px;" width="600"></a>', $a[1]);
$cc = $b[0];
$udid = $json["uid"];


$data6 = '{"token":"'.$cc.'"}';
$ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, 'https://ca6cl11co4ja5se6.juaranutrimenu.royco.co.id/api/camden/v1/verify-email-user');
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
  curl_setopt($ch, CURLOPT_POST, 1);
  curl_setopt($ch, CURLOPT_POSTFIELDS, $data6);
$headers[] ="Host: ca6cl11co4ja5se6.juaranutrimenu.royco.co.id";
//$headers[] ="content-length: 76";
$headers[] ="accept: application/json, text/plain, */*";

$headers[] ="save-data: on";
$headers[] ="user-agent: Mozilla/5.0 (Linux; Android 10; Redmi Note 7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Mobile Safari/537.36";
$headers[] ="content-type: application/json;charset=UTF-8";
$headers[] ="origin: https://webstatic.juaranutrimenu.royco.co.id";
$headers[] ="sec-fetch-site: same-site";
$headers[] ="sec-fetch-mode: cors";
$headers[] ="sec-fetch-dest: empty";
$headers[] ="referer: https://webstatic.juaranutrimenu.royco.co.id/";
//$headers[] ="accept-encoding: gzip, deflate, br";
//$headers[] ="accept-language: id-ID,id;q=0.9,en-US;q=0.8,en;q=0.7";
  curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
 $result = curl_exec($ch);
 $json = json_decode($result,true);
var_dump($result);


}

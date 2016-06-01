# VolleyMySQL

bash-3.2$ cat getData.php 
<?php 
 
 if($_SERVER['REQUEST_METHOD']=='GET'){
 
 $id  = $_GET['id'];
 
 require_once('dbConnect.php');
 
 $sql = "SELECT * FROM employee WHERE id='".$id."'";
 
 $r = mysqli_query($con,$sql);
 
 $res = mysqli_fetch_array($r);
 
 $result = array();
 
 array_push($result,array(
 "name"=>$res['name'],
 "designation"=>$res['designation'],
 "salary"=>$res['salary']
 )
 );
 
 echo json_encode(array("result"=>$result));
 
 mysqli_close($con);
 
 }
?>
bash-3.2$ pwd
/Applications/MAMP/htdocs/Volley


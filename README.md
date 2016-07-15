# check-network-from-IP
<?php
if(isset($_POST['submit'])) 
{

		$IP1 = strip_tags( trim( $_POST[ 'IP1' ] ) ); 
		$IP2 = strip_tags( trim( $_POST[ 'IP2' ] ) ); 
		$IP3 = strip_tags( trim( $_POST[ 'IP3' ] ) ); 
		$IP4 = strip_tags( trim( $_POST[ 'IP4' ] ) ); 
		$cidr = strip_tags( trim( $_POST[ 'cidr' ] ) );

							if($IP1=='' || $IP2=='' ||$IP3==''||$IP4==''){
									echo 'You left one or more box empty! This is not allowed :)';
							}



							else {
								if($IP1>255 || $IP1<0) echo 'First Octet value is invalid. IP must be less than 255 and greater than 0'; echo '<br><br>';
								if($IP2>255 || $IP2<0) echo 'Second Octet value is invalid. IP must be less than 255 and greater than 0';echo '<br><br>';
								if($IP3>255 || $IP3<0) echo 'Third Octet value is invalid. IP must be less than 255 and greater than 0';echo '<br><br>';
								if($IP4>255 || $IP4<0) echo 'Fourth Octet value is invalid. IP must be less than 255 and greater than 0';echo '<br><br>';
								if($cidr>32 & $cidr<0 ) echo 'Cidr must be greater than 0 and less than 32';echo '<br><br>';



							}

							echo 'You have given IP as  ';
							echo $IP1 .'.' .''. $IP2 .'.'  . $IP3 . '.' . $IP4 .'/' . $cidr;
							echo '<br/>';
							echo '<br/>';
							echo '<br/>';


							if($cidr<9 && $cidr>0){

										if($cidr==1){
											$incr=128;
										}
										if($cidr==2){
											$incr=64;
										}
										if($cidr==3){
											$incr=32;
										}
										if($cidr==4){
											$incr=16;
										}
										if($cidr==5){
											$incr=8;
										}
										if($cidr==6){
											$incr=4;
										}
										if($cidr==7){
											$incr=2;
										}
										if($cidr==8){
											$incr=1;
										}
										$res=intval($IP1/$incr);


										if($res==0){
										$res1=0;

										}
										else {$res1=$res*$incr;}
									echo 'We Calculated the Network IP as below . ';
									echo '<br/>';

								
									echo $res1; echo ' .';
									echo '0';  echo ' .';
									echo '0'; echo ' .';
									echo '0';

							}


							if($cidr<17 && $cidr>8){

										if($cidr==9){
											$incr=128;
										}
										if($cidr==10){
											$incr=64;
										}
										if($cidr==11){
											$incr=32;
										}
										if($cidr==12){
											$incr=16;
										}
										if($cidr==13){
											$incr=8;
										}
										if($cidr==14){
											$incr=4;
										}
										if($cidr==15){
											$incr=2;
										}
										if($cidr==16){
											$incr=1;
										}
										$res=intval($IP2/$incr);


										if($res==0){
										$res1=0;

										}
										else {$res1=$res*$incr;}
									echo 'We Calculated the Network IP as below . ';
									echo '<br/>';

								
									echo $IP1; echo ' .';
									echo $res1;  echo ' .';
									echo '0'; echo ' .';
									echo '0';

							}


							if($cidr<25 && $cidr>16){

										if($cidr==17){
											$incr=128;
										}
										if($cidr==18){
											$incr=64;
										}
										if($cidr==19){
											$incr=32;
										}
										if($cidr==20){
											$incr=16;
										}
										if($cidr==21){
											$incr=8;
										}
										if($cidr==22){
											$incr=4;
										}
										if($cidr==23){
											$incr=2;
										}
										if($cidr==24){
											$incr=1;
										}
										$res=intval($IP3/$incr);


										if($res==0){
										$res1=0;

										}
										else {$res1=$res*$incr;}
									echo 'We Calculated the Network IP as below . ';
									echo '<br/>';

								
									echo $IP1; echo ' .';
									echo $IP2;  echo ' .';
									echo $res1; echo ' .';
									echo '0';

							}


							if($cidr<33 && $cidr>24){

										if($cidr==25){
											$incr=128;
										}
										if($cidr==26){
											$incr=64;
										}
										if($cidr==27){
											$incr=32;
										}
										if($cidr==28){
											$incr=16;
										}
										if($cidr==29){
											$incr=8;
										}
										if($cidr==30){
											$incr=4;
										}
										if($cidr==31){
											$incr=2;
										}
										if($cidr==32){
											$incr=1;
										}
										$res=intval($IP4/$incr);


										if($res==0){
										$res1=0;

										}
										else {$res1=$res*$incr;}
										echo 'We Calculated the Network IP as below . ';
										echo '<br/>';
										echo '<br/>';
										echo '<br/>';
										echo $IP1; echo '.';
										echo $IP2;  echo '.';
										echo $IP3; echo '.';
										echo $res1;

							}
							echo '<br><br>';
							echo '<div id="warning">Please notify bugs (munna786bd@gmail.com)</div>';
							echo '<br> Give Another IP:<br>';
}

echo '';
?>


<h1> Network Finder Tool By Munna </h1>
<h2> Write A HOST IP and it's CIDR value and Click Submit</h2>
<h3>Example 192.168.50.1/25</h3>


<form action="<?php echo $_SERVER['PHP_SELF']; ?>" method="POST">
<input type="text" name="IP1">.
<input type="text" name="IP2">.
<input type="text" name="IP3">.
<input type="text" name="IP4">
/ <input type="text" name="cidr">
<input type="submit" name="submit" id="button-blue">
<div class="ease"></div>
</form>


<div id="form-main">

  </div>
  
  
  <style>
  @import url(http://fonts.googleapis.com/css?family=Montserrat:400,700);

html{    

  background-size: cover;
  height:100%;
}

#feedback-page{
	text-align:center;
}

#form-main{
	width:100%;
	float:left;
	padding-top:0px;
}

#form-div {
	background-color:rgba(72,72,72,0.4);
	padding-left:35px;
	padding-right:35px;
	padding-top:35px;
	padding-bottom:50px;
	width: 450px;
	float: left;
	left: 50%;
	position: absolute;
  margin-top:30px;
	margin-left: -260px;
  -moz-border-radius: 7px;
  -webkit-border-radius: 7px;
}

.feedback-input {
	color:#3c3c3c;
	font-family: Helvetica, Arial, sans-serif;
  font-weight:500;
	font-size: 18px;
	border-radius: 0;
	line-height: 22px;
	background-color: #fbfbfb;
	padding: 13px 13px 13px 54px;
	margin-bottom: 10px;
	width:100%;
	-webkit-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	box-sizing: border-box;
  border: 3px solid rgba(0,0,0,0);
}

.feedback-input:focus{
	background: #fff;
	box-shadow: 0;
	border: 3px solid #3498db;
	color: #3498db;
	outline: none;
  padding: 13px 13px 13px 54px;
}

.focused{
	color:#30aed6;
	border:#30aed6 solid 3px;
}



textarea {
    width: 100%;
    height: 150px;
    line-height: 150%;
    resize:vertical;
}

input:hover, textarea:hover,
input:focus, textarea:focus {
	background-color:white;
}

#button-blue{
	font-family: 'Montserrat', Arial, Helvetica, sans-serif;
	float:left;
	width: 100%;
	border: #fbfbfb solid 4px;
	cursor:pointer;
	background-color: #3498db;
	color:white;
	font-size:24px;
	padding-top:22px;
	padding-bottom:22px;
	-webkit-transition: all 0.3s;
	-moz-transition: all 0.3s;
	transition: all 0.3s;
  margin-top:20px;
  font-weight:700;
}

#button-blue:hover{
	background-color: #3498aa;
	color: #0493ad;
}
	
.submit:hover {
	color: green;
}
	
.ease {
	width: 0px;
	height: 74px;
	background-color: #fbfbfb;
	-webkit-transition: .3s ease;
	-moz-transition: .3s ease;
	-o-transition: .3s ease;
	-ms-transition: .3s ease;
	transition: .3s ease;
}

.submit:hover .ease{
  width:100%;
  background-color:white;
}

@media only screen and (max-width: 580px) {
	#form-div{
		left: 3%;
		margin-right: 3%;
		width: 88%;
		margin-left: 0;
		padding-left: 3%;
		padding-right: 3%;
	}
}
  
  
  </style>


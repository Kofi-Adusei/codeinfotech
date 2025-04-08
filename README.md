<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>App | Log in</title>

  <!-- Google Font: Source Sans Pro -->
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,400i,700&display=fallback">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.3/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
  <link rel="stylesheet" href="../../plugins/fontawesome-free/css/all.min.css">
  <script src="../../dist/js/jquery.js"></script>
  <link rel="stylesheet" href="../../plugins/icheck-bootstrap/icheck-bootstrap.min.css">
  <link rel="stylesheet" href="../../dist/css/adminlte.min.css">
  <link href="../../dist/css/custom.css" rel="stylesheet" type="text/css"/>
  <style>
      body{
        background-image : url("../../dist/image/kente3.jpg"); 
      }
      .card{
          padding: 1.3em .3em 3em;
          border-radius: .4em;
          box-shadow: 2px 2px 2px 2px rgba(255,255,255);
      }
      .btn-reload{
          background-color: #869791;
      }
      .input-text-code{
          padding: .08em .08em .08em;
          border-radius: 4em;
          text-align: center;
          border-color: #008966;
          border-bottom-color: #008966;
          border-top-color: #008966;
      }
  </style>
 
</head>
<body class="hold-transition login-page">
<div class="login-box">
  <!-- /.login-logo -->
  <div class="card card-outline" style="width:25rem;">
    <div class="card-header text-center">
        <a href="../../app-login-opt.php">
          <img src="../../dist/image/TEACHER_SIGNIN.png" class = "img-circle" align="center" width="250" height="110"/>
       </a>
        <span class="text-danger" id="response"><?php echo $flag_message?></span>
    </div>
    <div class="card-body login-card-body">
        <form method="post" id="app-login-form" autocomplete="off">
        <div class="input-group mb-3">
            <input type="email" class="form-control input-box" name="useremail" id="useremail" placeholder="Username (eg. example@gmail.com)">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-envelope"></span>
            </div>
          </div>
        </div>
        <div class="input-group mb-3">
          <input type="password" class="form-control input-box" name="upassword" id="upassword" placeholder="Enter Password">
          <div class="input-group-append">
            <div class="input-group-text">
              <span class="fas fa-lock"></span>
            </div>
          </div>
        </div>
         <div class="custom-control custom-checkbox mb-3 turing">
             <div class="turing row">
         <div class="col-sm-6">
             <a href="#" class="reload btn-reload"  onClick="generateCode(6);return false;">
                <div class="turing reloader"><b>&#x21BA; reload code</b></div>
            </a>
                 <p id="randomfield" name="randomfield" style="text-align: center;font-size:x-large; font-weight: bold; width:100%;height:50px;margin-bottom:6px; margin-top:3px;background:#E6E6E6;border-color:#E6E6E6; border-radius:50px;padding:3px; margin-left: -20px"></p>
          </div>
              <div class="col-sm-6">
                <input type="text" id="login" style="text-align: center; width:100%; font-size:x-large; font-weight: bold" class="fadeIn second input100 input-text-code" name="txtcaptha" placeholder="Enter code">
            </div>
         </div>
         </div>
        <div class="row">
          <div class="col-8">
              
          </div>
          <!-- /.col -->
          <div class="col-4">
              <button type="submit" style="border-radius: 2em;background-color: teal;color:#0000FF #ffffff;" class="btn btn-primary btn-block" name="submit" id="submit">Sign In</button>
          </div>
          <!-- /.col -->
        </div>
      </form>
       
      <p class="mb-1">
        <a href="#">I forgot my password</a>
      </p>
      <p class="mb-0">
          <a href="../../app-register.php" class="text-center">Register as new membership</a>
      </p>
    </div>
    <!-- /.login-card-body -->
  </div>
</div>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.3/jquery.min.js"></script>    
<script src="../../plugins/jquery/jquery.min.js"></script>
<script src="../../plugins/bootstrap/js/bootstrap.bundle.min.js"></script>
<script src="../../dist/js/adminlte.min.js"></script>
<script src="../../plugins/jquery/jquery.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.3/jquery.min.js" integrity="sha512-STof4xm1wgkfm7heWqFJVn58Hm3EtS31XFaagaa8VMReCXAkQnJZ+jEy8PCC/iT18dFy95WcExNHFTqLyp72eQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.3/jquery.js" integrity="sha512-nO7wgHUoWPYGCNriyGzcFwPSF+bPDOR+NvtOYy2wMcWkrnCNPKBcFEkU80XIN14UVja0Gdnff9EmydyLlOL7mQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
  <script>
    
    const characters='0123456789ABCDEFGHIJKLMNOPQRSTUVWZYZabcdefghijklmnopqrstuvwxyz';
    function generateCode(length){
        var generatecode='';
        for(var i = 0; i < length; i++){
          //var code =  characters.charAt(Math.floor(Math.random()*characters.length));
           //generatecode += code
            var code =  Math.floor(Math.random()*characters.length);
           generatecode += characters.substring(code,code+1);
        }
        document.getElementById("randomfield").innerHTML=generatecode;
    }
    generateCode(6);
   
    $(function() {
       $('#submit').click(function() {
         var cod=$('#randomfield').text();
          // alert(cod);
      });
     })
    
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        body{
    margin: 0;
}
.container{
    background-color: snow;
    width: 100%;
    height: 900px;
}
.heading{
    width: 100%;
    height: 150px;
    margin: 0 auto;
}
.heading_title{
    font-size: 50px;
    font-style: italic;
    font-weight: bold;
    font-family: 隶书;
    color: burlywood;
    width: 300px;
    height: 100px;
    padding-top: 50px;
    padding-left: 20px;
    margin: 0 auto;
    float: left;
}
.nav_bar{
    margin: 0px auto;;
    width: 900px;
    height: 70px;
    padding-top: 60px;
    padding-left: 160px;
}
.nav{
    width: 700px;
    height: 40px;
    padding-left: 60px;
    margin-bottom: 20px;
}
li{
    display: inline;
    list-style-type: none;
    padding-left: 50px;
}
a{
    text-decoration: none;
    color: dimgrey;
    font-size: 30px;
    font-family: 华文行楷;
}
a:hover{
    color: grey;
}
#todayTime{
    width: 100px;
    height: 20px;
    font-family: "Adobe 宋体 Std L";
    font-size: 25px;
    color: black;
    font-style: italic;
    float: right;
    margin-top: 70px;
    margin-right: 60px;
}
.body{
    width: 100%;
    height: 750px;
    background-color: bisque;
    margin: 0px auto;
}
.body_left{
    float: left;
    background-color: grey;
    width: 20%;
    height: 750px;
}
.body_right{
    float: right;
    background-color: grey;
    width: 20%;
    height: 750px;
}
.formOne{
    float: right;
    width: 300px;
    height: 25px;
    padding-top: 40px;
    display: inline;
}
.formTwo{
    float: right;
    width: 300px;
    height: 25px;
    padding-top: 5px;
    margin-right: 1px;
    display: inline;
    margin-top: 2px;
}
.date{
    width: 200px;
    height: 100px;
    float: right;
    margin-right: 25px;
    margin-top: 10px;
}
    </style>
</head>
<body>
<script>
    function time() {
        var today = new Date();
        var h = today.getHours();
        var m = today.getMinutes();
        var s = today.getSeconds();
        h = checkTime(h);
        m = checkTime(m);
        s = checkTime(s);
        document.getElementById("todayTime").innerHTML=h+":"+m+":"+s;
    }
    setInterval(function () {
        time()
    },1000)
    function checkTime(i) {
        if(i<10){
            i = "0"+i;
        }
        return i;
    }
    function checkEmail() {
        var email = document.getElementById("email");
        if(email.value==""){
            alert("请输入邮箱");
            return false;
        }
        else if(!email.checkValidity()){
            alert("请输入正确的邮箱");
            return false;
        }
    }
</script>
    <div class="container">
        <div class="heading">
            <p id="todayTime"></p>
            <div class="heading_title">
                科学研究院
            </div>
            <div class="nav_bar">
                <ul class="nav">
                    <li>|<a href="#">首页</a>|</li>
                    <li>|<a href="#">科技创新</a>|</li>
                    <li>|<a href="#">理论创新</a>|</li>
                    <li>|<a href="#">技术问答</a>|</li>
                </ul>
            </div>
        </div>
        <div class="body">
            <div class="body_left">
                <div class="formOne">
                    <form id="testform" onsubmit="checkEmail()" novalidate="true">
                        <label id="email">邮箱:</label>
                        <input type="email" placeholder="example@xx.com" required="required">
                    </form>
                </div>
                <div class="formTwo">
                    <form>
                        <label id="password">密码：</label>
                        <input type="text" required="required">
                        <input type="submit" value="确认">
                    </form>
                </div>
                <div class="date">
                    <form>
                        <input type="date" name="date" value="确认">
                    </form>
                </div>
            </div>
            <div class="body_right">

            </div>
        </div>
    </div>
</body>
</html>

<!DOCTYPE html>
<html lang="zh">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>❤️</title>

<style>
*{
    margin:0;
    padding:0;
    overflow:hidden;
}

body{
    background:#000;
    width:100vw;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    color:white;
    font-family:"Microsoft YaHei",sans-serif;
}

#box{
    text-align:center;
}

input{
    padding:12px;
    font-size:20px;
    border-radius:10px;
    border:none;
    text-align:center;
}

button{
    margin-top:15px;
    padding:12px 25px;
    font-size:18px;
    border:none;
    border-radius:10px;
    cursor:pointer;
}

#loveText{
    position:absolute;
    z-index:100;
    font-size:40px;
    font-weight:bold;
    text-shadow:0 0 20px pink;
}

.heart{
    position:absolute;
    color:red;
    animation:fall linear forwards;
}

@keyframes fall{
    from{
        transform:translateY(-100px);
        opacity:1;
    }
    to{
        transform:translateY(110vh);
        opacity:0;
    }
}
</style>
</head>

<body>

<div id="box">
    <h2>请输入你的名字 ❤️</h2>
    <br>
    <input id="name" placeholder="输入名字">
    <br>
    <button onclick="startLove()">进入</button>
</div>

<div id="loveText" style="display:none;"></div>

<script>
function startLove(){

    let name=document.getElementById("name").value;

    if(name===""){
        alert("请输入名字");
        return;
    }

    document.getElementById("box").style.display="none";

    let text=document.getElementById("loveText");
    text.innerHTML=name+" ❤️ 我爱你";
    text.style.display="block";

    setInterval(createHeart,100);
}

function createHeart(){

    let heart=document.createElement("div");

    heart.className="heart";
    heart.innerHTML="❤️";

    heart.style.left=Math.random()*window.innerWidth+"px";
    heart.style.top="-50px";
    heart.style.fontSize=(20+Math.random()*50)+"px";

    let duration=3+Math.random()*4;
    heart.style.animationDuration=duration+"s";

    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },duration*1000);
}
</script>

</body>
</html>

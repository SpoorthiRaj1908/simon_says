let gameSeq =[];
let userSeq=[];
let scores=[];
let level=0;
let started=false;
let btns=["yellow","red","purple","green"];
let h2=document.querySelector("h2");
let body=document.querySelector("body");
document.addEventListener("keypress",function(){
    if(started==false){
    console.log("game started");
    started=true;
    levelup();
    }
});
function gameflash(btn){
    btn.classList.add("flash");
    setTimeout(function(){
        btn.classList.remove("flash");
    },250);
}

function levelup(){
    userSeq=[];
level++;
h2.innerText=`level  ${level}`;
let randomidx=Math.floor(Math.random()*3);
let randomcolor=btns[randomidx];
let randombtn=document.querySelector(`.${randomcolor}`);
gameSeq.push(randomcolor);
console.log(gameSeq);
gameflash(randombtn);
}
function checkans(idx){
    if(gameSeq[idx]==userSeq[idx]){
        if(userSeq.length==gameSeq.length){
            setTimeout(levelup,1000);
        }
        
    }
    else{
        body.classList.add("done");
        setTimeout(function(){
            body.classList.remove("done");
        },150);
        let score=level;
        scores.push(score);

        let highestscore=Math.max(...scores);
        console.log(highestscore);
        h2.innerHTML=`game over ! your score is<b> ${score} </b><br> press any key to restart<br> your highest score is ${highestscore}`;
        console.log(scores);
        reset();

    }

}
function userflash(btn){
btn.classList.add("userflash");
setTimeout(function(){
    btn.classList.remove("userflash");
},250);

}

function btnpressed(){
let btn=this;
gameflash(btn);
let usercolor=btn.getAttribute("id");
userSeq.push(usercolor);
console.log(userSeq);
checkans(userSeq.length-1);
}
let btn=document.querySelectorAll("button");
let allbtns=document.querySelectorAll(".btn");

for(bt of allbtns) {
    bt.addEventListener("click",btnpressed);
}
function reset(){
    started=false;
    gameSeq=[];
    userSeq=[];
    level=0;
}

// Elements
const loading = document.getElementById("loading");
const main = document.getElementById("main");

const startBtn = document.getElementById("startBtn");

const hero = document.querySelector(".hero");
const cake = document.getElementById("cakeSection");
const gift = document.getElementById("giftSection");
const message = document.getElementById("messageSection");
const finalPage = document.getElementById("finalSection");

const next1 = document.getElementById("next1");
const next2 = document.getElementById("next2");
const next3 = document.getElementById("next3");
const openGift = document.getElementById("openGift");

const typing = document.getElementById("typing");

// Start Website
startBtn.onclick = () => {
loading.style.display = "none";
main.classList.remove("hidden");
};

// Hero → Cake
next1.onclick = () => {
hero.classList.add("hidden");
cake.classList.remove("hidden");
};

// Cake → Gift
next2.onclick = () => {
cake.classList.add("hidden");
gift.classList.remove("hidden");
};

// Gift → Message
openGift.onclick = () => {
gift.classList.add("hidden");
message.classList.remove("hidden");

typeMessage();
};

// Message → Final
next3.onclick = () => {
message.classList.add("hidden");
finalPage.classList.remove("hidden");

confetti();
};

// --------------------
// Typewriter Effect
// --------------------

const text = `Happy 20th Birthday Dnyaneshwari! ❤️

Today is your special day and I just wanted to remind you how amazing you are.

Thank you for being such a kind, caring and wonderful friend.

May this new year of your life bring you endless happiness, success, beautiful memories and lots of smiles.

Keep shining...
Keep smiling...
Keep being the wonderful person you are.

May all your dreams come true.

Happy Birthday once again! 🎂🎉💖`;

let i = 0;

function typeMessage() {

typing.innerHTML = "";

i = 0;

let timer = setInterval(() => {

typing.innerHTML += text.charAt(i);

i++;

if(i >= text.length){

clearInterval(timer);

}

},40);

}

// --------------------
// Simple Confetti
// --------------------

function confetti(){

for(let i=0;i<120;i++){

let piece = document.createElement("div");

piece.style.position="fixed";
piece.style.width="10px";
piece.style.height="10px";
piece.style.left=Math.random()*100+"vw";
piece.style.top="-20px";
piece.style.background=hsl(${Math.random()*360},100%,60%)`;
piece.style.borderRadius="50%";
piece.style.zIndex="999";

document.body.appendChild(piece);

let fall = piece.animate(

[

{
transform:"translateY(0px) rotate(0deg)"
},

{
transform:translateY(${window.innerHeight+100}px) rotate(${Math.random()*720}deg)
}

],

{

duration:3000+Math.random()*2000,

easing:"linear"

});

fall.onfinish=()=>piece.remove();

}

}

// --------------------
// Floating Balloons
// --------------------

setInterval(()=>{

let balloon=document.createElement("div");

balloon.innerHTML="🎈";

balloon.style.position="fixed";

balloon.style.left=Math.random()*100+"vw";

balloon.style.bottom="-50px";

balloon.style.fontSize=(30+Math.random()*30)+"px";

balloon.style.zIndex="50";

document.body.appendChild(balloon);

let fly=balloon.animate(

[

{transform:"translateY(0px)"},

{transform:translateY(-${window.innerHeight+100}px)`}

],

{

duration:8000,

easing:"linear"

}

);

fly.onfinish=()=>balloon.remove();

},1500);
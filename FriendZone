<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#ffffff">
<title>Mini Facebook</title>

<style>
*{box-sizing:border-box}
body{
  margin:0;
  font-family:Arial,Helvetica,sans-serif;
  background:#fff;
  color:#17191c;
  padding-bottom:75px
}
button,input,textarea{font:inherit}
button{cursor:pointer}
.topbar{
  position:sticky;
  top:0;
  z-index:10;
  background:#fff;
  padding:12px 14px 8px;
  border-bottom:1px solid #ddd
}
.toprow{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:12px
}
.logo{
  font-size:29px;
  font-weight:800;
  color:#1877f2;
  letter-spacing:-1px
}
.icon{
  border:0;
  background:#f0f2f5;
  border-radius:50%;
  width:42px;
  height:42px;
  font-size:21px;
  display:grid;
  place-items:center;
  flex-shrink:0
}
.topicons{display:flex;gap:9px}
.tabs{
  display:flex;
  justify-content:space-around;
  margin-top:12px;
  color:#606770;
  font-size:21px
}
.tab{
  flex:1;
  text-align:center;
  padding:9px 0 5px;
  border:0;
  background:white;
  border-bottom:3px solid transparent
}
.tab.active{
  color:#1877f2;
  border-bottom-color:#1877f2
}
.composer{
  display:flex;
  align-items:center;
  gap:10px;
  padding:14px;
  border-bottom:7px solid #f0f2f5
}
.avatar{
  width:43px;
  height:43px;
  flex-shrink:0;
  border-radius:50%;
  display:grid;
  place-items:center;
  background:#dceaff;
  color:#1877f2;
  font-size:20px;
  font-weight:bold;
  overflow:hidden
}
.avatar img{
  width:100%;
  height:100%;
  object-fit:cover
}
.composer button{
  background:#f0f2f5;
  border:0;
  border-radius:24px;
  padding:12px 15px;
  flex:1;
  text-align:left;
  color:#65676b
}
.stories{
  display:flex;
  overflow-x:auto;
  gap:9px;
  padding:12px;
  border-bottom:7px solid #f0f2f5
}
.story{
  position:relative;
  min-width:112px;
  height:178px;
  border:1px solid #ddd;
  border-radius:13px;
  overflow:hidden;
  background:#e9f2ff
}
.story img{
  width:100%;
  height:140px;
  object-fit:cover
}
.story .storyname{
  font-size:12px;
  font-weight:bold;
  padding:7px 4px;
  text-align:center
}
.story .plus{
  position:absolute;
  top:116px;
  left:37px;
  width:36px;
  height:36px;
  border-radius:50%;
  background:#1877f2;
  border:3px solid white;
  color:white;
  font-size:25px;
  display:grid;
  place-items:center
}
.post{
  border-bottom:7px solid #f0f2f5;
  padding:13px 14px 8px
}
.posthead{
  display:flex;
  align-items:center;
  gap:10px
}
.postinfo{flex:1;min-width:0}
.postname{font-weight:bold;font-size:15px}
.posttime{font-size:12px;color:#65676b;margin-top:4px}
.more{
  border:0;background:white;
  font-size:22px;color:#65676b
}
.posttext{
  margin:13px 0;
  font-size:16px;
  line-height:1.45;
  overflow-wrap:anywhere
}
.postphoto{
  display:block;
  width:calc(100% + 28px);
  max-width:none;
  margin-left:-14px;
  height:auto;
  max-height:520px;
  object-fit:cover;
  background:#eee
}
.poststats{
  display:flex;
  justify-content:space-between;
  padding:10px 0;
  color:#65676b;
  font-size:13px
}
.actions{
  display:flex;
  border-top:1px solid #ddd;
  padding-top:5px
}
.actions button{
  flex:1;
  padding:10px 0;
  border:0;
  background:white;
  color:#65676b;
  font-size:13px;
  font-weight:bold
}
.actions button.liked{color:#1877f2}
.commentbox{
  display:flex;
  gap:6px;
  margin:7px 0
}
.commentbox input{
  min-width:0;
  flex:1;
  border:0;
  background:#f0f2f5;
  border-radius:20px;
  padding:10px 13px
}
.commentbox button{
  border:0;
  background:#1877f2;
  color:white;
  border-radius:18px;
  padding:8px 12px
}
.comment{
  margin:8px 0;
  background:#f0f2f5;
  padding:9px 12px;
  border-radius:15px;
  font-size:13px;
  overflow-wrap:anywhere
}
.bottomnav{
  position:fixed;
  bottom:0;
  left:0;
  right:0;
  z-index:20;
  display:flex;
  justify-content:space-around;
  background:white;
  border-top:1px solid #ddd;
  padding:7px 1px max(7px,env(safe-area-inset-bottom))
}
.navitem{
  flex:1;
  border:0;
  background:white;
  color:#555;
  font-size:10px;
  font-weight:bold;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:3px
}
.navitem span{font-size:22px}
.navitem.active{color:#1877f2}
.screen{display:none}
.screen.active{display:block}
.panel{padding:16px}
.panel h2{margin-top:5px}
.field{
  display:block;
  width:100%;
  margin:12px 0;
  padding:12px;
  border:1px solid #ddd;
  border-radius:10px
}
.primary{
  background:#1877f2;
  color:white;
  border:0;
  border-radius:8px;
  padding:12px 17px;
  font-weight:bold
}
.muted{color:#65676b;font-size:13px}
@media(min-width:700px){
  main{max-width:600px;margin:auto}
  .topbar{padding-left:max(14px,calc((100% - 900px)/2))}
}
</style>
</head>

<body>

<header class="topbar">
  <div class="toprow">
    <button class="icon" id="menuBtn" aria-label="Menu">☰</button>
    <div class="logo">facebook</div>
    <div class="topicons">
      <button class="icon" id="createBtn" aria-label="Create post">＋</button>
      <button class="icon" id="searchBtn" aria-label="Search">⌕</button>
      <button class="icon" id="messengerBtn" aria-label="Messenger">💬</button>
    </div>
  </div>
  <div class="tabs">
    <button class="tab active" data-screen="home">⌂</button>
    <button class="tab" data-screen="videos">▣</button>
    <button class="tab" data-screen="friends">♙</button>
    <button class="tab" data-screen="market">▤</button>
    <button class="tab" data-screen="notifications">♧</button>
  </div>
</header>

<main>
<section id="home" class="screen active">

  <div class="composer">
    <div class="avatar" id="smallAvatar">G</div>
    <button id="openComposer">What's on your mind?</button>
    <button class="icon" id="photoBtn" aria-label="Add photo">▧</button>
  </div>

  <section class="stories" id="stories">
    <div class="story">
      <div style="height:140px;display:grid;place-items:center;font-size:40px">📷</div>
      <div class="plus">+</div>
      <div class="storyname">Create story</div>
    </div>
    <div class="story">
      <div style="height:140px;display:grid;place-items:center;font-size:45px">🌅</div>
      <div class="storyname">Your friends</div>
    </div>
    <div class="story">
      <div style="height:140px;display:grid;place-items:center;font-size:45px">🌍</div>
      <div class="storyname">Explore</div>
    </div>
    <div class="story">
      <div style="height:140px;display:grid;place-items:center;font-size:45px">🎉</div>
      <div class="storyname">Community</div>
    </div>
  </section>

  <div class="panel" id="composerPanel" hidden>
    <h3>Create post</h3>
    <textarea class="field" id="postText" maxlength="2000"
      placeholder="What's on your mind?"></textarea>
    <input class="field" id="photoUrl"
      placeholder="Optional photo URL (https://...)">
    <button class="primary" id="publishBtn">Post</button>
    <button class="icon" id="cancelPost">×</button>
  </div>

  <div id="feed"></div>
</section>

<section id="videos" class="screen panel">
  <h2>Videos & Reels</h2>
  <p>Discover videos from your community.</p>
  <p class="muted">Video uploads can be added in a future version.</p>
</section>

<section id="friends" class="screen panel">
  <h2>Friends</h2>
  <p>Welcome to your community!</p>
  <p class="muted">Real friend requests require user accounts and a shared database.</p>
</section>

<section id="market" class="screen panel">
  <h2>Marketplace</h2>
  <p>Buy and sell within your community.</p>
  <p class="muted">Product listings are not enabled yet.</p>
</section>

<section id="notifications" class="screen panel">
  <h2>Notifications</h2>
  <p>You’re all caught up.</p>
</section>

<section id="messages" class="screen panel">
  <h2>Messenger</h2>
  <input class="field" id="messageName" placeholder="Recipient's name">
  <div id="chatMessages"></div>
  <form id="messageForm">
    <input class="field" id="messageText" placeholder="Write a message..." required>
    <button class="primary">Send</button>
  </form>
  <p class="muted">Demo only: messages are stored on this device, not delivered to another person.</p>
</section>

<section id="profile" class="screen panel">
  <h2>Your Profile</h2>
  <div class="avatar" id="profileAvatar">G</div>
  <input class="field" id="profileName" placeholder="Your name">
  <button class="primary" id="saveName">Save name</button>
  <p class="muted">Your name is saved in this browser.</p>
</section>

<section id="search" class="screen panel">
  <h2>Search posts</h2>
  <input class="field" id="searchInput" placeholder="Search the feed...">
  <div id="searchResults"></div>
</section>

<section id="menu" class="screen panel">
  <h2>Menu</h2>
  <button class="field" data-goto="profile">👤 My Profile</button>
  <button class="field" data-goto="friends">👥 Friends</button>
  <button class="field" data-goto="messages">💬 Messenger</button>
  <p class="muted">Welcome to Mini Facebook.</p>
</section>
</main>

<nav class="bottomnav">
  <button class="navitem active" data-screen="home"><span>⌂</span>Home</button>
  <button class="navitem" data-screen="videos"><span>▣</span>Reels</button>
  <button class="navitem" data-screen="friends"><span>♙</span>Friends</button>
  <button class="navitem" data-screen="notifications"><span>♧</span>Alerts</button>
  <button class="navitem" data-screen="profile"><span>☻</span>Profile</button>
</nav>

<script>
const $ = id => document.getElementById(id);

function read(key, fallback){
  try{
    const v = localStorage.getItem(key);
    return v ? JSON.parse(v) : fallback;
  }catch(e){return fallback}
}

let name = read("mini-name","Guest");
let posts = read("mini-posts",[
  {
    id:1,
    author:"Mini Facebook",
    text:"Welcome to our community! 🎉 Share your thoughts and say hello.",
    photo:"",
    likes:[],
    comments:[]
  },
  {
    id:2,
    author:"Community News",
    text:"This is where posts from your community will appear.",
    photo:"",
    likes:[],
    comments:[]
  }
]);

function save(){
  try{
    localStorage.setItem("mini-name",JSON.stringify(name));
    localStorage.setItem("mini-posts",JSON.stringify(posts));
  }catch(e){}
}

function el(tag,cls,txt){
  const x=document.createElement(tag);
  if(cls)x.className=cls;
  if(txt!==undefined)x.textContent=txt;
  return x;
}

function go(screen){
  document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));
  const target=$(screen);
  if(target)target.classList.add("active");

  document.querySelectorAll("[data-screen]").forEach(b=>{
    b.classList.toggle("active",b.dataset.screen===screen);
  });

  window.scrollTo(0,0);
}

function render(){
  $("smallAvatar").textContent=name.charAt(0).toUpperCase();
  $("profileAvatar").textContent=name.charAt(0).toUpperCase();
  const feed=$("feed");
  feed.replaceChildren();

  [...posts].reverse().forEach(post=>{
    const card=el("article","post");
    const head=el("div","posthead");
    head.append(el("div","avatar",(post.author||"G").charAt(0).toUpperCase()));

    const info=el("div","postinfo");
    info.append(el("div","postname",post.author));
    info.append(el("div","posttime","Just now · 🌐"));
    head.append(info);
    head.append(el("button","more","•••"));
    card.append(head);

    if(post.text)card.append(el("div","posttext",post.text));

    if(post.photo){
      const img=el("img","postphoto");
      img.src=post.photo;
      img.alt="Post photo";
      img.onerror=()=>img.remove();
      card.append(img);
    }

    const stats=el("div","poststats",
      "👍 "+post.likes.length+" likes     ·     "+post.comments.length+" comments");
    card.append(stats);

    const actions=el("div","actions");
    const like=el("button",
      post.likes.includes(name)?"liked":"",
      post.likes.includes(name)?"👍 Liked":"👍 Like");
    like.onclick=()=>{
      post.likes=post.likes.includes(name)
        ?post.likes.filter(n=>n!==name):[...post.likes,name];
      save();render();
    };

    const comment=el("button","","💬 Comment");
    comment.onclick=()=>input.focus();

    const share=el("button","","↗ Share");
    share.onclick=async()=>{
      const text=post.text||"Check out this post!";
      try{
        if(navigator.share)await navigator.share({title:"Mini Facebook",text});
        else if(navigator.clipboard){
          await navigator.clipboard.writeText(text);
          alert("Post text copied.");
        }else alert(text);
      }catch(e){}
    };
    actions.append(like,comment,share);
    card.append(actions);

    const comments=el("div","");
    post.comments.forEach(c=>{
      comments.append(el("div","comment",c.author+": "+c.text));
    });

    const form=el("form","commentbox");
    const input=el("input","");
    input.placeholder="Write a comment...";
    input.maxLength=500;
    input.required=true;
    const send=el("button","","Send");
    send.type="submit";
    form.append(input,send);
    form.onsubmit=e=>{
      e.preventDefault();
      const text=input.value.trim();
      if(!text)return;
      post.comments.push({author:name,text});
      save();render();
    };
    comments.append(form);
    card.append(comments);
    feed.append(card);
  });
}

function openComposer(){
  go("home");
  $("composerPanel").hidden=false;
  $("postText").focus();
}

$("openComposer").onclick=openComposer;
$("createBtn").onclick=openComposer;
$("photoBtn").onclick=openComposer;
$("cancelPost").onclick=()=>{$("composerPanel").hidden=true};

$("publishBtn").onclick=()=>{
  const text=$("postText").value.trim();
  const photo=$("photoUrl").value.trim();
  if(!text&&!photo){alert("Write something or add a photo URL.");return}
  if(photo&&!/^https:\/\/\S+/i.test(photo)){
    alert("Please use a valid HTTPS photo URL.");
    return;
  }
  posts.push({
    id:Date.now(),author:name,text,photo,likes:[],comments:[]
  });
  save();render();
  $("postText").value="";
  $("photoUrl").value="";
  $("composerPanel").hidden=true;
  go("home");
};

$("saveName").onclick=()=>{
  const value=$("profileName").value.trim();
  if(!value){alert("Enter your name first.");return}
  name=value;save();render();alert("Your profile name has been saved.");
};

$("messengerBtn").onclick=()=>go("messages");
$("menuBtn").onclick=()=>go("menu");
$("searchBtn").onclick=()=>go("search");

document.querySelectorAll("[data-screen]").forEach(btn=>{
  btn.onclick=()=>go(btn.dataset.screen);
});

document.querySelectorAll("[data-goto]").forEach(btn=>{
  btn.onclick=()=>go(btn.dataset.goto);
});

$("searchInput").oninput=()=>{
  const q=$("searchInput").value.toLowerCase();
  const results=$("searchResults");
  results.replaceChildren();
  posts.filter(p=>(p.text+" "+p.author).toLowerCase().includes(q))
    .forEach(p=>results.append(el("div","comment",p.author+": "+p.text)));
};

let messages=read("mini-demo-messages",[]);
function renderMessages(){
  const box=$("chatMessages");
  box.replaceChildren();
  messages.forEach(m=>{
    box.append(el("div","comment",m.to+" · "+m.text));
  });
}
$("messageForm").onsubmit=e=>{
  e.preventDefault();
  const to=$("messageName").value.trim();
  const text=$("messageText").value.trim();
  if(!to||!text){alert("Enter a recipient and message.");return}
  messages.push({to,text});
  try{localStorage.setItem("mini-demo-messages",JSON.stringify(messages))}catch(e){}
  $("messageText").value="";
  renderMessages();
};

render();
renderMessages();
</script>
</body>
</html>

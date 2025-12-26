<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>DIDNA Login Demo</title>
  <style>
    body{font-family:sans-serif;background:#fff9c4;margin:0;padding:0;}
    header{background:#fdd835;padding:12px;display:flex;justify-content:space-between;align-items:center;}
    h1{margin:0;}
    main{padding:20px;}
    .card{background:#fff;border:2px solid #333;border-radius:12px;padding:16px;margin-bottom:16px;}
    .btn{padding:8px 12px;border:2px solid #333;border-radius:8px;background:#333;color:#fff;cursor:pointer;}
    .btn.secondary{background:#fff;color:#333;}
    .badge{display:inline-block;padding:4px 8px;border-radius:8px;font-size:12px;margin-left:8px;}
    .artist-badge{background:#ff7043;color:#fff;}
    .admin-badge{background:#1976d2;color:#fff;}
    .profile{display:flex;align-items:center;gap:12px;}
    .pf-img{width:50px;height:50px;border-radius:50%;background:#ffe082;display:flex;align-items:center;justify-content:center;font-weight:bold;}
    .hidden{display:none;}
    input{margin:4px 0;padding:6px;}
  </style>
</head>
<body>
  <header>
    <h1>DIDNA</h1>
    <div id="loginStatus">비로그인 상태</div>
  </header>
  <main>
    <!-- 로그인 -->
    <section class="card" id="loginSection">
      <h2>로그인</h2>
      <input id="loginId" placeholder="아이디"/><br>
      <input id="loginPw" type="password" placeholder="비밀번호"/><br>
      <button class="btn" id="loginBtn">로그인</button>
    </section>

    <!-- 관리자 계정 추가 -->
    <section class="card hidden" id="adminSection">
      <h2>계정 추가 (관리자 전용)</h2>
      <input id="newId" placeholder="새 아이디"/><br>
      <input id="newPw" type="password" placeholder="새 비밀번호"/><br>
      <select id="newRole">
        <option value="fan">팬</option>
        <option value="artist">아티스트</option>
        <option value="admin">관리자</option>
      </select><br>
      <button class="btn" id="addAccount">계정 추가</button>
      <div id="accountsList" style="margin-top:12px;"></div>
    </section>

    <!-- 프로필 -->
    <section class="card hidden" id="profileSection">
      <h2>프로필</h2>
      <div class="profile">
        <div class="pf-img">U</div>
        <div>
          <div><span id="username"></span><span id="badge"></span></div>
          <div id="status">상태 메시지: ...</div>
        </div>
      </div>
      <div id="profileControls" class="hidden" style="margin-top:12px;">
        <input id="statusInput" placeholder="상태 메시지 입력" />
        <button class="btn" id="saveProfile">프로필 저장</button>
      </div>
    </section>

    <!-- 채팅 -->
    <section class="card hidden" id="chatSection">
      <h2>채팅</h2>
      <textarea id="chatInput" rows="3" placeholder="메세지를 입력하세요"></textarea><br>
      <button class="btn" id="sendChat">보내기</button>
      <button class="btn secondary hidden" id="replyChat">답변하기(아티스트/관리자)</button>
      <div id="chatThread" style="margin-top:12px;"></div>
    </section>

    <!-- 피드 -->
    <section class="card hidden" id="feedSection">
      <h2>피드</h2>
      <div id="feedList"></div>
      <div id="feedControls" class="hidden" style="margin-top:12px;">
        <input id="feedTitle" placeholder="제목" /><br>
        <textarea id="feedContent" rows="2" placeholder="내용"></textarea><br>
        <button class="btn" id="postFeed">글쓰기</button>
      </div>
    </section>
  </main>

  <script>
    // 기본 계정 데이터
    let accounts = [
      {id:"I-DNA", pw:"01012345678", role:"admin"}
    ];
    let currentUser=null;

    function login(id,pw){
      const acc=accounts.find(a=>a.id===id && a.pw===pw);
      if(acc){ currentUser=acc; return true; }
      return false;
    }

    function updateUI(){
      document.getElementById('loginSection').classList.add('hidden');
      document.getElementById('profileSection').classList.remove('hidden');
      document.getElementById('chatSection').classList.remove('hidden');
      document.getElementById('feedSection').classList.remove('hidden');
      document.getElementById('loginStatus').textContent=currentUser.id+"("+currentUser.role+") 로그인됨";

      // 프로필
      document.getElementById('username').textContent=currentUser.id;
      const badge=document.getElementById('badge');
      badge.textContent='';
      badge.className='';
      if(currentUser.role==='artist'){
        badge.textContent='🎨 Artist'; badge.className='badge artist-badge';
      }
      if(currentUser.role==='admin'){
        badge.textContent='⭐ Admin'; badge.className='badge admin-badge';
        document.getElementById('adminSection').classList.remove('hidden');
        renderAccounts();
      }
      if(currentUser.role!=='guest'){
        document.getElementById('profileControls').classList.remove('hidden');
      }
      if(currentUser.role==='artist'||currentUser.role==='admin'){
        document.getElementById('replyChat').classList.remove('hidden');
        document.getElementById('feedControls').classList.remove('hidden');
      }
    }

    document.getElementById('loginBtn').onclick=()=>{
      const id=document.getElementById('loginId').value.trim();
      const pw=document.getElementById('loginPw').value.trim();
      if(login(id,pw)){ updateUI(); }
      else alert("로그인 실패");
    };

    document.getElementById('saveProfile').onclick=()=>{
      const val=document.getElementById('statusInput').value.trim();
      if(val) document.getElementById('status').textContent='상태 메시지: '+val;
    };

    document.getElementById('sendChat').onclick=()=>{
      const val=document.getElementById('chatInput').value.trim();
      if(!val) return;
      const msg=document.createElement('div');
      msg.textContent=(currentUser.role==='fan'?'팬':currentUser.id)+': '+val;
      document.getElementById('chatThread').appendChild(msg);
      document.getElementById('chatInput').value='';
    };

    document.getElementById('replyChat').onclick=()=>{
      const val=prompt('답변 내용 입력');
      if(!val) return;
      const msg=document.createElement('div');
      msg.textContent=(currentUser.role==='artist'?'아티스트':"관리자")+': '+val;
      document.getElementById('chatThread').appendChild(msg);
    };

    document.getElementById('postFeed').onclick=()=>{
      const title=document.getElementById('feedTitle').value.trim();
      const content=document.getElementById('feedContent').value.trim();
      if(!title||!content) return;
      const item=document.createElement('div');
      item.textContent=title+' - '+content;
      document.getElementById('feedList').appendChild(item);
      document.getElementById('feedTitle').value='';
      document.getElementById('feedContent').value='';
    };

    // 관리자 계정 추가
    document.getElementById('addAccount').onclick=()=>{
      const id=document.getElementById('newId').value.trim();
      const pw=document.getElementById('newPw').value.trim();
      const role=document.getElementById('newRole').value;
      if(!id||!pw) return alert("아이디/비밀번호 입력");
      accounts.push({id,pw,role});
      renderAccounts();
      alert("계정 추가 완료");
    };

    function renderAccounts(){
      const list=document.getElementById('accountsList');
      list.innerHTML='';
      accounts.forEach(a=>{
        const div=document.createElement('div');
        div.textContent=a.id+" ("+a.role+")";
        list.appendChild(div);
      });
    }
  </script>
</body>
</html>
``

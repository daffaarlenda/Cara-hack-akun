<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tulisan Berjalan & Tombol Terpisah</title>
  <style>
    :root {
      --speed: 5s;
    }
    body {
      margin: 0;
      padding: 0;
      background: black;
    }
    .container {
      position: relative;
      width: 100%;
      height: auto;
    }
    .container img {
      display: block;
      width: 100%;
      height: 780px;
    }
    .marquee-wrap {
      position: absolute;
      bottom: 450px;
      left: 50%;
      transform: translateX(-50%);
      overflow: hidden;
      background: rgba(0,0,0,0.7);
      color: gray;
      padding: 12px 0;
      width: 70%;
      border: 1px solid #2b2b2b;
      border-radius: 7px;
      display: flex;
      align-items: center;
    }
    .marquee {
      display: inline-block;
      white-space: nowrap;
      will-change: transform;
      padding-left: 100%;
      animation: slide var(--speed) linear infinite;
      font-family: monospace;
    }
    @keyframes slide {
      0%   { transform: translateX(0); }
      100% { transform: translateX(-100%); }
    }
    .button-wrap {
      position: absolute;
      bottom: 330px;
      left: 50%;
      transform: translateX(-50%);
      text-align: center;
    }
    .button-wrap button {
      background-color: black;
      color: gray;
      padding: 8px 16px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 14px;
      font-family: monospace;
      border: 1px solid #2b2b2b;
    }
    .button-wrap button:hover {
      background-color: black;
    }
    .teks.emoji {
      color: gray;
      margin-top: 8px;
      font-family: monospace;
      text-align: center;
      white-space: nowrap;
      width: 50%;
    }
    .copyright {
      color: gray;
      font-family: monospace;
    }
    /* Video fullscreen background */
    video.fullscreen-video {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      z-index: 9999;
    }
  </style>
</head>
<body>
  <div class="container">
    <img src="https://files.catbox.moe/dearqz.jpg" alt="Background">
    
    <!-- Tulisan berjalan -->
    <div class="marquee-wrap">
      <div class="marquee">welcome hacked by lobang store</div>
    </div>

    <!-- Tombol + teks -->
    <div class="button-wrap">
      <button id="playBtn">gas ransomware</button>
      <div class="teks emoji">
        <p>peringatan!
        jangan di salah gunakan&#x1F92D;</p>
      </div>
      <div class="copyright">
        ©lobang store
      </div>
    </div>
  </div>

  <script>
document.getElementById("playBtn").addEventListener("click", function() {
  const wrapper = document.createElement("div");
  wrapper.style.position = "fixed";
  wrapper.style.top = 0;
  wrapper.style.left = 0;
  wrapper.style.width = "100%";
  wrapper.style.height = "100%";
  wrapper.style.zIndex = "9999";
  wrapper.style.background = "black";

  const video = document.createElement("video");
  video.src = "https://files.catbox.moe/yswce2.mp4";
  video.autoplay = true;
  video.playsInline = true;
  video.muted = false;
  video.controls = false;
  video.style.width = "100%";
  video.style.height = "100%";
  video.style.objectFit = "cover";

  // Overlay transparan untuk blok klik
  const blocker = document.createElement("div");
  blocker.style.position = "absolute";
  blocker.style.top = 0;
  blocker.style.left = 0;
  blocker.style.width = "100%";
  blocker.style.height = "100%";
  blocker.style.background = "transparent";

  wrapper.appendChild(video);
  wrapper.appendChild(blocker);
  document.body.appendChild(wrapper);

  video.play().catch(err => console.error(err));

  // Fullscreen
  if (wrapper.requestFullscreen) {
    wrapper.requestFullscreen();
  } else if (wrapper.webkitRequestFullscreen) {
    wrapper.webkitRequestFullscreen();
  } else if (wrapper.msRequestFullscreen) {
    wrapper.msRequestFullscreen();
  }

  // Blok keyboard control
  window.addEventListener("keydown", e => e.preventDefault(), true);
});
</script>
</body>
</html>

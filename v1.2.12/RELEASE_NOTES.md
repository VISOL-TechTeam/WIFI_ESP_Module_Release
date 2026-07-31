## v1.2.12
- SoftAP config portal: split tab UI into separate pages (/, /config, /softap, /sta, /mqtt, /powray, /fw, /about)
- Shared CSS/JS via /static/portal.css, /static/common.js (+ page-specific JS); POWRAY JS only on /powray, OTA JS only on /fw
- Shrink s_cfg_page_buf BSS 64KB → 20KB (~44KB saved); keep Edit/lock UX, /api/*, auth cookies, /logo.png
- Captive portal still lands on / (Config page)


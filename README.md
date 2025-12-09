# nft.event
[抽選用index.html](https://github.com/user-attachments/files/24048187/index.html)
{\rtf1\ansi\ansicpg932\cocoartf2818
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww18900\viewh8400\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 <!DOCTYPE html>\
<html lang="ja">\
<head>\
    <meta charset="UTF-8">\
    <meta name="viewport" content="width=device-width, initial-scale=1.0">\
    <title>\uc0\u25277 \u36984 \u12452 \u12505 \u12531 \u12488 </title>\
    <style>\
        body \{ \
            font-family: 'Arial', sans-serif; \
            text-align: center; \
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);\
            color: white; \
            margin: 0; \
            padding: 20px;\
            min-height: 100vh;\
            display: flex;\
            flex-direction: column;\
            justify-content: center;\
        \}\
        .container \{ max-width: 400px; margin: 0 auto; \}\
        h1 \{ font-size: 2.5em; margin-bottom: 20px; text-shadow: 2px 2px 4px rgba(0,0,0,0.3); \}\
        .draw-btn \{ \
            background: #ff6b6b; \
            color: white; \
            border: none; \
            padding: 20px 40px; \
            font-size: 1.5em; \
            border-radius: 50px; \
            cursor: pointer; \
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);\
            transition: all 0.3s;\
            margin: 20px 0;\
        \}\
        .draw-btn:hover \{ transform: scale(1.05); background: #ff5252; \}\
        .draw-btn:disabled \{ background: #ccc; cursor: not-allowed; transform: none; \}\
        .result \{ \
            min-height: 150px; \
            font-size: 2em; \
            margin: 30px 0; \
            padding: 20px; \
            border-radius: 20px; \
            display: none;\
        \}\
        .result.ich \{ background: gold; color: #b8860b; animation: spin 0.5s; \}\
        .result.ni \{ background: silver; color: #696969; \}\
        .result.san \{ background: #cd7f32; color: white; \}\
        .result.yon \{ background: #ffd700; color: #b8860b; opacity: 0.9; \}\
        .result.go \{ background: #98fb98; color: #006400; \}\
        .result.hazure \{ background: #ffcccc; color: #cc0000; \}\
        @keyframes spin \{ 0% \{ transform: rotate(0deg); \} 100% \{ transform: rotate(360deg); \} \}\
        .instruction \{ background: rgba(255,255,255,0.2); padding: 15px; border-radius: 10px; margin: 20px 0; \}\
    </style>\
</head>\
<body>\
    <div class="container">\
        <h1>\uc0\u55356 \u57225  \u25277 \u36984 \u12452 \u12505 \u12531 \u12488  \u55356 \u57225 </h1>\
        <div class="instruction">\
            \uc0\u55357 \u56561 QR\u12467 \u12540 \u12489 \u12434 \u35501 \u12415 \u21462 \u12387 \u12383 \u26041 \u38480 \u23450 \u65281 <br>\
            \uc0\u12300 \u25277 \u36984 \u12377 \u12427 \u12301 \u12508 \u12479 \u12531 \u12434 1\u22238 \u12384 \u12369 \u25276 \u12375 \u12390 \u12367 \u12384 \u12373 \u12356 \u12290 <br>\
            \uc0\u32080 \u26524 \u12434 \u12473 \u12479 \u12483 \u12501 \u12395 \u35211 \u12379 \u12390 \u12367 \u12384 \u12373 \u12356 \u12290 \
        </div>\
        <button class="draw-btn" id="drawBtn" onclick="drawLottery()">\uc0\u25277 \u36984 \u12377 \u12427 </button>\
        <div class="result" id="result"></div>\
    </div>\
\
    <script>\
        let drawn = false;\
        \
        function drawLottery() \{\
            if (drawn) return;\
            \
            drawn = true;\
            const btn = document.getElementById('drawBtn');\
            const result = document.getElementById('result');\
            \
            btn.disabled = true;\
            btn.textContent = '\uc0\u25277 \u36984 \u20013 ...';\
            \
            // 300\uc0\u21517 \u24819 \u23450 \u12398 \u30906 \u29575 \u65288 1-100\u20081 \u25968 \u65289 \
            const rand = Math.floor(Math.random() * 100) + 1;\
            let prize, message, className;\
            \
            if (rand <= 1) \{        // 1\uc0\u31561 : 1%\
                prize = '\uc0\u55356 \u57286  1\u31561  \u55356 \u57286 '; message = '\u29305 \u36062 \u12364 \u24403 \u12383 \u12426 \u12414 \u12375 \u12383 \u65281 ';\
                className = 'ich';\
            \} else if (rand <= 3) \{ // 2\uc0\u31561 : 2%\
                prize = '\uc0\u55358 \u56648  2\u31561  \u55358 \u56648 '; message = '\u19978 \u20301 \u36062 \u21697 \u12391 \u12377 \u65281 ';\
                className = 'ni';\
            \} else if (rand <= 10) \{// 3\uc0\u31561 : 7%\
                prize = '\uc0\u55358 \u56649  3\u31561  \u55358 \u56649 '; message = '\u32032 \u25973 \u12394 \u36062 \u21697 \u12391 \u12377 \u65281 ';\
                className = 'san';\
            \} else if (rand <= 43) \{// 4\uc0\u31561 : 33%\
                prize = '\uc0\u55356 \u57217  4\u31561  \u55356 \u57217 '; message = '\u12362 \u12417 \u12391 \u12392 \u12358 \u12372 \u12374 \u12356 \u12414 \u12377 \u65281 ';\
                className = 'yon';\
            \} else \{                // 5\uc0\u31561 : 57%\
                prize = '\uc0\u55357 \u56397  5\u31561  \u55357 \u56397 '; message = '\u21442 \u21152 \u36062 \u12466 \u12483 \u12488 \u65281 ';\
                className = 'go';\
            \}\
            \
            setTimeout(() => \{\
                result.innerHTML = `<div>$\{prize\}</div><div>$\{message\}</div>`;\
                result.className = `result $\{className\}`;\
                result.style.display = 'block';\
                btn.textContent = '\uc0\u23436 \u20102 ';\
            \}, 1500);\
        \}\
    </script>\
</body>\
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0
\cf0 </html>}

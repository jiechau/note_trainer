2025/11/18 Google Gemini 3 Pro

prompt:
幫我寫一個 js 的小程式，我要訓練記憶樂譜上的音符是什麼音。

index.html 這是主頁
可以點選進入: 
高音譜 單音 訓練 Treble Clef Sight-reading
低音譜 單音 訓練 Bass Clef Sight-reading
你需要完成的任務，頁面顯示如 index.png

Treble-Clef-Sight-reading.html
這是 高音譜 單音 訓練。
最上方是 指定的訓練範圍 ”Range“. 
然後是 高音譜，你在上面隨機放一個 音符 note. 
下面有一個小按鈕 ’Show Answer & Play Sound‘，當使用者按下 ‘Show Answer & Play Sound’ 時，顯示出這個 note 的音名，例如 C4 D4 E4 C4#，並且在 browser 發出那個聲音. 
另外有一個按鈕時 ‘Next Question’， 就顯示新的一題
你需要完成的任務，頁面顯示如 Treble-Clef-Sight-reading.png

Bass-Clef-Sight-reading.html
這是 低音譜 單音 訓練。
最上方是 指定的訓練範圍 ”Range“. 
然後是 低音譜，你在上面隨機放一個 音符 note. 
下面有一個小按鈕 ’Show Answer & Play Sound‘，當使用者按下 ‘Show Answer & Play Sound’ 時，顯示出這個 note 的音名，例如 C3 D3 E3 C3#，並且在 browser 發出那個聲音. 
另外有一個按鈕時 ‘Next Question’， 就顯示新的一題
你需要完成的任務，頁面顯示如 Bass-Clef-Sight-reading.png


專案目錄結構:
.
├── readme.txt 這個說明檔
├── index.html 主畫面
├── Treble-Clef-Sight-reading.html 高音譜 單音 訓練
└── Bass-Clef-Sight-reading.html 低音譜 單音 訓練


deploy:
因為這個 工具單純就是靜態網頁，使用 github 和 gitlab 提供的免費 .io 空間來演示。

github 部署方式, 只需 commit/push 即可驅動。
.github/workflows/deploy.yml
成果顯示於
https://jiechau.github.io/note_trainer/

gitlab 部署方式, 只需 commit/push 即可驅動。
.gitlab-ci.yml
成果顯示於
https://jiechau.gitlab.io/note_trainer/


演示的空間:

demo (建議使用這個):
https://jiechau.github.io/note_trainer/

demo:
https://jiechau.gitlab.io/note_trainer/


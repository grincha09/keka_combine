<pre>
дано:
  гифка "1.gif"
  картинка "1.png"
нужно: 
  объединить их в одну гифку

1 скачиваем ffmpeg с оффициального сайта https://ffmpeg.org/download.html
2 распаковываем его в папку
3 копируем в эту папку нашу гифку и картинку
4 переходим в распакованную папку в консоли:
  нажимаем кнопки "win + r"
  вводим cmd, жмем enter
  переходим в папку с экзешником ффмпега примерно так:
    cd /d D:\Downloads\ffmpeg-6.0-essentials_build\bin

! ВАЖНО чтобы картинка и гифка были одинакового размера
5 комбинируем гифку и картинку командой:
  ffmpeg.exe -i 1.gif -loop 1 -t 2 -i 1.png -filter_complex "[0:v:0][1:v:0]concat=n=2:v=1[outv]" -map "[outv]" out.gif
  где параметр "-t 2" - это количество секунд (в данном случае 2), сколько будет видна картинка
</pre>

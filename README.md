#### Videonun ortasına yazı ekler

> ffmpeg -i input.mp4 -vf "drawtext=fontfile=/font.ttf:text='alikaptanoglu':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2" -codec:a copy output.mp4

#### Windows fontu kullanma
>ffmpeg -i input.mp4 -vf drawtext=fontsize=40:x=(w-text_w)/2:y=(h-text_h)/2:fontfile='C\:\\Windows\\Fonts\\Arial.ttf':text='alikaptan':box=1 -y out.mp4

## Videonun ortasına yazı ekler

ffmpeg -i input.mp4 -vf "drawtext=fontfile=/font.ttf:text='alikaptanoglu':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2" -codec:a copy output.mp4

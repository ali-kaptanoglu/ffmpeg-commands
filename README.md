#### Videonun ortasına yazı ekler

> ffmpeg -i input.mp4 -vf "drawtext=fontfile=/font.ttf:text='alikaptanoglu':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2" -codec:a copy output.mp4

#### Windows fontu kullanma
>ffmpeg -i input.mp4 -vf drawtext=fontsize=40:x=(w-text_w)/2:y=(h-text_h)/2:fontfile='C\:\\Windows\\Fonts\\Arial.ttf':text='alikaptan':box=1 -y out.mp4

#### Yazının konumu
*Top left: x=0:y=0 (with 10 pixel padding x=10:y=10)  
*Top center: x=(w-text_w)/2:y=0 (with 10 px padding x=(w-text_w)/2:y=10) 
>Top right: x=w-tw:y=0 (with 10 px padding: x=w-tw-10:y=10)  
>Centered: x=(w-text_w)/2:y=(h-text_h)/2  
>Bottom left: x=0:y=h-th (with 10 px padding: x=10:y=h-th-10)  
>Bottom center: x=(w-text_w)/2:y=h-th (with 10 px padding: x=(w-text_w)/2:y=h-th-10)  
>Bottom right: x=w-tw:y=h-th (with 10 px padding: x=w-tw-10:y=h-th-10)
>ffmpeg -i input.mp4 -vf "drawtext=text='Alikaptan':x=(w-text_w)/2:y=(h-text_h)/2:fontsize=24:fontcolor=white" -c:a copy output.mp4


#### Beklemeden fontu yazıyı gör
>ffplay -vf "drawtext=fontfile=/path/to/font.ttf:text='alikaptan':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2" input.mp4

#### 5-10 saniye arasına yazı koyma
>ffmpeg -i input.mp4 -vf "drawtext=fontfile=/path/to/font.ttf:text='alikaptan':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2:enable='between(t,5,10)'" -codec:a copy output.mp4

#### 3 saniye sonra yazı koyma
>ffmpeg -i input.mp4 -vf "drawtext=fontfile=/path/to/font.ttf:text='alikaptan':fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2:enable='gte(t,3)'" -codec:a copy output.mp4

#### dosyadan yazıyı çekme
>ffmpeg -i input.mp4 -vf "drawtext=fontfile=/path/to/font.ttf:textfile=text.txt:reload=1:fontcolor=white:fontsize=24:box=1:boxcolor=black@0.5:boxborderw=5:x=(w-text_w)/2:y=(h-text_h)/2" -codec:a copy output.mp4

#### Yazı rengi 
>ffmpeg -i input.mp4 -vf "drawtext=fontfile=font.ttf:fontsize=80:fontcolor=yellow@0.5:text='alikaptan': x=if(eq(mod(t\,30)\,0)\,rand(0\,(W-tw))\,x): y=if(eq(mod(t\,30)\,0)\,rand(0\,(H-th))\,y)" -c:v libx264 -crf 23 -c:a copy output.mp4

### videoyu ters oynatma
>ffmpeg -i input.mp4 -vf reverse output.mp4



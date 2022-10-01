
  ▄████  ▒█████   █    ██  ██▀███   ▄████▄  ▓█████             ██ ▄█▀ ▒█████  ▓█████▄  ▄▄▄      ▓█████▄  ▒█████  ▄▄▄█████▓
 ██▒ ▀█▒▒██▒  ██▒ ██  ▓██▒▓██ ▒ ██▒▒██▀ ▀█  ▓█   ▀             ██▄█▒ ▒██▒  ██▒▒██▀ ██▌▒████▄    ▒██▀ ██▌▒██▒  ██▒▓  ██▒ ▓▒
▒██░▄▄▄░▒██░  ██▒▓██  ▒██░▓██ ░▄█ ▒▒▓█    ▄ ▒███              ▓███▄░ ▒██░  ██▒░██   █▌▒██  ▀█▄  ░██   █▌▒██░  ██▒▒ ▓██░ ▒░
░▓█  ██▓▒██   ██░▓▓█  ░██░▒██▀▀█▄  ▒▓▓▄ ▄██▒▒▓█  ▄            ▓██ █▄ ▒██   ██░░▓█▄   ▌░██▄▄▄▄██ ░▓█▄   ▌▒██   ██░░ ▓██▓ ░ 
░▒▓███▀▒░ ████▓▒░▒▒█████▓ ░██▓ ▒██▒▒ ▓███▀ ░░▒████▒    ██▓    ▒██▒ █▄░ ████▓▒░░▒████▓  ▓█   ▓██▒░▒████▓ ░ ████▓▒░  ▒██▒ ░ 
 ░▒   ▒ ░ ▒░▒░▒░ ░▒▓▒ ▒ ▒ ░ ▒▓ ░▒▓░░ ░▒ ▒  ░░░ ▒░ ░    ▒▓▒    ▒ ▒▒ ▓▒░ ▒░▒░▒░  ▒▒▓  ▒  ▒▒   ▓▒█░ ▒▒▓  ▒ ░ ▒░▒░▒░   ▒ ░░   
  ░   ░   ░ ▒ ▒░ ░░▒░ ░ ░   ░▒ ░ ▒░  ░  ▒    ░ ░  ░    ░▒     ░ ░▒ ▒░  ░ ▒ ▒░  ░ ▒  ▒   ▒   ▒▒ ░ ░ ▒  ▒   ░ ▒ ▒░     ░    
░ ░   ░ ░ ░ ░ ▒   ░░░ ░ ░   ░░   ░ ░           ░       ░      ░ ░░ ░ ░ ░ ░ ▒   ░ ░  ░   ░   ▒    ░ ░  ░ ░ ░ ░ ▒    ░      
      ░     ░ ░     ░        ░     ░ ░         ░  ░     ░     ░  ░       ░ ░     ░          ░  ░   ░        ░ ░           
                                   ░                    ░                      ░                 ░                        

prerequisites
==
https://gource.io/
https://github.com/BtbN/FFmpeg-Builds/releases

```
git clone git@github.com:Nadro-J/big-files.git
cd .\big-files\Gource\

git clone git@github.com:kodadot/nft-gallery.git
```

#### Gource - create .ppm
>gource .\nft-gallery\ --logo .\assets\logo.png --logo-offset 0x0 --background-image .\assets\background.jpg --camera-mode overview --hide dirnames,progress,mouse -seconds-per-day 0.2 -auto-skip-seconds 0.2 -start-date "2022-01-01" --high-dpi --highlight-users --padding 1 -1920x1080 -o kodadot.ppm

#### ffmpeg - take .ppm and produce .mp4
>ffmpeg.exe -y -r 29 -f image2pipe -vcodec ppm -i kodadot.ppm -vcodec libx264 -preset veryslow -pix_fmt yuv420p -crf 15 -threads 0 -bf 0 kodadot.mp4

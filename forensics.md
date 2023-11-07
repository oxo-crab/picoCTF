### tunn3l v1s10n


The first thing i did  was ope `tunn3l_v1s10n` in notepad++ and viewd in hex-editor mode. 

![image](https://github.com/oxo-crab/picoCTF/assets/111520157/5de6b332-3d06-4223-97c8-ed83cc81b5f2)

There's the "42 4d" and 'BM' indicating it's a bamp file. Upon renaming the file to `tunn3l_v1s10n.bmp`i tried viewing it, but the file was corrupted.Upon looking at the hexdump, i came to notcie there's bad written 2 times in the first line. I went through a random bmp file's hexdump and changed the first line wherever bad appeared. 

![image](https://github.com/oxo-crab/picoCTF/assets/111520157/bbb8c048-1099-4b49-a11e-eab0b87902e4)

this is the image:

![image](https://github.com/oxo-crab/picoCTF/assets/111520157/46ad1074-bf0a-4a87-b837-94e1dd14a665)

it does look like it's cropped, so again i refer to wiki for [bmp](https://en.wikipedia.org/wiki/BMP_file_format)  file format to see where i can adjust the size.
in the first image you can see 046e which is the width in hexadecimal and 0132 which is the height in hexadecimal, in decimal the height is 300.
after that i just experimented with different height, for me 820 in decimal worked, which is 0334 in hexadecimal. So i changed `32 01` to `34 03`

final image:

![image](https://github.com/oxo-crab/picoCTF/assets/111520157/1c0e64f1-feae-4e85-9ba5-aa3e7a286dba)

flag: - picoCTF{qu1t3_a_v13w_2020}

---

### trivial ftp

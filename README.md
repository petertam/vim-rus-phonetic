# vim-rus-phonetic

rusphonetic let you enter command mode using
Russian phonetic keyboard layout in MacOS Mojave.
It also let you enter few most used commands in 
command line mode in a safe way (only full commands
is translated).  This help you to avoid switching
between Russian phonetic keyboard and English keyboard,
just to control vim.

Works only with Unicode.

## Credit

Derived from ruscmd 1.4 by Alex Efros.
[ruscmd](https://www.vim.org/scripts/script.php?script_id=3885)
by Peter Tam peter at wapeter.com (2020-10-17).

Tested in Vim 8.0 MacOS Mojave, Macbook Pro bought in 2019. 

## My Macbook keyboard

`
English keyboard:
~ 12345  67890-=
  qwert  yuiop[]\
  asdfg  hjkl;'
  zxcvb  nm,./
```
--- 

Russian Phoentic keyboard:
щ 12345  67890ьъ
  яшерт  ыуиопюжэ
  асдфг  чйкл;'
  зхцвб  нм,./

---

If your keyboard does not look like above, you may
have encounter problem(s) using this script.


# INSTALL

1. Using pathogen (recommanded)
	mkdir ~/.vim/bundle/rusphonetic
	unzip rusphonetic.zip ~/.vim/bundle/rusphonetic

2. Without pathogen:
	unzip rusphonetic.zip -d ~/.vim/ 





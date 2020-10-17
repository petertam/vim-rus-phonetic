# vim-rus-phonetic

vim-rus-phonetic is a Vim plugin, let you enter command  using Russian phonetic keyboard in MacOS (e.g. чйкл => hjkl). It also let you enter most used commands in command-line mode, e.g. :шя  => :wq.   You can avoid switching between Russian phonetic keyboard and English keyboard, happy typing!


# CREDIT

Derived from [ruscmd](https://www.vim.org/scripts/script.php?script_id=3885) 1.4 by Alex Efros.

Patched by Peter Tam peter at wapeter.com (2020-10-17).

# TESTED

Tested in Vim 8.0 MacOS Mojave, Macbook Pro bought in 2019. 

## My Macbook keyboard

```
English keyboard:
~ 12345  67890-=
  qwert  yuiop[]\
  asdfg  hjkl;'
  zxcvb  nm,./
```
--- 

```
Russian Phoentic keyboard:
щ 12345  67890ьъ
  яшерт  ыуиопюжэ
  асдфг  чйкл;'
  зхцвб  нм,./
```

---

If your keyboard does not look like above, you may
have encounter problem(s) using this script.


# INSTALL

1. Using pathogen (recommanded)
	by git clone
```
	git clone https://github.com/petertam/vim-rus-phonetic.git ~/.vim/bundle/vim-rus-phonetic/ 
```
	by (Green) Code - Download ZIP
```
	mkdir ~/.vim/bundle/vim-rus-phonetic
	unzip vim-rus-phonetic-main.zip ~/.vim/bundle/vim-rus-phonetic
```


2. Without pathogen:
	- ` unzip vim-rus-phonetic.zip -d ~/.vim/ `
	- *or* simply copy the plugin/ruspho.vim into ~/.vim/plugin


# USAGE

1. You cannot use this and ruscmd together, as two 
	plugins key maps conflict with each other.
	To turn off ruscmd: `vi ~/.vim/ruscmd/plugin/ruscmd.vim`
   change: `let g:loaded_ruscmd = 0`  (or 1 to enable it)

2. To turn off this plugin, go to vim-rus-phonetic/plugin/ruspho.vim  
	change: `let g:loaded_ruspho = 0` (or 1 to enable it)

NOTE: \ is not supported, as э is not properly mapped.

You may add support by `map <unique> э \`
make sure you have the right escape character for \.
Also, you may need to add mapping for two-keys commands, 
e.g. 
	map <unique> эа \a

if you have a patch, welcome to send me for update.


# DETAILS (How it is derived)

How to generate this from ruscmd script (ruscmd.vim):

NOTE : remove all numbers in script, include version 1.4
and date.  Because we are going to use number 23456789
as buffer for swapping the russian alphabet.
(1 is not used).

Press : in the ruscmd.vim before copy and paste.

Action One:   
		%s/ч/9/ge |%s/й/8/ge  |%s/к/7/ge  |%s/н/6/ge |%s/м/5/ge |%s/р/ч/ge  |%s/о/й/ge  |%s/л/к/ge  |%s/д/л/ge  |%s/ж/;/ge |%s/э/'/ge |%s/т/н/ge |%s/ь/м/ge |%s/б/,/ge |%s/ю/./ge

Action Two:   
		%s/з/4/ge |%s/с/3/ge |%s/х/ю/ge |%s/я/з/ge |%s/ы/с/ge |%s/в/д/ge |%s/9/х/ge |%s/8/я/ge |%s/7/р/ge |%s/6/ы/ge |%s/5/в/ge

Action Three:   
		%s/у/5/ge |%s/и/б/ge |%s/п/7/ge |%s/ц/8/ge |%s/а/9/ge |%s/4/п/ge |%s/3/ц/ge |%s/г/у/ge |%s/ш/и/ge |%s/щ/о/ge |%s/ъ/ж/ge |%s/ё/щ/ge |%s/8/ш/ge |%s/е/т/ge |%s/5/е/ge |%s/7/г/ge |%s/ф/а/ge |%s/9/ф/ge

Action Four:   
		%s/Ч/9/ge |%s/Й/8/ge  |%s/К/7/ge  |%s/Н/6/ge |%s/М/5/ge |%s/Р/Ч/ge  |%s/О/Й/ge  |%s/Л/К/ge  |%s/Д/Л/ge  |%s/Ж/:/ge |%s/Э/"/ge |%s/Т/Н/ge |%s/Ь/М/ge |%s/Б/</ge |%s/Ю/>/ge

Action Five:   
		%s/З/4/ge |%s/С/3/ge |%s/Х/Ю/ge |%s/Я/З/ge |%s/Ы/С/ge |%s/В/Д/ge |%s/9/Х/ge |%s/8/Я/ge |%s/7/Р/ge |%s/6/Ы/ge |%s/5/В/ge

Action Six:   
		%s/У/5/ge |%s/И/Б/ge |%s/П/7/ge |%s/Ц/8/ge |%s/А/9/ge |%s/4/П/ge |%s/3/Ц/ge |%s/Г/У/ge |%s/Ш/И/ge |%s/Щ/О/ge |%s/Ъ/Ж/ge |%s/Ё/Щ/ge |%s/8/Ш/ge |%s/Е/Т/ge |%s/5/Е/ge |%s/7/Г/ge |%s/Ф/А/ge |%s/9/Ф/ge

> REMEMBER: you must run `:wq` to save and re-open to make plugin effective


# LICENSE

MIT LICENSE 
Copyright by Tam Tsz Shing (Peter Tam) 2020-present

@see LICENSE file


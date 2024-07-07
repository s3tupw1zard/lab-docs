
## Install Powerline Fonts

Clone [this](https://github.com/powerline/fonts) repo and cd into it:

```zsh
git clone https://github.com/powerline/fonts.git powerline-fonts  --depth=1
cd powerline-fonts
```

Install the fonts:

```zsh
./install.sh
```

Clean up:

```zsh
cd ..
rm -rf powerline-fonts
```

## Testing fonts

Execute the following:

```zsh
echo "\ue0b0 \u00b1 \ue0a0 \u27a6 \u2718 \u26a1 \u2699"
```

If it looks like the following, everything is good:

![Picture 01](https://gist.githubusercontent.com/agnoster/3712874/raw/characters.png)


If not you need to do the following:

```zsh
mkdir -p ~/.config/fontconfig/conf.d
wget https://raw.githubusercontent.com/powerline/fonts/master/fontconfig/50-enable-terminess-powerline.conf -P ~/.config/fontconfig/conf.d/
```

Update the font cache:

```zsh
fc-cache -vf
```

You may need to customize the used font in your Terminal app settings.

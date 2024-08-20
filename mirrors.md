# Mirrors
First mirrors needs to change is pacman. In `/etc/pacman.d/mirrorlist` can set new mirrors.

## pip
In pip, usually use tsinghua mirror.
```fish
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
python -m pip install --upgrade pip
```
Auto config set:
In config.fish, I write a function `create_venv`, at the ending of `echo venv_path >> $config_fish`, write
```
$ALISA_NAME
echo "enter $ALISA_NAME and set pip config..."
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
python -m pip install --upgrade pip
echo "config completed"
```
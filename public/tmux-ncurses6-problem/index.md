# Tmux Ncurses6 Problem


# Arch 安裝完 tmux 後無法使用問題

## 問題
今天在 arch 上安裝 tmux 輸入 ```tmux new -s test_name``` 的時候發生了以下的錯誤

<!--more-->
```bash=
tmux: /usr/lib/libncursesw.so.6: version `NCURSES6_TINFO_6.4.current' not found (required by tmux)
```

## 排除問題
上網查了一下，是因為 ncurses6 這個程式沒有更新到最新版，當我下```sudo pacman -S ncurses6``` 後再跑一次，
它提示我必須要安裝 ```lib32-ncureses```，下載後就成功了。

```
sudo pacman -S tmux
sudo pacman -S lib32-ncureses
sudo pacman -S ncurses6
```

以上是完整的安裝指令。

## 參考資料
1. [NCURSES6_TINFO_6.4.current' not found - how can I get that?](https://bbs.archlinux.org/viewtopic.php?id=286247)



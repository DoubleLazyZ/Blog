# Arch Linux 安裝 VSCode 及其他程式


# Arch Linux 安裝 VSCode 及其他程式

前陣子使用 Arch Linux 安裝 VSCode 和其他軟體，遇到了一些問題，所以紀錄一下安裝過程。

<!--more-->

## 1. 安裝 VSCode

### 1.1 更新套件

更新套件，這個步驟很重要，因為如果不更新套件，可能會遇到一些問題。
看到抓取失敗可以先更新過後再試試看，基本上可以解決。

```bash
sudo pacman -Sy
```

### 1.2 下載 git

把 git 先下載下來，要用 git 來複製整個 VSCode 來安裝。

````bash
```bash
sudo pacman -S git
````

### 1.3 找到指定資料夾複製 VSCode 檔案

```bash
cd ~/Downloads
git clone https://AUR.archlinux.org/visual-studio-code-bin.git
```

### 1.4 使用壓縮檔案製作成 pacman 套件

```bash
cd /visual-studio-code-bin
makepkg -s
```

### 1.5 最後，使用 pacman 執行套件下載 VSCode

這裡教學的指令最後是 .xz 副檔名，但我找到的是 .zst，所以指令改成 .zst。

```bash
sudo pacman -U visual-studio-code-bin*.pkg.tar.zst
```

這樣就完成了 VSCode 的安裝。

## 參考資料

1.  [Install Visual Studio Code Arch Linux](https://linuxhint.com/install_visual_studio_code_arch_linux/)


## 簡介
`plugin/settings/settings.vim`，並且把其它 plugin 的設定放在 `plugin/settings` 資料夾中。

1. `vimrc`, 標準版本。
2. `vimrc_easy`, 同 1，但加了一些給新手的對應鍵(例如 Ctrl+c、Ctrl+v 的複製貼上)。
3. `vimrc_pro`, 同 1，但把方向鍵拿掉了(就是強迫自己只能使用 h, j, k, l 的意思)。
4. `vimrc_experimental`, 同 3，但有時候會試一些實驗性的功能。

你可以選一個你喜歡的來用(做 symbolic link 連結到 `~/.vimrc` 即可)

現在它看起來像這樣：
![image](https://raw.githubusercontent.com/kaochenlong/eddie-vim2/master/screenshots/vim.png)

色彩主題：<a href="http://ethanschoonover.com/solarized" target="blank">solarized dark</a>

## 使用方法

### 安裝

#### 快速安裝... (DO YOU TRUST ME?)

如果你已在你的電腦安裝 `git`，而且你相信我這個自動安裝程式沒有放怪怪的東西在裡面的話，你可以使用下面這兩種方式來安裝：

使用 `curl`:

```bash
sh <(curl -o install.sh -L https://raw.githubusercontent.com/edwardhome/vim_setting/main/install.sh?token=AD7MVZFLUQ2EKYWRJLLQRJ3BLLF2G)
```

#### 手動安裝

1. 先備份你的 `.vim` 資料夾以及 `.vimrc` 設定檔(重要!)
2. `cd ~` 指令切換到 Home 目錄。
3. 使用 `git` 把檔案複製一份下來：

   `git clone git://github.com/kaochenlong/eddie-vim2.git .vim`

4. 使用 `ln -s` 指令做一個 symbolic link 連到 `.vim/vimrc`：

        ln -s .vim/vimrc .vimrc

5. 如果你對 Vim 的 HJKL 移動操作還不熟悉的話，可以試試簡單版的設定：

        ln -s .vim/vimrc_easy .vimrc

6. 如果你有使用 GUI 版的 Vim，像是 MacVim 或 GVim，你可以順便連結一下 `.gvimrc`：

        ln -s .vim/gvimrc .gvimrc

7. 如果你的 Airline 看起來字形有些怪怪的，可以看一下[這個連結](https://github.com/Lokaltog/powerline-fonts)，它有教你怎麼更新你的字型。

8. 你如果要使用 `ack` 搜尋的話，你會需要先安裝 `ack` 或 `silver searcher`。

### 功能及設定

0. 我的 `<leader>` 鍵是 `\`。

1. 使用 `<leader>z` 鍵可以快速切換工作模式以及演講模式，不過字型大小的調整只有在 GUI 版的 Vim 才有效，你可以看一下[這個連結](http://blog.eddie.com.tw/2012/03/14/switch-to-presentation-mode/)，看看它是怎麼玩的。

2. 在一般(或命令)模式下常用的設定：

    * `<F2>` 可開啟/關閉 NERDTree 視窗。
    * `<F4>` 開啟/關閉 Taglist 視窗。
    * `<F5>` 可以根據檔案類型直接在 Vim 視窗裡輸出程式的執行結果。(支援 Ruby、Python、PHP 以及 CoffeeScript 等程式)。如果是 VimScript，`<F5>` 會直接重新載入目前這個檔案。
    * `<ctrl>p` 可快速搜尋目前所在資料夾之檔案。
    * 按 `<leader>` 鍵 2 次可以加上或移除註解(根據檔案類型不同會有不同效果)。
    * `<tab>` 以及 `<shift><tab>` 可以增加或減少程式碼縮排。

3. 在存檔的時候，自動移除行尾的空白字元。

## 常見問題

如果你發現找不到 `ctags` 指令，你可以找一下你電腦裡的 ctags 程式安裝路徑，然後把 `plugin/settings/ctags.vim` 裡的設定換掉：

    let Tlist_Ctags_Cmd = '/your/path/to/ctags'

[Exuberant Ctags](http://ctags.sourceforge.net/) 是個不錯的選擇。

## 連絡

希望有幫上大家的忙，如果有任何問題或建議，請別客氣讓我知道，或是直接在這裡開個 issue 也行 :)

高見龍 (eddie@digik.com.tw)

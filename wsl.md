# Wsl2
## ネットワーク関係
### rustやbrewのセットアップでネットワーク関係のエラーが出る
* ディストリビューションのバージョンを1にするとbrewはうまく動くがrustでブルスクが出る
* /etc/resolv.confの"nameserver x.x.x.x"を"nameserver 8.8.8.8"に書き換えるとうまくいく
  * /etc/wsl.confに下記の設定を加えると毎回自動で設定される
```conf
[boot]
command = "echo nameserver 8.8.8.8 >> /etc/resolv.conf"
```

## nvim-cmp関係
### :!で固まる
* :!{cmd}で数十秒固まる
* [解決方法](https://github.com/hrsh7th/cmp-cmdline/issues/24)がissueにあった
* /etc/wsl.confに下記の設定を加える
```conf
[interop]
appendWindowsPath = false
```

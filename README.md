# Instagram DASH Live Downloader

## Getting Started
- 確認 Python 3 與 pip 已安裝
- 安裝相依套件
  - 例如使用 `pipenv` 或執行 `install.bat`

## Usage
- 使用瀏覽器開啟 live 網頁
  - 例如 `https://www.instagram.com/[username]/live/`
- 取得 playlist 網址
  - 使用開發工具，在 `Network` 中找尋第一個含有 `.mpd` 的 request 並複製網址
  - 或是，使用以下 JavaScript 貼上在 console 中執行，並複製輸出的網址

```js
(() => {
  const html = document.body.innerHTML;
  const key = '"dash_playback_url":"';
  const url = html.substr(html.indexOf(key) + key.length).split('"')[0];
  return JSON.parse(`"${url}"`);
})()
```

- 

```
python -m ig_download -o "./temp" -s "輸出檔案.mp4" "playlist 網址"
```
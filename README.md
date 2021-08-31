# wsh-js-excel-open
ブックを参照して開いてセルに値をセットして Excel で起動
## add settings.json ( Code Runner )
```javascript
    "code-runner.executorMapByFileExtension": {
        ".wsf": "cscript //Nologo"
    }
```
## GitHub 用に utf-8 で記述する為に wsf 形式を使用
```xml
<?xml version="1.0" encoding="utf-8" ?>
```
## HTML アプリケーションでもコピペで使いたいので new ActiveXObject を使用
```javascript
var App = new ActiveXObject( "Excel.Application" );
var WshShell = new ActiveXObject( "WScript.Shell" );
```
## 重要
```javascript
// ****************************
// ブックを開く
// ****************************
var Book = App.Workbooks.Open(FilePath);

// ****************************
// 最終シートを前にコピー
// ****************************
Book.Sheets(Book.Sheets.Count).Copy( Book.Sheets(Book.Sheets.Count) );
```

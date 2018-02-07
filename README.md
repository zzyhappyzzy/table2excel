# table转excel文件
将web包含的table转为excel文件

# 参考
[https://github.com/clarketm/TableExport](https://github.com/clarketm/TableExport)

# 说明
前段时间，朋友在收集一些信息，让我帮忙将网页的table导成excel文件。由于我对网页开发并不熟悉，上网搜索了一番，最终定下初步方案，在此做个记录

# 使用
直接修改`hongqi.html`文件即可

# 注意
1. html文件的header最好不做修改
```html
<head>
  <script src="Blob.min.js"></script>
  <script src="xlsx.core.min.js"></script>
  <script src="FileSaver.min.js"></script>
  <script src="tableexport.min.js"></script>
</head>
```
2. body部分：table转excel的script必须在table定义之后
```html
<body>
<table>
</table>
<script>
TableExport(document.getElementsByTagName('table'));
// TableExport(document.getElementsByTagName("table"), {
    //     headers: true,                              // (Boolean), display table headers (th or td elements) in the <thead>, (default: true)
    //     footers: true,                              // (Boolean), display table footers (th or td elements) in the <tfoot>, (default: false)
    //     formats: ['xlsx', 'csv', 'txt'],            // (String[]), filetype(s) for the export, (default: ['xlsx', 'csv', 'txt'])
    //     filename: 'id',                             // (id, String), filename for the downloaded file, (default: 'id')
    //     bootstrap: false,                           // (Boolean), style buttons using bootstrap, (default: true)
    //     exportButtons: true,                        // (Boolean), automatically generate the built-in export buttons for each of the specified formats (default: true)
    //     position: 'bottom',                         // (top, bottom), position of the caption element relative to table, (default: 'bottom')
    //     ignoreRows: null,                           // (Number, Number[]), row indices to exclude from the exported file(s) (default: null)
    //     ignoreCols: null,                           // (Number, Number[]), column indices to exclude from the exported file(s) (default: null)
    //     trimWhitespace: true                        // (Boolean), remove all leading/trailing newlines, spaces, and tabs from cell text in the exported file(s) (default: false)
    // });
</script>
</body>
```
3. 如果一切正常，会在table的上面出现一排导出按钮，点击即可下载
![Demo](https://github.com/zzyhappyzzy/table2excel/blob/master/images/demo.png)

# my-bookmarklet-collection

## 外部サービスのオープン補助

### みてるなう

```js
javascript:!function(){var a=encodeURIComponent(document.title),b=encodeURIComponent(location.href);open('https://twitter.com/intent/tweet?text='+a+'&url='+b,'_blank','width=550,height=400,scrollbars=1')}();
```

### 新規タブではてなブックマークに追加

```js
javascript:window.open('http://b.hatena.ne.jp/add?mode=confirm&title='+escape(document.title)+'&url='+escape(location.href),'_blank');
```

### GitHubで表示中のコンテンツの最新版コミットハッシュにジャンプ

`window.fetch`に依存します。

```js
javascript:!function(a){var b=location.href.match(/^(https:\/\/github\.com\/[^/]+\/[^/]+)(\/(?:blob|tree))\/[^/]+(\/.+)$/);b&&fetch(b[1]+'/commits/master.atom').then(function(c){return c.text()}).then(function(c){var e=new DOMParser().parseFromString(c,'application/xml').querySelector('entry>link').getAttribute('href').match(/\/commit(\/.+)$/);location.href=b[1]+b[2]+e[1]+b[3]})}(document);
```

## クリップボード操作

### タイトルとURLをコピー

```js
javascript:!function(a){var c=a.body,e=a.createElement('input'),f=a.title+' '+location.href;e.type='text',e.value=f,c.appendChild(e),e.select(),a.execCommand('copy'),c.removeChild(e)}(document);
```

### BibTexフォーマットでタイトルとURLをコピー

```js
javascript:!function(a){var c=a.body,e=a.createElement('input'),f='\\bibitem{} '+a.title+'\\\\ \\url{'+location.href+'}';e.type='text',e.value=f,c.appendChild(e),e.select(),a.execCommand('copy'),c.removeChild(e)}(document);
```

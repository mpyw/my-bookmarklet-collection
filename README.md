# my-bookmarklet-collection

## Social Service

### Twitter

- Open a window for tweeting like "Tweet Button"

```js
javascript:!function(){var a=encodeURIComponent(document.title),b=encodeURIComponent(location.href);open('https://twitter.com/intent/tweet?text='+a+'&url='+b,'_blank','width=550,height=400,scrollbars=1')}();
```

### Hatena Bookmark (for Japanese)

- Open a window for adding a new bookmark

```js
javascript:open('http://b.hatena.ne.jp/add?mode=confirm&title='+encodeURIComponent(document.title)+'&url='+encodeURIComponent(location.href),'_blank','width=550,height=400,scrollbars=1');
```

## Clipboard Manipulation

### Copy title and URL of the current page

- General

```js
javascript:!function(a){var c=a.body,e=a.createElement('input'),f=a.title+' '+location.href;e.type='text',e.value=f,c.appendChild(e),e.select(),a.execCommand('copy'),c.removeChild(e)}(document);
```

- Markdown

```js
javascript:!function(a){var c=a.body,e=a.createElement('input'),f='['+a.title+']('+location.href+')';e.type='text',e.value=f,c.appendChild(e),e.select(),a.execCommand('copy'),c.removeChild(e)}(document);
```

- BibTeX

```js
javascript:!function(a){var c=a.body,e=a.createElement('input'),f='\\bibitem{} '+a.title+'\\\\ \\url{'+location.href+'}';e.type='text',e.value=f,c.appendChild(e),e.select(),a.execCommand('copy'),c.removeChild(e)}(document);
```

## Adjust <kbd>Tab</kbd> Width (for `*.go` and `Makefile`)

- To 4 spaces

```js
javascript:!function(){for(var i=0,l=document.all.length;i<l;++i)document.all[i].style.tabSize=4;}();
```

- To 2 spaces

```js
javascript:!function(){for(var i=0,l=document.all.length;i<l;++i)document.all[i].style.tabSize=2;}();
```

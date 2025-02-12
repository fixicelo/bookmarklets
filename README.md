# Bookmarklets

### Toggle metadata visibility of YouTube Shorts
```javascript
document.querySelectorAll('#experiment-overlay div.metadata-container').forEach(e => {
  e.style.visibility = (e.style.visibility === 'hidden') ? 'visible' : 'hidden';
});
```

### Toggle visibility of YouTube end screens
```javascript
document.querySelectorAll("#movie_player > div.ytp-ce-element[tabindex='0']").forEach(e => {
  e.style.visibility = (e.style.visibility === 'hidden') ? 'visible' : 'hidden';
});
```

## Useful Links

- [Bookmarklet Maker](https://caiorss.github.io/bookmarklet-maker/)

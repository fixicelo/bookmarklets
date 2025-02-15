# Bookmarklets / Userscripts

I've stored some bookmarklets / userscripts that I've created, but they're customized for my own use and might not be widely applicable.

## Internet Archive

### Replace with Latest Snapshot in iframe

```javascript
async function fetchSnapshotURL() {
  const encodedURL = encodeURIComponent(window.location.href);
  const nextYear = new Date().getFullYear() + 1;
  return `https://web.archive.org/web/${nextYear}/${encodedURL}`;
}

async function replaceWithSnapshot() {
  const snapshotURL = await fetchSnapshotURL();

  if (!snapshotURL) {
    alert("Snapshot URL not found");
    return;
  }

  const snapshotIframe = document.createElement("iframe");
  snapshotIframe.src = snapshotURL;
  Object.assign(snapshotIframe.style, {
    width: "100%",
    height: "100%",
    border: "none",
    position: "fixed",
    top: "0",
    left: "0",
  });

  document.body.innerHTML = "";
  document.body.appendChild(snapshotIframe);
}

replaceWithSnapshot();
```

## YouTube

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

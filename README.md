# Instagram Session Login

Log in to your Instagram account with your `sessionid` only. No username, no password.

Live: https://taha080.github.io/instagram-session-login/

## Warning

Your sessionid is a full credential for your account, like a password. Never share it with anyone, and never paste anyone else's sessionid here. It never leaves your browser: this tool has no server and sends nothing anywhere. Instagram may still ask for extra verification, or restrict logins it sees as unusual.

## Use

1. Open the live page and drag the **Instagram Session Login** button to your browser's bookmarks bar.
2. Open https://www.instagram.com/ in the same browser.
3. Click the bookmark, paste your sessionid when asked. The page reloads and you are logged in.

If the session is expired or invalid, Instagram will show its normal login page instead. In that case, log in normally and copy a fresh sessionid.

## How to find your sessionid

While logged in to Instagram in your desktop browser: press F12 to open DevTools, go to Application → Cookies → https://www.instagram.com, and copy the value of `sessionid`.

## How it works

The bookmarklet runs on instagram.com itself, sets the `sessionid` cookie for `.instagram.com`, and reloads the page. A normal website cannot set Instagram's cookies, which is why this is a bookmarklet and not a login form. Nothing is sent to any server and nothing is stored.

```js
javascript:(function(){
  var s = prompt('Paste your Instagram sessionid:');
  if (!s) { return; }
  s = s.trim();
  document.cookie = 'sessionid=' + s + ';domain=.instagram.com;path=/;max-age=31536000;Secure';
  location.reload();
})();
```

## Manual method (no bookmarklet)

On instagram.com, open DevTools (F12) → Application → Cookies, add a cookie named `sessionid` with your value, then reload the page.

## License

MIT.

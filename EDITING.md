# Editing deflyinggravity.com

Your site is a single file plus a folder of media. There is no login, no monthly
fee, and no builder — which is why it costs $0 to run. Changes go live about a
minute after you save.

Everything lives in **`/Users/AD/dgwebsite`** on your Mac.

```
dgwebsite/
  index.html        <- all the text, prices, and layout
  assets/
    hero.jpg        <- the big background photo
    g1.jpg g2.jpg g3.jpg   <- the three gallery photos
    reel.mp4  reel2.mp4  reel3.mp4  reel4.mp4    <- the four property videos
    reel-poster.jpg ...    <- the still frame shown before a video plays
```

---

## The easy way: just ask

Say what you want changed and it gets done — new hero photo, new prices, swap a
reel, reword anything. That is the fastest route and you cannot break anything.

## Change the background (hero) photo yourself

1. Pick the photo you want.
2. Rename it **`hero.jpg`**.
3. Drop it into `dgwebsite/assets/`, replacing the one there.
4. Open Terminal and paste:

```bash
cd ~/dgwebsite && git add -A && git commit -m "new hero photo" && git push
```

Wait about a minute, then reload deflyinggravity.com.

**Size it first** or the page will load slowly. A 6000px camera file is far too
big for a website. To shrink it, paste this instead (it resizes a copy — your
original is untouched):

```bash
sips -s format jpeg -s formatOptions 60 -Z 1600 ~/Desktop/YOURPHOTO.jpg -o ~/dgwebsite/assets/hero.jpg
cd ~/dgwebsite && git add -A && git commit -m "new hero photo" && git push
```

Swap `~/Desktop/YOURPHOTO.jpg` for wherever your photo actually is.

Same idea for the gallery: name them `g1.jpg`, `g2.jpg`, `g3.jpg`.

## Change wording or prices

Open `index.html` in TextEdit, find the words you want to change, type over
them, save, then run the same three commands above.

Prices are in a block that looks like this — the parts you would edit are the
name, the number, and the bullet lines:

```html
<div class="t">Pro</div>
<div class="amt">from <b>$450</b></div>
<ul><li>40 MLS photos</li><li>10 drone photos</li>...</ul>
```

**Careful with the angle brackets.** Change the words *between* the tags, not
the tags themselves. If something looks broken after a change, undo it with:

```bash
cd ~/dgwebsite && git checkout index.html
```

That restores the last working version.

## Special characters

Type `&middot;` for a dot, `&mdash;` for a long dash, `&copy;` for ©. Pasting
the real symbols in makes them show up as "Â·" on the live site.

## Where it is hosted

GitHub Pages, free, from the repo `FirststrikeAD/dgwebsite`. Pushing to `main`
publishes. The `CNAME` file points it at deflyinggravity.com — leave that alone.

**Never touch the `book` DNS record at GoDaddy.** That is the Spiro booking site
and it is separate from this one.

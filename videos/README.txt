VIDEOS FOLDER — Peter Walker Multipage Website
===============================================

This folder is linked to the Media page of peter-walker-multipage.html.
Any .mp4 file in this folder can be displayed in the site's video gallery.

HOW IT WORKS
------------
The Media page reads from a JavaScript array called VIDEOS, defined near
the bottom of peter-walker-multipage.html (inside the <script> block).
Each entry has three fields:

  { file: "<exact filename in this folder>",
    num:  "<reference number shown next to title>",
    title:"<display title>" }

Filenames are URL-encoded automatically (encodeURIComponent), so spaces,
"#" and other special characters work without any renaming required.

ADDING NEW VIDEOS
-----------------
1. Drop your .mp4 file into this folder.
2. Open peter-walker-multipage.html.
3. Find the VIDEOS array (near "Video catalogue" comment).
4. Append a new entry, e.g.:

   { file: "My New Auction Clip.mp4",
     num:  "37",
     title: "My New Auction Clip" },

5. Save. Refresh the Media page in your browser.

CURRENTLY WIRED-IN VIDEOS (9 of 36 present in folder)
------------------------------------------------------
- #23 Peter Walker_ Authentic Auctions, Beating the Market (1).mp4
- #1  Auction vs. Contract_ Real Estate Agent's Honest Mistake Revealed.mp4
- #2  Auction Success_ Selling for More Than Expected!.mp4
- #14 Auction Secrets_ Avoid Sleepless Nights Before Bidding!.mp4
- #15 Real Estate Auction Secrets_ Market Value & Buyer Promises.mp4
- #18 Authentic Real Estate_ Change Your Words, Change Your Business.mp4
- #27 Auction Day Secrets_ Sell Your Property NOW!.mp4
- #31 Auction Secrets_ Honesty is the Best Auction Strategy.mp4
- #33 Real Estate Bidding_ Your Winning Strategy Revealed!.mp4

You have 36 .mp4 files in this folder. The remaining 27 are NOT in the
gallery yet — add them to the VIDEOS array if you want them shown.

LOCAL PREVIEW
-------------
Modern browsers block large video files via the file:// protocol. To
test the site locally, run a quick HTTP server from the PWA folder:

  cd /Users/neilverney/Documents/Claude/Projects/PWA
  python3 -m http.server 8080

Then open: http://localhost:8080/peter-walker-multipage.html

RECOMMENDED VIDEO SPECS FOR WEB
-------------------------------
- Codec:    H.264 (AVC)
- Container: .mp4 with faststart flag
- Resolution: 1080p or 720p
- Bitrate:  4–8 Mbps for general web
- Audio:    AAC, 128–192 kbps stereo

To re-encode with ffmpeg for faster loading:
  ffmpeg -i input.mp4 -movflags +faststart -vcodec libx264 \
         -crf 23 -preset medium -acodec aac -b:a 128k output.mp4

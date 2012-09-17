Create Your Own "I've Seen Footage" video
=========================================

Make your own version of [Death Grips' exhausting video for "I've Seen Footage"](http://youtu.be/sticXkHxZC4), using your own images (and a different song if you like, though REALLY WHAT SORT OF PERSON ARE YOU.)

1. Get some images. How about [exporting your Instagram photos](http://instaport.me/)? Put them in `images/`.
2. Run `rake sequence`. This is a necessary step because `ffmpeg` needs nicely numbered images. Rerun it every time the contents of `images/` change.
3. Put your legally-obtained recording of "I've Seen Footage" in `audio/`.
4. Run `rake`. Hopefully everything will be just fine.


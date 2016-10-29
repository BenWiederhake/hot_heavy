The drawings have unclear or too restrictive licenses,
so we can't put the in this public repository.
Instead, they now live in `/ext/images/bird_secrets`.
To make it easier for the using program (Chromium, cp and rsync),
just symbolically link to the proper images.

However, since this directory is actually `/.heavy/bird_images/`,
the links look a bit weird.
Thus, the parent directory `/ext/images/` is not available as `..`, but only as `../../ext/images`.
That is because the *link* (read: pointed-to inode) `..` is actually `/.heavy`.

Keep that in mind when creating symbolic links.  For example, the `kiwi-drawing.jpg`
needs to contain `../../ext/images/birds_secret/kiwi-drawing.jpg`.

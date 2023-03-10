The urls in ths repo are for all of the img content Pikamee has posted in the community tab, and they are already set to take the best quality possible (using ```=s0```)

This repo does not contain any of her Members Only posts and it was taken whilst logged off to prevent that.

### COMMANDS USED 

I used the following command in linux to record my clipboard into a file, that way I can do it faster
```while : ; do  sleep .5; TMP="$(xclip -o)"; [[ "$TMP" != "$OLD" ]] && echo $TMP >> output.txt; OLD="$TMP" ; done```

Afterwards I used this one to fix the ending of every url to put a ```=s0``` so that it returns the best quality possible of each image

```cat output.txt | sed 's;=.*;=s0;g' >> images.txt```

To download everything I used curl like so:

```VAR=0; for item in `cat images.txt`; do VAR=$((VAR + 1)); curl $item > $VAR; done```

that way all the images are writen like: 

```1,2,3,4,5```

I have not specified the extensions on this command, because some are png and some are jpeg, and since linux doesn't care about file extensions I didn't bother

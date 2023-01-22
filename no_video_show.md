# Videos with no video_show ID
You should be able to use the video_type field to narrow your results, and remove trailers. 

Running:
```
vids.py --dump_video_categories
```
I get these IDs. **I don't know if a premium account will return more results.**
```
3: Quick Looks
5: Endurance Run
6: Events
8: Features
10: Premium
11: Extra Life
12: Old Games
13: Unfinished
20: Best of Giant Bomb
23: Giant Bombcast
7: Trailers
```

So this will return all videos with no video_show, and is considered a Feature (8). Use the second command to download.
```
vids.py --filter --video_show "" --video_type 8

vids.py --filter --video_show "" --video_type 8 --download
```

There are also shows that don't have a video_show and a video_type, so remember to check for those.
```
vids.py --filter --video_show "" --video_type ""

vids.py --filter --video_show "" --video_type "" --download
```

# gb_vids
A command line utility to download GB videos.

99% of the work on this was done by harryr0se. I just made changes so that it worked in Python 3. Please see below for the original:
https://github.com/harryr0se/giant_bomb_cli

**This requires Python 3 and https://pypi.org/project/requests/ to be installed.**

# Example 1: Downloading a single video
Let's say I want Drew's Iceland video. I can search for it by using:
```
vids.py --filter --name "iceland"
```
It'll display the ID as 7330. So I can use this command to download it at low quality:
```
vids.py --filter --id 7330 --quality "low" --download
```

# Example 2: Downloading a series
To get the ID of each series use:
```
vids.py --dump_video_shows
```
Then if I want to download all the Altered Beast videos in This is the Run at HD quality:
```
vids.py --filter --video_show 17 --name "altered beast" --quality "hd" --download
```

# Usage
```

Usage: giant_bomb_cli.py [options]

Options:
  -l <x>, --limit <x>   limits the amount of items requested, defaults to 25
  --offset <x>          specify the offest into the results, defaults to 0
  --quality QUALITY     the quality of the video, used when streaming or
                        downloading (low, high, hd) defaults to high
  --download            will attempt to download all videos matching filters
  --output OUTPUTFOLDER
                        the folder to output downloaded content to
  --dump_video_shows    will dump all known ids for video shows,
  --filter              will attempt to filter by the below arguments
  --sort SORTORDER      orders the videos by their id (asc/desc) defaults to
                        desc
  --download-archive DOWNLOADARCHIVE
                        Download videos whose ids aren't listed within the
                        file, the script will also update the archive file
                        each run

Filter options:
  Use these in conjunction with --filter to customise results

  --name FILTERNAME     search for videos containing the specified phrase in
                        the name
  --id CONTENTID        id of the video
  --video_show VIDEOSHOW
                        id of the video show (see --dump_video_shows)

Debug Options:
  --debug               logs server requests and json responses
```

# FAQ

## Where can I get my api key from?
Your api key can be requested and found at http://www.giantbomb.com/api/

## Where is my api key stored?
Your api key is stored in your home directory (~/.giant_bomb_cli/config)

If you wish to change api key, just delete the config file and you'll be prompted to input a new one next time the script is run

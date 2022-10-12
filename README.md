# winnow-photos

Provide assistance to remove unnecessary photos.

## Current Photo processing flow

At present I use a script to import photos from any location to `~/Pictures/YYYY/MM/DD/` based on image tags or file date. These are the incoming directories. When I want to produce an album, I copy or move selected photos from this receiving directory to `~/Pictures/YYYY/YYYY-MM-DD_some-useful-description/` and possibly edit them. (This used to be `~/Pictures/YYYY-MM-DD_some-useful-description/` but the `~/Pictures/` directory was getting too crowded. I plan to move all of the albun directories to their respective `~/Pictures/YYYY/` directory.)

## Problem

There are all original photos captured with digital cameras and some scanned from negatives, slides or prints. Some of the older photos do not have EXIF tags and are sorted by file date. I have not purged many of the unneeded images, and there are a *lot*. This is an obstacle to getting the most benefit from any sort of photo display server such as PhotoPrism or Nextcloud.

## Need

Separate the interesting images from virtual duplicates and uninteresting images. This is a huge curation task that I would like an assist with from some kind of automation.

## Solution

I envision some kind of process that

1. Identifies directories that have been processed.
1. Identifies images within the receiving directory that have corresponding entries in the processed directories.
1. Displays both in some manner that is useful for deciding what should be deleted.
1. Facilitate the deletion.
1. Displaying both in a manner that helps to decide which, if any, images in the receiving directory should be copied to the processed directory.

This process should be aware that there may be multiple processed directories for any given incoming directory and single processed directories for multiple incoming directories. (e.g. multiple events in one day and an event that spans multiple days.) I anticipate that this process will require viewers of some sort that show both processed contents and incoming contents. Perhaps a third view that shows images in the incoming directory that either matches or does not match images in the processed directory would be useful.

A second process is also needed that will

1. Identify receiving directories that have no corresponding processed directory.
1. Facilitate the creation of a processed directory and allocation of selected images to be copied to the receiving directory.
1. Facilitate the deletion of any undesired images or incoming directories.

Since my policy has been to preserve originals, the images in the receiving directory that correspond to images that have been processed will be preserved. Any images selected to not be deleted can be copied to the processed folder (for the first scenario.)

## Errata

* Files are on a Linux file server and I use a Linux desktop.
* I write software so scripting/programming a solution is not out of the question. Before I start, I'd prefer to have a solid understanding of what I want to do and a strategy to accomplish it.
* Just having written this README has helped me to clarify my thoughts and I will probably begin this manually. That may provide additional insight into the problem and solution and will actuallly get some of done. At best there will remain a lot of manual effort.
* I'm using ZFS and snapshotting the filesystem that holds the photos so if I totally screw up, I should be able to recover. And I have a backup and will create an additional backup before unleashing any automation.

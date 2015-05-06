# Oral Histories Solution Pack

**In Development, will not work**

## Introduction

Adds all required Fedora objects depending on video or audio file uploaded and TRANSCRIPT datastream through the Islandora interface.
Displays transcript content along with video or audio file.

## Requirements

This module requires the following modules/libraries:

* [Islandora](https://github.com/islandora/islandora)
* [Tuque](https://github.com/islandora/tuque)
* [Islandora Video Solution Pack](https://github.com/Islandora/islandora_solution_pack_video)
* [Islandora Audio Solution Pack](https://github.com/Islandora/islandora_solution_pack_audio)

## Installation

Install as usual, see [this](https://drupal.org/documentation/install/modules-themes/modules-7) for further information.

## Configuration

Select a viewer in Administration » Islandora » Oral Histories Solution Pack (admin/islandora/solution_pack_config/oralhistories) and enable transcript or caption display.
The module currently doesn't support JW Player as viewer.

## Notes

**Caution:** This Solution Pack is currently in early development stage. It only supports transcript file in a flat xml format like below:

Here is a simple xml file for transcript:
```
<?xml version="1.0" encoding="UTF-8"?>
<cues>
    <!-- If the entire transcript has one speaker only, use 'solespeaker' element.
         Then skip 'speaker' element in 'cue' element level. But DO NOT use them in both places. If 'solespeaker' element
         presents in the document, following 'speaker' elements will be skipped. -->
    <solespeaker>One Speaker</solespeaker>
    <!-- At least one 'transcript' or 'annotation' emlement must present in a 'cue' element. -->
    <cue>
        <speaker>Different Speaker</speaker>
        <!-- 'start' and 'end' elements are start time and end time in seconds for the cue. -->
        <start>0.000</start>
        <end>12.124</end>
        <!-- By default the content in 'transcript' or 'annotation' is in English. For non-english content,
             an attribute 'xml:lang' should present with two-letter valid BCP 47 language tag. Examples:
             xml:lang="fr" indicting content in French, xml:lang="de" indicating content in German. -->
        <transcript>This is the transcript text content.</transcript>
        <annotation>This is the annotation content.</annotation>
    </cue>

    <!-- add more cues with above structure.-->

</cues>
```


## Troubleshooting/Issues

When Caption display is true, video.js doesn't behave the same on Firefox and Chrome. On Firefox, it requires to click the caption menu once to start showing.
On Chrome, it displays automatically.

Having problems or solved a problem? Check out the Islandora google groups for a solution.

* [Islandora Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora)
* [Islandora Dev Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/islandora-dev)


## Maintainers/Sponsors
Current maintainers:

* [Lingling Jiang](https://github.com/sprklinginfo)

## Development

If you would like to contribute to this module, please check out our helpful [Documentation for Developers](https://github.com/Islandora/islandora/wiki#wiki-documentation-for-developers) info, as well as our [Developers](http://islandora.ca/developers) section on the Islandora.ca site.



## License

[GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)

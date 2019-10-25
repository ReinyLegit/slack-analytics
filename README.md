# slack-analytics

## Environment
- Windows
- Python3.X

## Log processing
1. Slack Download logs from (Settings & Permissions> Data Import / Export)
2. Create a data folder and put the unzipped one
3. Run createMasterCsv.py
4. Run createTalkCsv.py

## createMasterCsv.py
Create csv from channels.json and users.json
- output
	- channels.csv
	- users.csv

## createTalkCsv.py
Create messages, reactions, mentions csv from daily logs for each channel
- output
	- talk.csv
	- reaction.csv
	- mention.csv
	- Channel name directory
		- talk.csv
		- reaction.csv
		- mention.csv

### message
|channel_id|talk_id|talk_user|text|
|:--|:--|:--|:--|
|C5XXXXXXX|XX1|U9XXXXXXX|`<@U8YYYYYYY>`Hello|
|C5XXXXXXX|XX2|U8YYYYYYY|I want to go home|
|C5XXXXXXX|XX3|U9XXXXXXX|Shigowa|

### reaction
|channel_id|talk_id|talk_user|reaction_user|emoji|
|:--|:--|:--|:--|:--|
|C5XXXXXXX|XX1|U9XXXXXXX|U8YYYYYYY|ok_woman|
|C5XXXXXXX|XX1|U9XXXXXXX|U7ZZZZZZZ|iine|
|C5XXXXXXX|XX2|U8YYYYYYY|U9XXXXXXX|wakaru|
|C5XXXXXXX|XX2|U9XXXXXXX|U7ZZZZZZZ|otukare|

### mention
|channel_id|talk_id|talk_user|mention_user|
|:--|:--|:--|:--|
|C5XXXXXXX|XX1|U9XXXXXXX|U8YYYYYYY|

## How to create a graph

### drawNetworkGraph.py
- Jupyter Notebook Outputs a network diagram of mention
- It is recommended to analyze in the channel because it is limited to the Top 50 remarks
- Log processing must be executed first

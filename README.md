WoT-Replay-BattleResult-To-JSON v8.7.0 / wotrpbr2j.pyc

Author: Marius Czyz aka Phalynx
Contact: marius.czyz@gmail.com
Website: http://www.vbaddict.net
Wiki: http://wiki.vbaddict.net

== Supported Versions
  * WoT 0.7.x and higher. 
	* Latest tested version: WoT 0.8.7.

== Python
	* You need Python 2.7, or just use the compiled version wotrpbr2j.exe

== Usage
	* wotrpbr2j.pyc <replay.wotreplay>
		creates a text file with the name of the replay where the extension has been replaced by ".json"
	
	* wotrpbr2j.pyc <replay.wotreplay> -c
		Console mode, suppress all messages and print parsed replay to the console window

	* wotrpbr2j.pyc <replay.wotreplay> -c
		Include chat. Increasing the processing time as the binary part of the replay is decrypted and uncompressed

	Example:
		python.exe wotrpbr2j.pyc 20130126_2329_ussr-Object_704_07_lakeville.wotreplay

	Example:
		python.exe wotrpbr2j.pyc 20130619_2232_ussr-SU-101_02_malinovka.wotreplay -c

	Without installing Python, you can use wotrpbr2j.exe instead of wotrpbr2j.pyc

== Structure:
	* common[status] = "ok" or "error"
	* common[message] = detailed error, otherwise "ok"
	* common[parser] = Version of used script
	* common[datablock_1] = Datablock 1 exists
	* common[datablock_2] = Datablock 2 exists
	* common[datablock_battle_result] = Battle Result exists
	
	
	If the replay can be read, the file will contain additional blocks:
	* datablock_1
	* datablock_2 - not always available
	* datablock_battle_result - available only for replays created by WoT 0.8.2 or higher
	* chat - Available only with the option -chat
	* identify - Contains data used by vBAddict to identify a replay
	
== Credits
	* https://github.com/marklr/wotanalysis
	* https://github.com/raszpl/wotdecoder
	* Parser for replays of WoT 0.7.2 by Vit@liy and Aborche, http://aborche.com/tst/WoT/parser072.py

# SafeText
Tool to sanitize text to allow for safe distribution of documents from anonymous sources by removing zero-width characters and homoglpyhs.

Individuals attempting to leak an email or other text file face the risk of identification through fingerprinting.
Fingerprinting often occurs when the original distributor of the document has embedded some form of a canary.
For example, Elon Musk's [email](https://web.archive.org/web/20131020092330/http://gawker.com/5164035/tesla-ceo-in-digital-witch-hunt) in 2008 in response to leaks featured slightly different 
wording for each employee. This tactic was realized by the employees, and failed. An easier
tactic that is also employed, is the presence of nearly invisible changes to the text. 
SafeText is designed to identify and remove these changes.
Specifically this tool will remove homoglyphs, zero-width characters, and other subtle characters.
This tool will also attempt to identify unique spelling of words that could give away an individual's location.

## Usage

To use SafeText, call:
```shell
python safetext.py inputfile
```
Example output is:
```shell
λ python safetext.py TestFile.txt
[*] Cleaning TestFile.txt to TestFile.txt.safe ...
[!] FOUND a SPACE ON LINE # 1
[!] WARNING - Use of spelling (colour) that identifies country on line 2
[!] FOUND HOMOGLYPHIC CHARACTER CYRILLIC_large_b ON LINE 7
[*] Output file closed
```
SafeText will output to infile.safe. 

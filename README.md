### Wordle Solution
Taped together in an hour for own casual convenience use.
DO NOT reference this repo for good coding style/design patterns.


#### Quick explanation
Was trying to get the exact vocab list of words Wordle uses. So dug into their website. Watched their network calls. Apparently they don't make any server calls so everything is actually generated locally in the browser. So the vocab is also in the JavaScript file they sent over.

Found the vocab list in the JavaScript file. Turns out they split the vocab into two sections. A list that contains winning words and a list of weird, unknown words that they don't use as winning words but they recognize as bridging words. Mutually exclusive. Checked using Python.

Total of 2309 possible words that are considered winning words, 10638 possible words that are considered bridge words.

Since everything's generated locally, the logic to determine the winning solution is also in the file.

They essentially take the
(milliseconds difference between today's date (set at 00:00) and a hardcoded date (19th June 2021) )mod 864e5
Then identify the solution of the day by indexing the winning solution list using (equation above ^ mod length of winning solution list).

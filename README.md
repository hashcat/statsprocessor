statsprocessor
==============

Statsprocessor is a word-generator based on per-position markov-chains packed into a single stand-alone binary.

Example
--------------

The following example was made just to see what comes out of statsprocessor.

<pre><code>
root@sf:~/statsprocessor-0.07# ./sp64.bin --pw-min 5 --pw-max 5 hashcat.hcstat ?l?l?l?l?l | head -9 
sange
songe
serin
singe
sunge
srane
shane
slane
snder
</pre></code>

In markov-chains we have a statistic generated which letter is following which letter based on the analysis of the original input dictionary used to generate the .hcstat. In this case the most used letter on the first position is the letter is “s”. The program then looks up the markov-table with the key “s” to get the most used letter after the letter “s” on position 0. In our case, its the letter “a”. This “chain” goes till the ende of the word and iterates through all letters stored in the markov-table.

Compile
--------------

Simply run make

Binary distribution
--------------

Binaries for Linux, Windows and OSX: https://github.com/jsteube/statsprocessor/releases

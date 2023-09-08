1. How many 4-letter words?
ggrep –c -P  '^[ऄअआइईउऊऋऌऍऎएऐऑऒओऔकखगघङचछजझञटठडढणतथदधनऩपफबभमयरऱलळऴवशषसहऺऻ़ऽािीुूृॄॅॆेैॉॊोौ्ॎॏॐ॒॑॓॔ॕॖॗक़ख़ग़ज़ड़ढ़फ़य़ॠॡॢॣ।॥०१२३४५६७८९॰ॱॲॳॴॵॶॷॸॹॺॻॼॽॾॿ]{4}$' < wiki.words > word4count.hist


#I have used only independent hindi vowels for this assignment
#https://www.easyhindityping.com/hindi-alphabet
2. Are there any words with no vowels?

ggrep -P '^[^अआइईउऊऋॠएऐऒओऔअंअः]+$' <wiki.words  > no_vowels.hist 

3. Find ‘’1-syllable’’ words (words with exactly one vowel)

grep  '^[^अआइईउऊऋॠएऐऒओऔअंअः]*[अआइईउऊऋॠएऐऒओऔअंअः][^अआइईउऊऋॠएऐऒओऔअंअः]*$' < wiki.words > vowel_1.hist

4. Find ‘’2-syllable’’ words (words with exactly two vowels)

grep  ^[^अआइईउऊऋॠएऐऒओऔअंअः]*[अआइईउऊऋॠएऐऒओऔअंअः][^अआइईउऊऋॠएऐऒओऔअंअः]*[अआइईउऊऋॠएऐऒओऔअंअः][^अआइईउऊऋॠएऐऒओऔअंअः]*$' < wiki.words > vowels_2.hist 

 
5.Count word initial consonant sequences: tokenise by word, delete the vowel and the rest of the word, and count

gsed 's/[^ःऄअआइईउऊऋऌऍऎएऐऑऒओऔकखगघङचछजझञटठडढणतथदधनऩपफबभमयरऱलळऴवशषसहऺऻ़ऽािीुूृॄॅॆेैॉॊोौ्ॎॏॐ॒॑॓॔ॕॖॗक़ख़ग़ज़ड़ढ़फ़य़ॠॡॢॣ।॥०१२३४५६७८९॰ॱॲॳॴॵॶॷॸॹॺॻॼॽॾॿ]\+/\n/g' < wiki.txt | sed 's/[अआइईउऊऋॠएऐऒओऔअंअः].*//g' | sed '/^$/d'| uniq -c > initial-consonants.hist 

6.Count word final consonant sequences

gsed 's/[^ःऄअआइईउऊऋऌऍऎएऐऑऒओऔकखगघङचछजझञटठडढणतथदधनऩपफबभमयरऱलळऴवशषसहऺऻ़ऽािीुूृॄॅॆेैॉॊोौ्ॎॏॐ॒॑॓॔ॕॖॗक़ख़ग़ज़ड़ढ़फ़य़ॠॡॢॣ।॥०१२३४५६७८९॰ॱॲॳॴॵॶॷॸॹॺॻॼॽॾॿ]\+/\n/g' < wiki.txt | sed 's/^.*[अआइईउऊऋॠएऐऒओऔअंअः]//g' | sed '/^$/d'| uniq -c| sort > final-consonants.hist 


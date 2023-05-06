# Lab Report 3
For these functions I used ChatGPT to give some command line operations for the grep function. 
## grep -r "term" Directory
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -r "telomere fusion" biomed
biomed/gb-2003-4-8-r50.txt:        telomere fusion between PTR chromosomes 12 and 13,
```
-r helps us find certain strings in files found in a directory. Here it is looking for the term "telomere fusion" in the biomed directory. It will provide the relative path to a file containing that string and also the contents of the line that have that string. This command is useful, in giving the users a very quick glimpse as to the context of the usage of this term and also displays where you can find them in the directory. 

```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -r "orangutan" biomed
biomed/gb-2003-4-8-r50.txt:        gorilla and orangutan chromosomes were assayed for the
biomed/gb-2003-4-8-r50.txt:        gorilla and orangutan G-banded metaphase chromosomes
biomed/gb-2003-4-8-r50.txt:        orangutan [ 1 2 ] . Two-color FISH experiments utilizing
biomed/gb-2003-4-8-r50.txt:        orangutan indicated the inversion event was restricted to
biomed/gb-2003-4-8-r50.txt:          orangutan (
biomed/gb-2003-4-8-r50.txt:          orangutan. BAC and PAC DNAs, isolated from bacterial
```
In this usage of -r, I searched for the term "orangutan" in the biomed directory. It outputed the file path and the line contents where the term was found. Note that even if it is in the same file, it will simply restate the path of that file before stating the line with the term.

## grep -n "term" file
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -n "relevant" biomed/1468-6708-3-1.txt
12:        for relevant covariates [ 1 2 3 4 5 6 ] . All studies found
```
-n will require the user to have a term they want to search and the path to a specific file. It will output the line number and the contents of that line for which the term appears. Here it shows that the term **relevant** was found in line 12 and beside it the line. This command is useful, as it gives you the line number where the term shows up so that you know where to start reading if you would like learn more about this term in particular. 
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -n "Introduction" biomed/1468-6708-3-1.txt
5:        Introduction
```
In this example, we looked into this file `biomed/1468-6708-3-1.txt` for the term **Introduction**. The output shows that there was only one match which was in line 5 and beside it shows the contents of that line number.

## grep -l "term" file(s)
Output shows all the files that contain the words
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -l "orangutan" biomed/*
biomed/gb-2003-4-8-r50.txt
```
-l will look for files found in a directory for the term and output the files that contain that term. Here it shows the files that follow the pattern of `biomed/*` and contain the term **orangutan** are listed, in this case it was only one file. This is useful if you want to find files that cover or use a particular term, so that you can focus on these files.   
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -l "telomere fusion" biomed/*
biomed/gb-2003-4-8-r50.txt
```
This example is also similar to the first where it looks for the term **telemore fusion** in for files following the `biomed/*` pattern. It's output shows there is only one file with that pattern inside the biomed folder that has that term. 

## grep -C number "term" file

```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -C 3 "telomere fusion" biomed/gb-2003-4-8-r50.txt
        Primarily examined through the use of G-banding
        cytogenetic techniques, the human and common chimpanzee
        karyotypes differ by only 10 euchromatic rearrangements: a
        telomere fusion between PTR chromosomes 12 and 13,
        resulting in HSA chromosome 2, and 9 pericentric inversions
        (HSA 1, 4, 5, 9, 12, 15, 16, 17, 18) [ 1 2 ] . The
        predominance of pericentric inversions between chimps and
```
grep -C takes a number, the term you want and the file path you are searching. The number indicates how many lines above and below the line in which the term you are looking for is found in. So in this example, there are 7 lines, indicating that they found one line where the term was found and also gave 3 lines above and below that line. This is particularly useful as it helps give readers context as to how the word is being used. 
```
Wilson@DESKTOP-SCRO0UF MINGW64 ~/OneDrive/Desktop/UCSD/CSE 15L/stringsearch-data/technical (main)
$ grep -C 3 "orangutan" biomed/gb-2003-4-8-r50.txt
        in situ hybridization (FISH) (data
        not shown).
        During this analysis, chimpanzee, pygmy chimpanzee,
        gorilla and orangutan chromosomes were assayed for the
        species-specificity of the pericentric inversion (Figure
        2). Previous cytogenetic analyses of human, chimpanzee,
        gorilla and orangutan G-banded metaphase chromosomes
        demonstrated that the pericentric inversion was a
        chimpanzee-specific event, with humans maintaining the
        ancestral state of this region when compared to gorilla and
        orangutan [ 1 2 ] . Two-color FISH experiments utilizing
        distal probe RP11-88O16, and the PWS/AS common deletion
        breakpoint-marking probe pDJ-778A2 clearly show that the
        chimpanzee lineage is the sole great ape species to harbor
--
        approximately 600 kb in length, according to the most
        recent assembly of the human genome. Comparative analysis
        using material from other great apes including gorilla and
        orangutan indicated the inversion event was restricted to
        the chimpanzee lineage. It should be noted that the
        inversion, although primarily characterized in the common
        chimpanzee (
--
          chimpanzee lineage, whereas humans share the ancestral
          state with the gorilla (
          Gorilla gorilla ; GGO) and
          orangutan (
          Pongo pygmaeus ; PPY). To confirm
          these observations, metaphase chromosome preparations
          were generated from lymphoblast-derived cell lines for
          human, common chimpanzee, pygmy chimpanzee (
          Pan paniscus ; PPA), gorilla and
          orangutan. BAC and PAC DNAs, isolated from bacterial
          cultures (Nucleobond, Clontech, Franklin Lakes, NJ), were
          labeled by nick-translation with biotin and digoxigenin.
          FISH experiments were performed under standard conditions
```
This example is similar, where it will output the lines above and below where the term **orangutan** is. Here it shows several iterations which can imply that the term is a significant point in this essay. 





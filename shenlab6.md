# BGGN 123 Shen lab 6
Celina Shen (PID: A16673724)

# Intro to functions lecture activities

``` r
add <- function(x,y) {
  x+y
}
```

Can I just execute this chunk? No, because the “add” chunk has not been
run yet!

``` r
add (1,1)
```

    [1] 2

``` r
add (c(100,1),1)
```

    [1] 101   2

``` r
add <- function(x, y=1) {
  x+y
}
```

If y≠1 in the input, the y=1 line will be overrode.

``` r
add(5)
```

    [1] 6

``` r
add (1,3)
```

    [1] 4

``` r
add (c(100,1),2)
```

    [1] 102   3

``` r
add <- function(x, y, z) {
  x+y+z
}
add(10, 1, 1)
```

    [1] 12

Make a function “generate_DNA()” that makes a random nucleotide sequence
of any length.

``` r
#generate_DNA <- function() {
bases <- c("A", "C", "G", "T")
sample(bases, size = 5, replace = TRUE)
```

    [1] "G" "T" "T" "G" "C"

Now that this part is working, I can make it into a function.

``` r
generate_DNA <- function(length) {
  bases <- c("A", "C", "G", "T")
  sequence <- sample(bases, size = length, replace = TRUE)
  return(sequence)
}
generate_DNA(10)
```

     [1] "C" "G" "A" "C" "C" "T" "G" "A" "T" "C"

``` r
#install.packages("bio3d")
library(bio3d)
unique(bio3d::aa.table$aa1)[1:20]
```

     [1] "A" "R" "N" "D" "C" "Q" "E" "G" "H" "I" "L" "K" "M" "F" "P" "S" "T" "W" "Y"
    [20] "V"

Generate random protein sequences of length 6 to 12.

``` r
generate_protein <- function(length){
  amino_acids <- unique(bio3d::aa.table$aa1)
  sequence <- sample(amino_acids, size=length, replace = TRUE)
  sequence <- paste(sequence, collapse = "")
  return(sequence)
}
```

Sequences from length 6 to 12.

``` r
answer <- sapply(6:12, generate_protein)
answer
```

    [1] "NXPLLM"       "EPLYATQ"      "TDFNLPNW"     "ASNLCVAQD"    "SHEKRMSPWW"  
    [6] "WSNPRDDAYRW"  "TKILXXPDMPLI"

Run function

``` r
generate_protein(6)
```

    [1] "FWGMVI"

``` r
paste(c("barry", "alice", "amy", "chandra"),
      "loves R")
```

    [1] "barry loves R"   "alice loves R"   "amy loves R"     "chandra loves R"

``` r
paste(">id.", 6:12, "\n", answer, "\n", sep ="")
```

    [1] ">id.6\nNXPLLM\n"        ">id.7\nEPLYATQ\n"       ">id.8\nTDFNLPNW\n"     
    [4] ">id.9\nASNLCVAQD\n"     ">id.10\nSHEKRMSPWW\n"   ">id.11\nWSNPRDDAYRW\n" 
    [7] ">id.12\nTKILXXPDMPLI\n"

``` r
cat(paste(">id.", 6:12, "\n", answer, "\n", sep =""), sep = "")
```

    >id.6
    NXPLLM
    >id.7
    EPLYATQ
    >id.8
    TDFNLPNW
    >id.9
    ASNLCVAQD
    >id.10
    SHEKRMSPWW
    >id.11
    WSNPRDDAYRW
    >id.12
    TKILXXPDMPLI

# Python-Mismatches-in-Sequences-
def opensequence(filename):
    sequence = ""
    with open(filename, "r") as seq:
        for line in seq:
            if line[0] != ">": #to eliminate the sequence name
                sequence += line.rstrip()
    return sequence
sequence = opensequence(input("Enter file name: ")) # to ask the user to enter the fasta file name

# function for opening a fasta file for the second sequence
def opensequence(filename):
    sequence2 = ""
    with open(filename, "r") as seq:
        for line in seq:
            if not line[0] == ">":
                sequence2 += line.rstrip()
    return sequence2
sequence2 = opensequence(input("Enter file name: "))

nucleotide = 0 #
Mismatches = []
for x in sequence: # x represents a nucleotide in sequence 1
    if x != sequence2[nucleotide]:
        Mismatches.append(nucleotide) # for appending the mismatching positions.
    nucleotide = nucleotide + 1
print(Mismatches)

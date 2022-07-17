# QuadParser-Replacement
Searches DNA sequence fasta file for G-quadruplexes and reports sequence name and each quadruplex found

# Convert a csv file to a fasta file:

cat infile.csv | sed'' 's/m/>m/g ; s/\,/\'$'\n''/g' > infile.fa   

# Search the file for quadruplexes using regex:

egrep -o -B1 '([gG]{3,}\w{1,7}){3,}[gG]{3,}|([cC]{3,}\w{1,7}){3,}[cC]{3,}' infile.fa > infile_G4reads.txt

# If egrep fails, try:

grep -E -o -B1 '([gG]{3,}\w{1,7}){3,}[gG]{3,}|([cC]{3,}\w{1,7}){3,}[cC]{3,}' infile.fa > infile_G4reads.txt


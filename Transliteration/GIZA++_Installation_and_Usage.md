
# GIZA++ Installation and Usage Guide

## Installation

To install GIZA++, follow these steps:

1. Clone the GIZA++ repository:
   ```bash
   git clone git@github.com:moses-smt/giza-pp.git
   ```

2. Navigate to the giza-pp directory:
   ```bash
   cd giza-pp
   ```

3. Compile the GIZA++ binaries:
   ```bash
   make
   ```

## Usage

After installation, you can use GIZA++ with the following commands:

1. Navigate to the GIZA++-v2 directory:

2. Convert plain text files to sentence-aligned format:
   ```bash
   ./plain2snt.out ../giza_example/combined.sat_Olck ../giza_example/combined.eng_Latn
   ```

3. Generate co-occurrence file:
   ```bash
   ./snt2cooc.out ../giza_example/combined.sat_Olck.vcb ../giza_example/combined.eng_Latn.vcb ../giza_example/combined.eng_Latn_combined.sat_Olck.snt > ../giza_example/corp.cooc
   ```

4. Run the GIZA++ alignment:
   ```bash
   ./GIZA++ -S ../giza_example/combined.eng_Latn.vcb -T ../giza_example/combined.sat_Olck.vcb -C ../giza_example/combined.eng_Latn_combined.sat_Olck.snt -CoocurrenceFile ../giza_example/corp.cooc -outputpath ../giza_example/
   ```

# links

https://gitter.im/UZH-BIO392/BIO392-2022-course-chat

https://drive.switch.ch/index.php/s/iCTAmYzVZEMSWYP

https://compbiozurich.org/courses/UZH-BIO392/

https://progenetix.org

https://github.com/compbiozurich/UZH-BIO392


# day 3 

## questions
- does the reference genome come with nucleotide variability?
> nope, variability always depends on the context (ethnicity, ..)

- how do sequence alignment algorithms work?
> eg. seeding and checking vincinity. read paper "Fast and accurate long-read alignment with Burrows–Wheeler transform"

- how to solve sequence alignment during hr?
> no clue



- UCSC genome browser https://genome-euro.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A15560138%2D15602945&hgsid=290662285_Fb1M2aMP5aCk8N4Foq8zPwovXDPC
  - genome vs. conservation, exons, .. -> find spots which likely contain lots of information.
  - data representation is "boring plain text"
  - 3bio bo/human genome
  - variant data store logic: chrom, start, end (of variant, duplication, ..?)
    - discussed storage formats: only reference genoma, FASTA and one other (FASTQ?) sequence based
  - sequencing: degree of uncertainty for each nucleotide
  - naming of reference genomes is a mess
  - "if youre doing science and youre using a mouse: this is not reproducible"
  
- FASTA
  - >"identifyer", return, rest letter sequence
 <img width="655" alt="Screen Shot 2022-09-22 at 13 08 34" src="https://user-images.githubusercontent.com/103630748/191731391-081cedd7-f5f6-42ff-89e1-03efcdc8aa84.png">

- where to get ur reference: https://www.ncbi.nlm.nih.gov/grc/human

- FASTQ
  - fasta with quality info
  - 4 lines: 
    - > identifyer
    - sequence
    - + (separator)
    - quality line (each base matched with trustability score (frequency of reading other than "base in seq")). one letter, but *different conventions in use*
    
- SAM (sequence alignment map)
  - file format storing only locus information (and reference to reference genome?), not sequence
<img width="981" alt="Screen Shot 2022-09-22 at 13 42 30" src="https://user-images.githubusercontent.com/103630748/191737648-f3042e91-636d-4396-9930-0132b9f4e4dc.png">

- BAM (binary alignment map)
  - indexed, compressed, not human readable (binary)
  
- BED (browser extensible date)
  - BED3 -> 3 cols, BED6 -> 6 cols 
  BED3: chromosome, start, end

  - depending on use case, one might really be not interested at all about the actual read one gi, only about the position in the reference genome
    - eg. transcriptomics, read counts..
    - much less storage needed
    - problem: counting is not standardized xD
      - eg. 11 23; nucleotide 11 included or not? first nucleotide was 1 or 0?
      
      <img width="594" alt="Screen Shot 2022-09-22 at 14 01 43" src="https://user-images.githubusercontent.com/103630748/191741320-b92d4fd3-8a06-4a43-8125-a1a3415b1c23.png">





## terminal, UNIX

- philosophy: small efficient programs which only do one thing
- write skripts which connect these programs
  - without saving to disk, compi can process files (text string processing)


date > folder/file.txt
> writes current date into new text file

- "shebang": #!\"language in which skript was written"
- file extensions can be anything, not bound to what language stuff is written!

- shell -> kernel -> computer ressources![image](https://user-images.githubusercontent.com/103630748/191703178-b083d6e2-3603-4d3a-8e9f-7d4b4087587c.png)

- prompt = symbol at beginning of commandline which indicates that compi is ready to take command (UNIX: $)
<img width="1471" alt="Screen Shot 2022-09-22 at 11 03 48" src="https://user-images.githubusercontent.com/103630748/191705616-1f566a1c-7c3b-42ba-8114-697114bffe48.png">

- mount point = directory for mounting external drives.. macOSX: /Volume

- in UNIX, file extensions are arbitrary. file can have multiple extensions

- root user has every right; only used for system administration
  - command to get root rights: sudo
  
- A process is an executing - or running - program identified by a unique process identifier (PID)
  - A thread is a 'light weight' process - or "unit of execution" - that is contained in a process. It uses the same environment as the process it belongs to - PID, memory, data, etc.
    - the more cores there are, the more threads can be executed at the same time


### awk
- very fast programming language
- type awk "command" in terminal
  - calls "awk" binary to execute code which follows
[awk_cheat_sheet-2.pdf](https://github.com/FlurinLa/Flurin_BIO392/files/9625256/awk_cheat_sheet-2.pdf)



 


















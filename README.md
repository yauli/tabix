# tabix
Note: tabix and bgzip binaries are now part of the HTSlib project.

## Description
Tabix indexes a TAB-delimited genome position file in.tab.bgz and creates an index file ( in.tab.bgz.tbi or in.tab.bgz.csi ) when region is absent from the command-line. The input data file must be position sorted and compressed by bgzip which has a gzip(1) like interface. After indexing, tabix is able to quickly retrieve data lines overlapping regions specified in the format "chr:beginPos-endPos". Fast data retrieval also works over network if URI is given as a file name and in this case the index file will be downloaded if it is not present locally.

## What's new in this version?
Add swithes which can filter positions of a input table according to specific annotations indexed by tabix tool. The word "filter" means that you can keep those matched lines or discard those matched lines.

## Options
-p STR     preset: gff, bed, sam, vcf, psltbl [gff]
-s INT     sequence name column [1]
-b INT     start column [4]
-e INT     end column; can be identical to '-b' [5]
-S INT     skip first INT lines [0]
-c CHAR    symbol for comment/meta lines [#]
-r FILE    replace the header with the content of FILE [null]
-B         region1 is a BED file (entire file will be read)
-0         zero-based coordinate
-h         print also the header lines
-H         print only the header lines
-l         list chromosome names
-f         force to overwrite the index
-F         filter a table, which will print table lines which can be found in <in.tab.bgz> file to stdout
-D         along with -F, when -D opens, table lines which cannot be found in <in.tab.bgz> will be printed to stdout

# SortSamRefName

Sort a BAM of contig and then on name


## Usage

```
Usage: sortsamrefname [options] Files
  Options:
    --bamcompression
      Compression Level.
      Default: 5
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    --maxRecordsInRam
      When writing  files that need to be sorted, this will specify the number 
      of records stored in RAM before spilling to disk. Increasing this number 
      reduces the number of file  handles needed to sort a file, and increases 
      the amount of RAM needed
      Default: 50000
    -o, --output
      Output file. Optional . Default: stdout
    --samoutputformat
      Sam output format.
      Default: TypeImpl{name='SAM', fileExtension='sam', indexExtension='null'}
    --tmpDir
      tmp working directory. Default: java.io.tmpDir
      Default: []
    --version
      print version and exit

```


## Keywords

 * sam
 * sort



## See also in Biostars

 * [https://www.biostars.org/p/154220](https://www.biostars.org/p/154220)


## Compilation

### Requirements / Dependencies

* java compiler SDK 1.8 http://www.oracle.com/technetwork/java/index.html (**NOT the old java 1.7 or 1.6**) . Please check that this java is in the `${PATH}`. Setting JAVA_HOME is not enough : (e.g: https://github.com/lindenb/jvarkit/issues/23 )
* GNU Make >= 3.81
* curl/wget
* git
* xsltproc http://xmlsoft.org/XSLT/xsltproc2.html (tested with "libxml 20706, libxslt 10126 and libexslt 815")


### Download and Compile

```bash
$ git clone "https://github.com/lindenb/jvarkit.git"
$ cd jvarkit
$ make sortsamrefname
```

The *.jar libraries are not included in the main jar file, so you shouldn't move them (https://github.com/lindenb/jvarkit/issues/15#issuecomment-140099011 ).
The required libraries will be downloaded and installed in the `dist` directory.

### edit 'local.mk' (optional)

The a file **local.mk** can be created edited to override/add some definitions.

For example it can be used to set the HTTP proxy:

```
http.proxy.host=your.host.com
http.proxy.port=124567
```
## Source code 

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/SortSamRefName.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/SortSamRefName.java)


<details>
<summary>Git History</summary>

```
Wed May 24 17:27:28 2017 +0200 ; lowres bam2raster & fix doc ; https://github.com/lindenb/jvarkit/commit/6edcfd661827927b541e7267195c762e916482a0
Thu May 11 16:20:27 2017 +0200 ; move to jcommander ; https://github.com/lindenb/jvarkit/commit/15b6fabdbdd7ce0d1e20ca51e1c1a9db8574a59e
Thu Apr 27 17:22:22 2017 +0200 ; cont jcommander ; https://github.com/lindenb/jvarkit/commit/0a27a246a537d2b48201596067652ea26bfc28d6
Wed Mar 30 17:45:00 2016 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/ef77dce3c82c470017916555304df6a470fbdad4
Tue Dec 15 14:18:29 2015 +0100 ; sort sam ref ; https://github.com/lindenb/jvarkit/commit/b7c82e602e66e9cd300d00e739d69296883f5864
Wed Aug 12 18:34:11 2015 +0200 ; ignore mapq=0 ; https://github.com/lindenb/jvarkit/commit/484ae4fc0e3333893aa6f343db8774f0ede40dda
Wed Aug 12 15:35:53 2015 +0200 ; Tool to sort BAM on REF/name , tool to 'cap' bam. ; https://github.com/lindenb/jvarkit/commit/6f7e43d6fb776bf2a549700d71220b3d2693862d
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **sortsamrefname** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)


## Example

```bash
$  java -jar dist/sortsamrefname.jar /commun/data/packages/samtools/1.2/samtools/examples/toy.sam  2> /dev/null 
@HD	VN:1.4	SO:unsorted
@SQ	SN:ref	LN:45
@SQ	SN:ref2	LN:40
@CO	SortSamRefName 1c7bc5e674136947586779a2aac53e576db4a67f /commun/data/packages/samtools/1.2/samtools/examples/toy.sam
r001	83	ref	37	30	9M	=	7	-39	CAGCGCCAT	*
r001	163	ref	7	30	8M4I4M1D3M	=	37	39	TTAGATAAAGAGGATACTG	*	XX:B:S,12561,2,20,112
r002	0	ref	9	30	1S2I6M1P1I1P1I4M2I	*	0	0	AAAAGATAAGGGATAAA	*
r003	0	ref	9	30	5H6M	*	0	0	AGCTAA	*
r003	16	ref	29	30	6H5M	*	0	0	TAGGC	*
r004	0	ref	16	30	6M14N1I5M	*	0	0	ATAGCTCTCAGC	*
x1	0	ref2	1	30	20M	*	0	0	AGGTTTTATAAAACAAATAA	????????????????????
x2	0	ref2	2	30	21M	*	0	0	GGTTTTATAAAACAAATAATT	?????????????????????
x3	0	ref2	6	30	9M4I13M	*	0	0	TTATAAAACAAATAATTAAGTCTACA	??????????????????????????
x4	0	ref2	10	30	25M	*	0	0	CAAATAATTAAGTCTACAGAGCAAC	?????????????????????????
x5	0	ref2	12	30	24M	*	0	0	AATAATTAAGTCTACAGAGCAACT	????????????????????????
x6	0	ref2	14	30	23M	*	0	0	TAATTAAGTCTACAGAGCAACTA	???????????????????????
```



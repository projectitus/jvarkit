# FindCorruptedFiles

Reads filename from stdin and prints corrupted NGS files (VCF/BAM/FASTQ/BED/TBI/BAI)


## Usage

```
Usage: findcorruptedfiles [options] Files
  Options:
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    -E, --noempty
      empty file is an error.
      Default: false
    -V, --stringency
      BAM ValidationStringency
      Default: LENIENT
      Possible Values: [STRICT, LENIENT, SILENT]
    --version
      print version and exit
    -N
      number of features (samrecord, variant) to read. -1= read everything.
      Default: 100

```


## Keywords

 * vcf
 * bam
 * fastq
 * bed


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
$ make findcorruptedfiles
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/FindCorruptedFiles.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/FindCorruptedFiles.java)


<details>
<summary>Git History</summary>

```
Fri May 12 12:31:52 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/79b31100024fed64156ce4e1796507814c20ebf1
Thu Mar 30 17:38:36 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/bba625df69e00a0aa54de192cdce6fda110a65b4
Fri Jan 22 23:49:23 2016 +0100 ; vcfiterator is now an interface ; https://github.com/lindenb/jvarkit/commit/9f9b9314c4b31b21044c5911a7e79e1b3fb0af7a
Tue Sep 23 09:06:47 2014 +0200 ; htsjdk 121 ; https://github.com/lindenb/jvarkit/commit/9b4a2140c3818506204f95f188379c814af6fb1d
Fri Jun 20 10:43:04 2014 +0200 ; corrupeted files: test BED ; https://github.com/lindenb/jvarkit/commit/a2a0899b5b435c7349fdadf9f02c5328aad54ca8
Fri May 23 15:00:53 2014 +0200 ; cont moving to htsjdk ; https://github.com/lindenb/jvarkit/commit/81f98e337322928b07dfcb7a4045ba2464b7afa7
Mon May 12 10:28:28 2014 +0200 ; first sed on files ; https://github.com/lindenb/jvarkit/commit/79ae202e237f53b7edb94f4326fee79b2f71b8e8
Thu Nov 28 08:16:28 2013 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/d41deb4c340967592eb53e98101077ccbd84a3dd
Fri Nov 22 17:34:16 2013 +0100 ; my version of fastqreader ; https://github.com/lindenb/jvarkit/commit/caf819c6c165d251722ce24f4429d6106e50c2cc
Fri Nov 22 14:50:33 2013 +0100 ; pad fastq ; https://github.com/lindenb/jvarkit/commit/dba22139a20b2e25b42cfcd1eb4969d2b1ebe929
Mon Nov 4 13:49:15 2013 +0100 ; chaned command line handling + getopt ; https://github.com/lindenb/jvarkit/commit/939d2ccf1a9a4be2d2116586b925062c65d81195
Fri Oct 11 15:39:02 2013 +0200 ; picard v.100: deletion of VcfIterator :-( ; https://github.com/lindenb/jvarkit/commit/e88fab449b04aed40c2ff7f9d0cf8c8b6ab14a31
Fri Sep 6 15:11:11 2013 +0200 ; moved code for latest version of picard (1.97). Using VCFIterator instead of ASciiLineReader ; https://github.com/lindenb/jvarkit/commit/810877c10406a017fd5a31dacff7e8401089d429
Wed Jul 31 17:19:13 2013 +0200 ; find corrupted NGS files ; https://github.com/lindenb/jvarkit/commit/d2f0c79e4fbc962ae335ba8aa065f1b389db949e
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **findcorruptedfiles** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)


## Example

```
$ find  DIR1 DIR2 -type f |\
java -jar dist/findcorruptedfiles.jar \
	-V SILENT 2> /dev/null > redo.txt
```



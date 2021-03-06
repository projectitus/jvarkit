# VcfSimulator

Generate a VCF


## Usage

```
Usage: vcfSimulator [options] Files
  Options:
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    --version
      print version and exit
  * -R
      Indexed fasta Reference file. This file must be indexed with samtools 
      faidx and with picard CreateSequenceDictionary
    -S
      random seed
      Default: java.util.Random@1424e82

```

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
$ make vcfSimulator
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/VcfSimulator.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/misc/VcfSimulator.java)


<details>
<summary>Git History</summary>

```
Tue Jun 6 18:06:17 2017 +0200 ; postponed vcf ; https://github.com/lindenb/jvarkit/commit/bcd52318caf3cd76ce8662485ffaacaabde97caf
Thu May 4 13:06:07 2017 +0200 ; moving to jcommander ; https://github.com/lindenb/jvarkit/commit/b2f8f945cb8838c0289a7d850ce24603417eccde
Thu Jun 18 18:33:28 2015 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/dcfd0ddf4d1a6817487762c188d92e149438abcb
Wed Jun 17 09:33:25 2015 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/7741efa7e9839e699efb11586bd37167c5bf6347
Thu Mar 19 16:38:00 2015 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/fe6480ef56d91e683467200bbe805a726c4c6457
Mon May 12 15:27:08 2014 +0200 ; moving to htsjdk ; https://github.com/lindenb/jvarkit/commit/fd30a81154a16835b5bab3d8e1ef90c9fee6bdcb
Mon May 12 10:28:28 2014 +0200 ; first sed on files ; https://github.com/lindenb/jvarkit/commit/79ae202e237f53b7edb94f4326fee79b2f71b8e8
Sun Feb 2 18:55:03 2014 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/abd24b56ec986dada1e5162be5bbd0dac0c2d57c
Tue Dec 17 10:52:24 2013 +0100 ; bam rename chrom ; https://github.com/lindenb/jvarkit/commit/07c9cfcf563b1ebb183c2eb20f50fda98d65290e
Sat Dec 14 00:39:57 2013 +0100 ; updated Biostar59647 ; https://github.com/lindenb/jvarkit/commit/35f92334d89c1e970b1e9c0f9f076ade021d5492
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **vcfSimulator** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)



# VCFComparePredictions

Compare predictions (SNPEff, VEP) for several VCFs


## Usage

```
Usage: vcfcmppred [options] Files
  Options:
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
    --tmpDir
      tmp working directory. Default: java.io.tmpDir
      Default: []
    --version
      print version and exit

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
$ make vcfcmppred
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcfcmp/VCFComparePredictions.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcfcmp/VCFComparePredictions.java)


<details>
<summary>Git History</summary>

```
Mon May 29 12:33:45 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/870be8e90d7e98d947f73e67ef9965f12f351846
Thu Apr 27 17:22:22 2017 +0200 ; cont jcommander ; https://github.com/lindenb/jvarkit/commit/0a27a246a537d2b48201596067652ea26bfc28d6
Fri Apr 21 18:16:07 2017 +0200 ; scan sv ; https://github.com/lindenb/jvarkit/commit/49b99018811ea6a624e3df556627ebdbf3f16eab
Wed Feb 22 19:07:03 2017 +0100 ; refactor prediction parsers ; https://github.com/lindenb/jvarkit/commit/dc7f7797c60d63cd09d3b7712fb81033cd7022cb
Thu Sep 17 17:25:48 2015 +0200 ; avoid conflict with xml ; https://github.com/lindenb/jvarkit/commit/8e3bd3251228084825b6c945bfde6f808e1fcf8f
Mon Jun 1 15:27:11 2015 +0200 ; change getChrom() to getContig() ; https://github.com/lindenb/jvarkit/commit/5abd60afcdc2d5160164ae6e18087abf66d8fcfe
Tue Feb 24 16:43:03 2015 +0100 ; vcfin : code rewrittern. picky with ALT alleles. #tweet ; https://github.com/lindenb/jvarkit/commit/65ef7741539e89c7a1a1f9cca28c13d531902c96
Fri Jun 20 10:22:32 2014 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/5db16faf6650512cc3f554d3f1c6a6ffc2935e16
Thu Jun 19 12:01:56 2014 +0200 ; compare predictions ; https://github.com/lindenb/jvarkit/commit/1f6f10a7b7c7f9fa6d4eb8c95ff974f385b884ae
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **vcfcmppred** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)


## Example

### VEP

```bash
$  java -jar dist/vcfcmppred.jar  f1.vcf f2.vcf 
(...)
7	8566286	rs2139	A	VEP discordant SO:terms between f1.vcf and f2.vcf	[SO:0001619, SO:0001632]
```


in f1.vcf (VEP 75) CSQ contains:

* intron_variant
* downstream_gene_variant
* nc_transcript_variant

in f2.vcf (VEP 71) CSQ contains:

* intron_variant

### SNPEFF

```bash
$  java -jar dist/vcfcmppred.jar  f1.vcf f2.vcf 
(...)
 8	1394127	.	G	SNPEff discordant SO:terms between between f1.vcf and f2.vcf	[SO:0001630]
```

in f1.vcf  (snpEff_3_6) EFF contains:

* downstream_gene_variant
* intron_variant
* splice_region_variant

in f2.vcf  (snpEff_3_4) EFF contains:

* downstream_gene_variant
* intron_variant






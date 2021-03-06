# VCFTrios

Find mendelian incompatibilitie in a VCF


## Usage

```
Usage: vcftrio [options] Files
  Options:
    -A, --attribute
      INFO Attribute name containing the name of the affected samples.
      Default: MENDEL
    --discard
      Discard variants without mendelian incompatibilities
      Default: false
    -f, --filter
      filter name. create a filter in the FILTER column for variants having an 
      INCOMPAT 
    -gf, --gfilter
      genotype filter name. create a filter in the GENOTYPE column
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    -if, --inversefilter
      inverse FILTER, flag variant having NO mendelian incompat.
      Default: false
    -o, --output
      Output file. Optional . Default: stdout
  * -p, --ped, --pedigree
      Pedigree file. A pedigree is a text file delimited with tabs. No header. 
      Columns are (1) Family (2) Individual-ID (3) Father Id or '0' (4) Mother 
      Id or '0' (5) Sex : 1 male/2 female / 0 unknown (6) Status : 0 
      unaffected, 1 affected,-9 unknown
    --version
      print version and exit

```


## Keywords

 * vcf
 * mendelian
 * pedigree


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
$ make vcftrio
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcftrios/VCFTrios.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcftrios/VCFTrios.java)


<details>
<summary>Git History</summary>

```
Wed Sep 20 15:52:53 2017 +0200 ; moving to amalgamation ; https://github.com/lindenb/jvarkit/commit/fca74f53afa062f238c8a899ee0ee6e7cd15136c
Mon Sep 18 17:29:05 2017 +0200 ; adding test for ConvertVcfChromosomes ; https://github.com/lindenb/jvarkit/commit/39c750097a13c007c850449a4586de5b51962242
Mon Sep 11 14:48:00 2017 +0200 ; adding tests, add test files for gnomad ; https://github.com/lindenb/jvarkit/commit/bc90c3c76e38e677a2fe824ce29bd7705dde3bd0
Tue Aug 8 17:07:46 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/2d33719edc69a979a2b6366351ca6f0b59959755
Mon Aug 7 09:53:19 2017 +0200 ; fixed unicode problems after https://github.com/lindenb/jvarkit/issues/82 ; https://github.com/lindenb/jvarkit/commit/68254c69b027a9ce81d8b211447f1c0bf02dc626
Mon Jul 3 18:24:52 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/143424e4b26825a00eb8ac652f2b80ebe1ac79a8
Mon May 15 10:41:51 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/c13a658b2ed3bc5dd6ade57190e1dab05bf70612
Fri May 12 18:07:46 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/ca96bce803826964a65de33455e5231ffa6ea9bd
Tue Apr 4 17:09:36 2017 +0200 ; vcfgnomad ; https://github.com/lindenb/jvarkit/commit/eac33a01731eaffbdc401ec5fd917fe345b4a181
Wed Feb 10 17:20:35 2016 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/7207a57a0af4612b86064e027a232e1e51cb144c
Sat Jan 23 14:55:35 2016 +0100 ; factory builder ; https://github.com/lindenb/jvarkit/commit/d70912b7dbbca748cf4d45a0ba44a6bc70f804d7
Mon Dec 28 20:23:04 2015 +0100 ; sam2axt ; https://github.com/lindenb/jvarkit/commit/a2edef74730256e93d244e440a79e7362d647795
Mon Nov 30 16:53:51 2015 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/89f3cbe043ac8c52735feec5b45e43cf873b7179
Tue May 26 12:45:19 2015 +0200 ; FixVcfMissingGenotypes QUAL=0 ignored + misc ; https://github.com/lindenb/jvarkit/commit/5238e8d4e420e2859703c6dbf784350800f4ecd0
Fri Apr 24 17:05:31 2015 +0200 ; moved VCF-BigWig to a standard command-line #tweet ; https://github.com/lindenb/jvarkit/commit/3a0c4ccb05e7492382e00328ac60951f215d9400
Fri Feb 27 16:26:00 2015 +0100 ; compat with knime ; https://github.com/lindenb/jvarkit/commit/da80660b8caa1bb7587e8afb5874663e305d23d0
Fri Feb 27 13:26:55 2015 +0100 ; refactoring vcf head/tail/filterjs/trio/groupbygene for #usegalaxy #tweet ; https://github.com/lindenb/jvarkit/commit/ff425a051a74e00d2cdfb27badf46647fac641a4
Tue Jan 13 16:41:28 2015 +0100 ; number of INFO field fixed in trio ; https://github.com/lindenb/jvarkit/commit/d7f7f1fa211e6ca5aa26aa5ce0c01079fb2cc3c5
Mon Jan 12 18:02:41 2015 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/801e96ea74dc515bb5de8dd02f64063c0cd137aa
Mon Oct 13 18:29:16 2014 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/c83f20cde867920870918ee6eb5e5406f554e2bb
Mon May 12 14:06:30 2014 +0200 ; continue moving to htsjdk ; https://github.com/lindenb/jvarkit/commit/011f098b6402da9e204026ee33f3f89d5e0e0355
Mon May 12 10:28:28 2014 +0200 ; first sed on files ; https://github.com/lindenb/jvarkit/commit/79ae202e237f53b7edb94f4326fee79b2f71b8e8
Fri Oct 11 15:39:02 2013 +0200 ; picard v.100: deletion of VcfIterator :-( ; https://github.com/lindenb/jvarkit/commit/e88fab449b04aed40c2ff7f9d0cf8c8b6ab14a31
Fri Sep 6 15:11:11 2013 +0200 ; moved code for latest version of picard (1.97). Using VCFIterator instead of ASciiLineReader ; https://github.com/lindenb/jvarkit/commit/810877c10406a017fd5a31dacff7e8401089d429
Mon Jul 22 18:33:02 2013 +0200 ; mapping uniprot to bed ; https://github.com/lindenb/jvarkit/commit/a220a67081b1a62a534032a4a1499cc0466240a0
Mon Jul 22 13:46:16 2013 +0200 ; VCF trios ; https://github.com/lindenb/jvarkit/commit/4c63cb107424f398aaaba3ddaaac8d6bb310f839
Sun Jul 21 14:17:59 2013 +0200 ; vcf trios, added git HASH in METAINF/Manifest ; https://github.com/lindenb/jvarkit/commit/1854d3695563b91471861164f5e8903042493470
Fri Jul 19 18:23:32 2013 +0200 ; code for fixvcf ; https://github.com/lindenb/jvarkit/commit/99cb799aac12c5b6217e830f403e0e8ce5cf7bf6
Mon Jul 8 19:18:13 2013 +0200 ; fix constructor of VCF header ; https://github.com/lindenb/jvarkit/commit/0ebd352c3073e1fc9fea9f5813a26b2f8a67e0c7
Fri Jul 5 08:12:55 2013 +0200 ; misc code added ; https://github.com/lindenb/jvarkit/commit/73fae24c634a5275693493a3899449c78a2474e1
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **vcftrio** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)


## Example

a pedigree file:

```
$  cat pedigree.txt 

A	SAMPLE_P	0	0	0
A	SAMPLE_M	0	0	0
A	SAMPLE_E	SAMPLE_P	SAMPLE_M	0
```


find mendelian incompatibilities:

```
$  gunzip -c input.vcf.gz |\
   java -jar dist/vcftrio.jar -p pedigree.txt | grep -E '(#CHROM|MENDEL=SAMPLE_E)' |\
   verticalize 

(...)
>>> 23
$1	#CHROM	X
$2	POS	0573
$3	ID	rs358
$4	REF	G
$5	ALT	A
$6	QUAL	85.60
$7	FILTER	PASS
$8	INFO	MENDEL=SAMPLE_E
$9	FORMAT	GT:DP:DP4:GP:GQ:PL
$10	SAMPLE_E	0/1:11:6,0,5,0:97,0,122:97:96,0,118
$11	SAMPLE_M	1/1:5:0,0,5,0:134,19,0:19:120,15,0
$12	SAMPLE_P	1/1:6:0,0,6,0:136,22,0:22:121,18,0
<<< 23
(...)
>>> 59
$1	#CHROM	Y
$2	POS	19
$3	ID	rs5678
$4	REF	CA
$5	ALT	C,CAA
$6	QUAL	31.86
$7	FILTER	PASS
$8	INFO	MENDEL=SAMPLE_E
$9	FORMAT	GT:DP:DP4:GP:GQ
$10	SAMPLE_E	2/2:80:3,0,43,34:.,.,108,.,203,0:99
$11	SAMPLE_M	.
$12	SAMPLE_P	1/1:53:0,0,27,26:81,99,0,.,.,.:81
<<< 59

```


 


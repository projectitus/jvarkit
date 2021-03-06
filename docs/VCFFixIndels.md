# VCFFixIndels

Fix samtools indels (for @SolenaLS)


## Usage

```
Usage: vcffixindels [options] Files
  Options:
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    -o, --output
      Output file. Optional . Default: stdout
    --version
      print version and exit

```


## Keywords

 * vcf
 * indel


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
$ make vcffixindels
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcffixindels/VCFFixIndels.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/vcffixindels/VCFFixIndels.java)


<details>
<summary>Git History</summary>

```
Thu Jul 13 20:16:36 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/85b6c9c196e9a065dfd47bee37fe50238af41660
Wed Jun 21 15:27:13 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/034f57d0e8d0399c12b290385d89e498e6138e1d
Tue Jun 6 18:06:17 2017 +0200 ; postponed vcf ; https://github.com/lindenb/jvarkit/commit/bcd52318caf3cd76ce8662485ffaacaabde97caf
Wed May 17 14:09:36 2017 +0200 ; fix typo bioalcidae ; https://github.com/lindenb/jvarkit/commit/9db2344e7ce840df02c5a7b4e2a91d6f1a5f2e8d
Sun May 7 13:21:47 2017 +0200 ; rm xml ; https://github.com/lindenb/jvarkit/commit/f37088a9651fa301c024ff5566534162bed8753d
Mon Apr 24 17:49:35 2017 +0200 ; cont jcommander ; https://github.com/lindenb/jvarkit/commit/d822a90a1eaba26a4d874472ccd45e689e8ba063
Fri Apr 21 18:16:07 2017 +0200 ; scan sv ; https://github.com/lindenb/jvarkit/commit/49b99018811ea6a624e3df556627ebdbf3f16eab
Fri Feb 12 17:17:38 2016 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/c613240c7f1a266ee7e60083ac906c24588bb4f5
Fri Nov 27 15:22:25 2015 +0100 ; cont ; https://github.com/lindenb/jvarkit/commit/04a83d5b9f0e69fd2f7087e519b0de3e2b4f9863
Tue Mar 24 10:29:58 2015 +0100 ; updated tool to fix vcf indels (L/R realign) for multiple ALT #tweet ; https://github.com/lindenb/jvarkit/commit/3d8b518d1a0d5e6daa8911c707e62475041fe38d
Thu Sep 11 09:36:01 2014 +0200 ; problem with java dataInputSTream: writeUTF requires line.length < SHORt_MAX ; https://github.com/lindenb/jvarkit/commit/19eac4ee36909a730903546b50461de3c19a5c1f
Mon May 12 14:06:30 2014 +0200 ; continue moving to htsjdk ; https://github.com/lindenb/jvarkit/commit/011f098b6402da9e204026ee33f3f89d5e0e0355
Mon May 12 10:28:28 2014 +0200 ; first sed on files ; https://github.com/lindenb/jvarkit/commit/79ae202e237f53b7edb94f4326fee79b2f71b8e8
Fri Oct 11 15:39:02 2013 +0200 ; picard v.100: deletion of VcfIterator :-( ; https://github.com/lindenb/jvarkit/commit/e88fab449b04aed40c2ff7f9d0cf8c8b6ab14a31
Sun Sep 15 17:28:38 2013 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/372db15a9147defe95cbd79219fbb62e3ea90005
Fri Sep 6 15:11:11 2013 +0200 ; moved code for latest version of picard (1.97). Using VCFIterator instead of ASciiLineReader ; https://github.com/lindenb/jvarkit/commit/810877c10406a017fd5a31dacff7e8401089d429
Sun Jul 21 14:17:59 2013 +0200 ; vcf trios, added git HASH in METAINF/Manifest ; https://github.com/lindenb/jvarkit/commit/1854d3695563b91471861164f5e8903042493470
Tue Jul 16 13:13:34 2013 +0200 ; moving bigwig to picard ; https://github.com/lindenb/jvarkit/commit/6b32bcf0385fa6d1125b97a7722cf99c82f7ead4
Wed Jul 10 12:34:59 2013 +0200 ; build.dtd and  fixed error in blast-map-annot ; https://github.com/lindenb/jvarkit/commit/f1b5f928840df4c894fdf8a236e4dfabf064db2c
Mon Jul 8 19:18:13 2013 +0200 ; fix constructor of VCF header ; https://github.com/lindenb/jvarkit/commit/0ebd352c3073e1fc9fea9f5813a26b2f8a67e0c7
Mon Jul 8 14:52:31 2013 +0200 ; vcf fix samtools indels ; https://github.com/lindenb/jvarkit/commit/6ef915df9563a3aef75a40995047ab650cf5e30d
Mon Jul 8 13:54:09 2013 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/1130d53716e0bcd1e1729fb5c43a7dc6955d5299
Mon May 6 18:56:46 2013 +0200 ; moving to git ; https://github.com/lindenb/jvarkit/commit/55158d13f0950f16c4a3cc3edb92a87905346ee1
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **vcffixindels** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)





### See also


 *  https://github.com/lindenb/jvarkit/wiki/VCFFixIndels
 *  "Unified Representation of Genetic Variants" http://bioinformatics.oxfordjournals.org/content/early/2015/02/19/bioinformatics.btv112.abstract (hey ! it was published after I wrote this tool !)
 *  https://github.com/quinlan-lab/vcftidy/blob/master/vcftidy.py
 *  http://www.cureffi.org/2014/04/24/converting-genetic-variants-to-their-minimal-representation/





### Example



```
$ curl -s "ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/release/20130502/supporting/input_callsets/si/ALL.wgs.samtools_pass_filter.20130502.snps_indels.low_coverage.sites.vcf.gz" |\
 gunzip -c | java -jar dist/vcfstripannot.jar -k '*' 2> /dev/null |\
 java -jar dist/vcffixindels.jar  2> /dev/null | grep FIX | head -n 15

##INFO=<ID=INDELFIXED,Number=1,Type=String,Description="Fix Indels for @SolenaLS (position|alleles...)">
1   2030133 .   T   TTTTGT,TTTTG    999 PASS    INDELFIXED=2030101|CGTTTTGTTTTGTTTTGTTTTGTTTTGTTTTGT*|CGTTTTGTTTTGTTTTGTTTTGTTTTGTTTTGTTTTGT|CGTTTTGTTTTGTTTTGTTTTGTTTTGTTTTGTTTTG
1   3046430 .   C   CCCT,CCC    999 PASS    INDELFIXED=3046429|TC*|TCCCT|TCCC
1   4258325 rs137902679;rs61115653  A   AAT,AA  999 PASS    INDELFIXED=4258316|CAAAAAAAAA*|CAAAAAAAAAA|CAAAAAAAAAAT
1   5374885 rs59294415  C   CCCC,CCCCA  999 PASS    INDELFIXED=5374881|TCCCC*|TCCCCCCC|TCCCCCCCA
1   5669438 rs143435517 C   CACAT,CAC   999 PASS    INDELFIXED=5669414|TACACACACACACACACACACACAC*|TACACACACACACACACACACACACAC|TACACACACACACACACACACACACACAT
1   5702062 .   A   AA,AAC  999 PASS    INDELFIXED=5702060|TAA*|TAAAC|TAAA
1   5713682 rs70977965  A   AAAAA,AAAAAC    999 PASS    INDELFIXED=5713678|CAAAA*|CAAAAAAAA|CAAAAAAAAC
1   5911136 .   T   TGCCATT,TGCCATTCCAAAGAGGCACTCA  999 PASS    INDELFIXED=5911135|CT*|CTGCCATTCCAAAGAGGCACTCA|CTGCCATT
1   6067269 rs34064079;rs59468731   G   GG,GGC  999 PASS    INDELFIXED=6067261|TGGGGGGGG*|TGGGGGGGGG|TGGGGGGGGGC
1   6069948 .   TC  T,TTC   999 PASS    INDELFIXED=6069933|CTTTTTTTTTTTTTTTC*|CTTTTTTTTTTTTTTTTC|CTTTTTTTTTTTTTTT
1   6480784 .   C   CGGGCCCCAGGCTGCCCGCC,CGGGCCCCAGGCTGCCCGCCT  999 PASS    INDELFIXED=6480783|GC*|GCGGGCCCCAGGCTGCCCGCCT|GCGGGCCCCAGGCTGCCCGCC
1   6829081 rs34184977;rs5772255    A   AAC,AA  999 PASS    INDELFIXED=6829070|TAAAAAAAAAAA*|TAAAAAAAAAAAA|TAAAAAAAAAAAAC
1   7086193 .   AG  A,AAG   999 PASS    INDELFIXED=7086179|TAAAAAAAAAAAAAAG*|TAAAAAAAAAAAAAAAG|TAAAAAAAAAAAAAA
1   8096161 .   T   TATATATATAC,TAT 999 PASS    INDELFIXED=8096143|CATATATATATATATATAT*|CATATATATATATATATATAT|CATATATATATATATATATATATATATAC

```




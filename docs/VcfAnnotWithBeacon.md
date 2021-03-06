# VcfAnnotWithBeacon

Annotate a VCF with ga4gh beacon


## Usage

```
Usage: vcfannotwithbeacon [options] Files
  Options:
    --baseurl
      Beacon Base URL API
      Default: https://beacon-network.org/api
    -B, --bdb
      Optional BerkeleyDB directory to store result. Avoid to make the same 
      calls to beacon
    --build
      genome build
      Default: HG19
    --cert
      ignore SSL certification errors
      Default: false
    -h, --help
      print help and exit
    --helpFormat
      What kind of help
      Possible Values: [usage, markdown, xml]
    --noupdate
      Don't query the variant already having the tag / do not update the 
      existing annotation
      Default: false
    -o, --out
      Output file. Optional . Default: stdout
    --stopOnError
      Stop on network error.
      Default: false
    --tag, -T
      INFO TAG
      Default: BEACON
    --version
      print version and exit

```


## Keywords

 * ga4gh
 * beacon
 * vcf
 * annotation


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
$ make vcfannotwithbeacon
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

[https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/ga4gh/VcfAnnotWithBeacon.java](https://github.com/lindenb/jvarkit/tree/master/src/main/java/com/github/lindenb/jvarkit/tools/ga4gh/VcfAnnotWithBeacon.java)


<details>
<summary>Git History</summary>

```
Thu May 18 18:34:07 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/89cb7d10eaeef051af30f1043698546f555cbcd8
Fri May 12 18:07:46 2017 +0200 ; cont ; https://github.com/lindenb/jvarkit/commit/ca96bce803826964a65de33455e5231ffa6ea9bd
Thu Apr 20 17:17:22 2017 +0200 ; continue transition jcommander ; https://github.com/lindenb/jvarkit/commit/fcf5def101925bea9ddd001d8260cf65aa52d6a0
Wed Apr 19 20:47:05 2017 +0200 ; fix cert ; https://github.com/lindenb/jvarkit/commit/0380c93507ee778fa247d05c556193a428926a73
Wed Apr 19 17:58:48 2017 +0200 ; rm-xml ; https://github.com/lindenb/jvarkit/commit/95f05cfd4e04f5013c22274c49db7bcc4cbbb1c8
```

</details>

## Contribute

- Issue Tracker: [http://github.com/lindenb/jvarkit/issues](http://github.com/lindenb/jvarkit/issues)
- Source Code: [http://github.com/lindenb/jvarkit](http://github.com/lindenb/jvarkit)

## License

The project is licensed under the MIT license.

## Citing

Should you cite **vcfannotwithbeacon** ? [https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md](https://github.com/mr-c/shouldacite/blob/master/should-I-cite-this-software.md)

The current reference is:

[http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

> Lindenbaum, Pierre (2015): JVarkit: java-based utilities for Bioinformatics. figshare.
> [http://dx.doi.org/10.6084/m9.figshare.1425030](http://dx.doi.org/10.6084/m9.figshare.1425030)

 
 


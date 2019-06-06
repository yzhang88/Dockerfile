<!--
 * @Author: xizhihui <zhihui_xi@qq.com>
 * @Date: 2019-06-06 08:10:25
 * @LastEditTime: 2019-06-06 08:10:25
 * @Description: Description here
 -->
## VcfCovExprAnno

Using [VCF Annotation Tools](https://vatools.readthedocs.io/en/latest/index.html) to add coverage(read count) and expression data to a vcf file from bam file or expression table respectively. Some options are discarded from VAtools, you can modify the `annotate` to add in.
According to your input bam (from rna/dna seq) or expression table (from different quantitative softwares), different fields will be added, see below. It should be noted that expression data annotation is only supported for VEP-annotated vcf file.

Type | Format Fields
---|---
Tumor DNA Coverage | AD, DP, and AF
Tumor RNA Coverage |  RAD, RDP, and RAF
Normal DNA Coverage | AD, DP, and AF
Gene Expression | GX
Transcript Expression | TX

### Usage

* build image

```shell
docker build --build-arg author=xizhihui -t xizhihui/vcfcovexpranno:20190606 .
```

* annotatation

```shell
annotate -h
```
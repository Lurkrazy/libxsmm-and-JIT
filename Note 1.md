# LIBXSMM and JIT

## 论文

* BLASFEO: Basic Linear Algebra Subroutines for EmbeddedOptimization（期刊B）

这篇文章在做小规模的时候提到了跟LIBXSMM对比

* LIBXSMM五连SC，两篇是小矩阵[References](https://github.com/hfp/libxsmm#reference)

* [Articles](https://github.com/hfp/libxsmm#articles)

      



## 开源项目源码

JIT会在./bin目录生成二进制可执行文件libxsmm_gemm_generator

由于项目还包含了其他接口，可以看根目录Makefile如何生成libxsmm_gemm_generator以及哪些部分跟JIT有关

## Notes

1、文档中JIT使用方法：[Backend JIT](https://github.com/hfp/libxsmm/blob/master/documentation/libxsmm_be.md)

2、小规模(mnk<23^3)的JIT比直接写的ASM仅慢2% [source](http://sc15.supercomputing.org/sites/all/themes/SC15images/tech_poster/poster_files/post137s2-file2.pdf)

3、目前为止JIT只支持alpha=1，beta=1/0。

4、支持稀疏矩阵，support: dense/dense_asm/sparse (dense creates C code, dense_asm creates ASM)

5、不支持转置矩阵

6、代码自动生成支持多指令集AVX1/AVX2/AVX512，但不支持SSE，[source](https://github.com/hfp/libxsmm/issues/376)

7、


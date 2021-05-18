---
layout: page
title: "/notes"
permalink: /notes/
---

# Notes

* When we pass `-mmcu=am335x.pru0` to pru-gcc compiler, a macro is defined by the compiler which can be used in the code. Macro is `__AM335X_PRU0__`. It is set to `1` if `pru0` option is passed, and it is undefined if `pru1` option is used. It can be used as follows:

```c
#ifdef __AM335X_PRU0__
    #define PRU_NUM 0 
#else
    #define PRU_NUM 1
#endif
```

Refer: [https://github.com/dinuxbg/gnupru/issues/36](https://github.com/dinuxbg/gnupru/issues/36)

# Resources that helped a lot

* [https://github.com/drifter1/compiler](https://github.com/drifter1/compiler)
* [http://web.cs.ucla.edu/classes/spring08/cs259/llvm-2.2/docs/WritingAnLLVMBackend.html](http://web.cs.ucla.edu/classes/spring08/cs259/llvm-2.2/docs/WritingAnLLVMBackend.html)
* [https://babel.ls.fi.upm.es/~pablo/Papers/Toys/C-compiler/intro.html](https://babel.ls.fi.upm.es/~pablo/Papers/Toys/C-compiler/intro.html)
* [https://github.com/anthony-y/toy-compiler](https://github.com/anthony-y/toy-compiler)
* [https://github.com/camilne/toy-compiler](https://github.com/camilne/toy-compiler)
* [https://github.com/ehostunreach/toy](https://github.com/ehostunreach/toy)
* [https://aquamentus.com/flex_bison.html](https://aquamentus.com/flex_bison.html)
* [https://www.youtube.com/playlist?list=PLIrl0f9NJZy4oOOAVPU6MyRdFjJFGtceu](https://www.youtube.com/playlist?list=PLIrl0f9NJZy4oOOAVPU6MyRdFjJFGtceu)
* [https://www.jonathanbeard.io/tutorials/FlexBisonC++](https://www.jonathanbeard.io/tutorials/FlexBisonC++)
* [https://gnuu.org/2009/09/18/writing-your-own-toy-compiler/](https://gnuu.org/2009/09/18/writing-your-own-toy-compiler/)
* [https://www.youtube.com/playlist?list=PLkB3phqR3X43IRqPT0t1iBfmT5bvn198Z](https://www.youtube.com/playlist?list=PLkB3phqR3X43IRqPT0t1iBfmT5bvn198Z)
* [https://medium.com/@ilyarudyak/flex-tutorial-9ed34fd1ff28](https://medium.com/@ilyarudyak/flex-tutorial-9ed34fd1ff28)
* [https://www.youtube.com/playlist?list=PLEbnTDJUr_IcPtUXFy2b1sGRPsLFMghhS](https://www.youtube.com/playlist?list=PLEbnTDJUr_IcPtUXFy2b1sGRPsLFMghhS)
* [https://www.youtube.com/playlist?list=PLEbnTDJUr_IcPtUXFy2b1sGRPsLFMghhS](https://www.youtube.com/playlist?list=PLEbnTDJUr_IcPtUXFy2b1sGRPsLFMghhS)
* [https://ruslanspivak.com/lsbasi-part7/](https://ruslanspivak.com/lsbasi-part7/)
* [https://medium.com/basecs/leveling-up-ones-parsing-game-with-asts-d7a6fc2400ff](https://medium.com/basecs/leveling-up-ones-parsing-game-with-asts-d7a6fc2400ff)
* [https://github.com/attractivechaos/klib](https://github.com/attractivechaos/klib)
* [https://github.com/rxi/vec](https://github.com/rxi/vec)
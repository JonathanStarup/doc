# Dependencies and Licensing #

Flix is licensed under the [Apache License, Version 2.0](https://github.com/flix/flix/blob/master/LICENSE.md). 

Flix depends on the following libraries:

| Library                                              | License                     | Required* | Bundled** | Module             |
| ---------------------------------------------------- | --------------------------- | :-------: | :-------: | ------------------ |
| [ASM](http://asm.ow2.org/)                           | BSD 3-Clause License        |    Yes    |    Yes    | Bytecode           |
| [Parboiled2](https://github.com/sirthias/parboiled2) | Apache License, Version 2.0 |    Yes    |    Yes    | Parsing            |
| [Shapeless](https://github.com/milessabin/shapeless) | Apache License, Version 2.0 |    Yes    |    Yes    | Parsing            |
| [ScalaTest](http://www.scalatest.org/)               | Apache License, Version 2.0 |    Yes    |     No    | Testing            |
| [scopt](https://github.com/scopt/scopt)              | MIT License                 |    Yes    |    Yes    | Commandline Parser |
| [Z3](https://github.com/Z3Prover/z3)                 | Apache License, Version 2.0 |     No    |     No    | Verifier           |
| [Bootstrap](http://getbootstrap.com/)                | MIT License                 |     No    |    Yes    | Web-based Debugger |
| [ChartJS](http://www.chartjs.org/)                   | MIT License                 |     No    |    Yes    | Web-based Debugger |
| [jQuery](https://jquery.com/)                        | MIT License                 |     No    |    Yes    | Web-based Debugger |
| [JSON4s](https://github.com/json4s/json4s)           | Apache License, Version 2.0 |     No    |    Yes    | Web-based Debugger |
| [NumeralJS](http://numeraljs.com/)                   | MIT License                 |     No    |    Yes    | Web-based Debugger |
| [React](https://github.com/facebook/react)           | BSD 3-Clause License        |     No    |    Yes    | Web-based Debugger |

*Required: The library is required to build and run Flix. 

**Bundled: The library is bundled with the Flix JAR.

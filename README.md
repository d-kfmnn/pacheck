[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Practical Algebraic Calculus Proof Checker
=================================================

To compile use `./configure.sh` and then `make`.
Furthermore, you need to have installed `gmp` to run `Pacheck`.


Usage: 
----------------------------------
`./pacheck [ <option> ... ]  [ <input> <proof>] [<target>]`

where `<option>` is one of the following

  `-h | --help            print this command line option summary and exit`  

  `-s | --no-target       only check inferences but not that proof generates target`  

  `-v | --verbose         get verbose output on number of checked inferences (every 500 rules)`  

  `-e | --use-exponents   turn off implicit reduction of exponents`  

  `-i | --no-indices      turn off usage of indices`   

  `-d | --no-delete       ignore delete rules`  

  `--print        print polynomials in failing checks for better diagnosis`  

  `--sparse       use spaces to make printed polynomials easier to read`  

The `<input>` argument should point to a file with the
original set of polynomials and <proof> is a path to a proof file
interpreted as a sequence of inferences in the polynomial calculus.
The tool checks that all inferences in the sequence are correct.

The `<target>` is optional. Ommiting this file has the same effect as choosing option `-s`
It should point to a file with a single polynomial which
should be generated by the proof.
The exit code is zero if and only if all checks succeed.

![OAWK](/images/LOGO)

<div align="center">
  <a href="https://www.linkedin.com/in/robertsean1995/"><img align="middle" src="https://img.shields.io/badge/LinkedIn-%230A66C2.svg?style=for-the-badge&logo=linkedin&logoColor=white"></a>
&nbsp;
  <a href="mailto:robertsean1995@gmail.com"><img align="middle" src="https://img.shields.io/badge/Email-%23EA4335.svg?style=for-the-badge&logo=gmail&logoColor=white"></a>
</div>

<hr>

**OAWK Programming ("o/awk/p" or "Oawk") is an interpreter of the Awk programming language that extends functionality by adding object orientation and various supporting capabilities. This idea was originally conceived while trying to improve my own offensive security methodologies by marrying Bash and Awk. The pseudo-class structure I tried to implement in Bash was not sufficient, so I decided to fork my preferred Awk implementation. Oawk is a fork of [Mawk](https://invisible-island.net/mawk/).**

**The name "Oawk" is derived from "Object-Oriented Awk" and follows the same naming convention as other Awk implementations (e.g. Nawk, Gawk, Mawk, etc.). The logo is made to resemble a regular expression in the same style as Grep ("g/re/p"), and the chickens are a lighthearted reference to the programming methodology for which Oawk was created. See [Bawk](https://github.com/robertsean1995/bawk) for more information.**

- Preserves traditional Awk syntax, semantics, and text-processing capabilities.
- Extends Awk with native classes, objects, instance state, methods, and lifecycle behavior.
- Treats functions as first-class runtime values that can be dynamically manipulated.
- Uses decorators to introduce a more dynamic runtime model beyond basic object orientation.
- Provides runtime reflection for inspecting Oawk values and objects.
- Includes an interactive REPL for exploratory and general-purpose programming.
- Remains based on Mawk, retaining its small and performance-oriented foundation.

<hr>

## Table of Contents
- [1 Introduction](#1-introduction)
  - [1a On the Capitalization of Awk](#1a-on-the-capitalization-of-awk)
- [2 Features](#2-features)
  - [2a Examples](#2a-examples)
- [3 Performance Metrics](#3-performance-metrics)
- [4 Installation](#4-installation)
  - [4a Dependencies](#4a-dependencies)
  - [4b Building and Installing](#4b-building-and-installing)
  - [4c Testing](#4c-testing)
  - [4d Uninstallation](#4d-uninstallation)
- [5 Supporting Tools](#5-supporting-tools)

<hr>

# Introduction

It preserves Awk's original text-processing design while adding classes, objects, methods, first-class functions, decorators, reflection, and an interactive Read-Eval-Print Loop ("REPL")

## On the Capitalization of Awk

This section is strictly due to the universal inconsistency I noticed when beginning this project. And it is a pet peeve, to be honest. There is no universally followed convention for the capitalization of "Awk". Across books, manuals, and any other documentation, especially online documentation, the language can be found written as "AWK", "Awk", or "awk". I have even noticed--in some cases--the name can take any of the aforementioned forms from within the same source. The primary example is *The AWK Programming Language* (1988), published by Alfred Aho, Brian Kernighan, and Peter Weinberger. This is the official reference manual for Awk. The title of the book writes the name as "AWK"; however, the authors refer to it as "Awk" starting on the first page of the Preface. Then "awk" is additionally established as the name of the command-line utility used to invoke the tool and language. As a result, all three forms have substantial historical precedent from within the same source. 

And the same inconsistency extends to individual Awk flavors (e.g. Nawk, Gawk, Mawk, etc.). Names may appear with different capitalization depending on whether a source is discussing the project and implementation, the command-line utility, or simply following its own stylistic convention. Consequently, Oawk adopts a consistent distinction throughout its documentation, both for itself and when referring to Awk and its flavors. "Awk" refers to the original implementation and programming language, while "Nawk", "Gawk", "Mawk", and "Oawk" refer to their respective flavors as projects. Lowercase forms such as `awk`, `nawk`, `gawk`, `mawk`, and `oawk` refer specifically to the command-line utilities and will be wrapped in code blocks. This makes statements like "Oawk is invoked with `oawk`" clear and unambiguous. The same capitalization convention is followed by the [Bawk](https://github.com/robertsean1995/bawk) programming methodology.

# Features

[Overview of Oawk's language features, including the extent of its object orientation, first-class functions, decorators and their effect on the runtime model, reflection, the REPL, and AWK compatibility.]

## Examples

### Classes and Objects

### Dynamic Functions and Decorators

# Performance Metrics

It is intended for Oawk to preserve Mawk's performance-oriented foundation. To measure the performance impact of these changes, Oawk is benchmarked alongside Mawk, Gawk, Python, and Bash using the same computational workload.

The benchmark performs one billion iterations of a simple arithmetic loop. Each implementation is measured using ```/usr/bin/time -v```. The test is repeated three (3) times per implementation. The reported results are the averages of **User time (seconds)**, representing CPU time spent executing the program in user mode, and **Maximum resident set size (kbytes)**, representing peak physical memory usage during execution. This is not an *exhaustive* comparison. 

These benchmarks are intended as a focused comparison of raw loop execution and memory overhead rather than a comprehensive measure of overall language performance. They simply provide a baseline for evaluating how closely Oawk retains Mawk's performance characteristics after so many changes and how those baselines compare to other languages. Bash is just here to show what it is like for a normal person to compete in the Olympics. 

<table>
  <thead>
    <tr>
      <th>Tool</th>
      <th>Test</th>
      <th>Average User Time (seconds)</th>
      <th>Average Peak Memory (kbytes)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Oawk</td>
      <td><pre>/usr/bin/time -v oawk 'BEGIN {
    for (i = 1; i <= 1000000000; i++)
        sum += i * i
    print sum }'</pre></td>
      <td>24.91</td>
      <td>3407</td>
    </tr>
    <tr>
      <td>Mawk</td>
      <td><pre>/usr/bin/time -v mawk 'BEGIN {
    for (i = 1; i <= 1000000000; i++)
        sum += i * i
    print sum }'</pre></td>
      <td>23.14</td>
      <td>2853</td>
    </tr>
    <tr>
      <td>Gawk</td>
      <td><pre>/usr/bin/time -v gawk 'BEGIN {
    for (i = 1; i <= 1000000000; i++)
        sum += i * i
    printf "%.0f\n", sum }'</pre></td>
      <td>52.84</td>
      <td>4659</td>
    </tr>
    <tr>
      <td>Python</td>
      <td><pre>/usr/bin/time -v python3 -c '
total = 0
for i in range(1, 1000000001):
    total += i * i
print(total)'</pre></td>
      <td>111.44</td>
      <td>9139</td>
    </tr>
    <tr>
      <td>Bash</td>
      <td><pre>/usr/bin/time -v bash -c '
sum=0
for ((i = 1; i <= 1000000000; i++)); do
    ((sum += i * i))
done
printf "%d\n" "$sum"'</pre></td>
      <td>1741.16</td>
      <td>3619</td>
    </tr>
  </tbody>
</table>

**Results:** Oawk was 7.65% slower than Mawk, with peak memory usage being 19.42% higher.

# Installation

### Dependencies

### Building and Installing

make && sudo make install

### Testing

make check

### Uninstallation

sudo make uninstall && make clean

# Supporting Tools

Formatter

Color syntax file






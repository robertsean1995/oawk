![BAWKP](/images/LOGO)

<div align="center">
  <a href="https://www.linkedin.com/in/robertsean1995/"><img align="middle" src="https://img.shields.io/badge/LinkedIn-%230A66C2.svg?style=for-the-badge&logo=linkedin&logoColor=white"></a>
&nbsp;
  <a href="mailto:robertsean1995@gmail.com"><img align="middle" src="https://img.shields.io/badge/Email-%23EA4335.svg?style=for-the-badge&logo=gmail&logoColor=white"></a>
</div>

<hr>

**OAWK Programming ("o/awk/p" or "Oawk") is an object-oriented extension of AWK, implemented as a fork of mawk. It preserves AWK's lightweight, text-processing-oriented design while extending the language with classes, objects, methods, first-class functions, decorators, reflection, and an interactive REPL. Oawk is intended to explore how far AWK can be extended toward object-oriented and dynamic programming without abandoning the language that makes AWK distinct. Oawk is a fork of [Mawk](https://invisible-island.net/mawk/).**

**The name "Oawk" is derived from "Object-Oriented Awk" and follows the same naming convention as other Awk implementations. The logo is made to resemble a regular expression in the same style as Grep ("g/re/p"), and the tree is a lighthearted reference to how I have grown to pronounce "Oawk"; it has a similar enough spelling to the deciduous hardwoods, so I simply started pronouncing it as "oak".**
- Extends AWK with native classes, objects, instance state, methods, and lifecycle behavior.
- Preserves traditional AWK syntax, semantics, and text-processing capabilities.
- Treats functions as first-class runtime values that can be stored, passed, returned, and dynamically replaced.
- Uses decorators to introduce a more dynamic runtime model beyond basic object-oriented syntax and semantics.
- Provides runtime reflection for inspecting Oawk values and objects.
- Includes an interactive REPL for exploratory and general-purpose programming.
- Remains based on mawk, retaining its small and performance-oriented foundation.

<hr>

## Table of Contents
- [1 Introduction](#1-introduction)
  - [1a On AWK Capitalization](#1a-on-awk-capitalization)
- [2 Features](#2-features)
  - [2a Examples](#2a-examples)
- [3 Performance Metrics](#3-performance-metrics)
- [4 Installation](#4-installation)
  - [4a Dependencies](#4a-dependencies)
  - [4b Building and Installing](#4b-building-and-installing)
  - [4c Testing](#4c-testing)
  - [4d Uninstallation](#4d-uninstallation)

<hr>

# Introduction

## On Awk Capitalization

a word on the captilization of awk

documenation is wildly inconsistent

is it AWK or Awk or awk
    the title of THE book says AWK and Google says AWK
    but literally in the same book, the authors refer to it as Awk

differences between commandline tools (lowercase) and official documentation

my bawkp follows this same convention

# Features

[Overview of Oawk's language features, including the extent of its object orientation, first-class functions, decorators and their effect on the runtime model, reflection, the REPL, and AWK compatibility.]

## Examples

### Classes and Objects

### Dynamic Functions and Decorators

# Performance Metrics

[One-line description of the benchmark workload and measurement methodology.]

| Implementation | Time | Memory |
|---|---:|---:|
| Oawk | | |
| mawk | | |
| gawk | | |
| Python | | |
| Bash | | |

# Installation

Dependencies

Building and Installing

make && sudo make install

Testing

make check

Uninstallation

sudo make uninstall && make clean

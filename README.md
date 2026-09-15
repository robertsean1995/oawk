![LOGO](/images/LOGO)

<div align="center">
  <a href="https://www.linkedin.com/in/robertsean1995/"><img align="middle" src="https://img.shields.io/badge/LinkedIn-%230A66C2.svg?style=for-the-badge&logo=linkedin&logoColor=white"></a>
&nbsp;
  <a href="mailto:robertsean1995@gmail.com"><img align="middle" src="https://img.shields.io/badge/Email-%23EA4335.svg?style=for-the-badge&logo=gmail&logoColor=white"></a>
</div>

<hr>

**OAWK Programming ("o/awk/p" or "Oawk") is an interpreter of the Awk programming language that extends functionality by adding object orientation and various supporting capabilities. This idea was originally conceived while trying to improve my own offensive security methodologies by marrying Bash and Awk. The pseudo-class structure I tried to implement from within Bash was not sufficient, so I forked my preferred Awk flavor and Oawk was born. Oawk is a fork of [Mawk](https://invisible-island.net/mawk/).**

**The name "Oawk" is derived from "Object-Oriented Awk" and follows the same naming convention as other Awk flavors (e.g. Nawk, Gawk, Mawk, etc.). The logo is made to resemble a regular expression in the same style as Grep ("g/re/p"), and the chickens are a lighthearted reference to the programming methodology for which Oawk was created. See [Bawk](https://github.com/robertsean1995/bawk) for more information.**

- Preserves traditional Awk syntax, semantics, and text-processing capabilities.
- Extends Awk with native classes, objects, instance state, methods, and lifecycle behavior.
- Treats functions as first-class runtime values that can be dynamically manipulated.
- Uses decorators to introduce a more dynamic runtime model beyond basic object orientation.
- Provides runtime reflection for inspecting Oawk values and objects.
- Includes an interactive REPL for exploratory and general-purpose programming.
- Remains based on Mawk, retaining its small and performance-oriented foundation.

<hr>

<div align="center">
  <img src="/images/DEMO" alt="DEMO">
</div>

<hr>

# 1 Introduction

This project originated while developing [Bawk](https://github.com/robertsean1995/bawk), an unconventional programming methodology that focused on combining Bash and Awk for offensive security and general-purpose programming. Early attempts used Bash to provide a pseudo-object-oriented wrapper for Awk. That approach technically worked, but it blurred the responsibility boundaries that held the methodology together and exposed a more fundamental limitation. Because Mawk was already my preferred Awk flavor for the project, it became the foundation for creating a solution. Oawk is the result: an object-oriented fork of Mawk that preserves the philosophy of Awk.

Oawk's object-oriented model draws deliberate inspiration from Python, providing that familiar reference point for classes, objects, methods, and dynamic behavior while adapting those concepts to Awk. Object orientation remains an extension of the existing language, rather than a replacement for its traditional programming model. Mawk remains the baseline against which that evolution is measured, with Oawk building upon its parser, runtime, execution model, and performance-oriented foundation where necessary to provide a broader programming environment. The result is still Awk at its core.

### On the Capitalization of Awk

This section is strictly due to the universal inconsistency I noticed when beginning this project. And it is a pet peeve, to be honest. There is no universally followed convention for the capitalization of "Awk". Across books, manuals, and any other documentation, especially online documentation, the language can be found written as "AWK", "Awk", or "awk". I have even noticed--in some cases--the name can take any of the aforementioned forms from within the same source. The primary example is *The AWK Programming Language* (1988), published by Alfred Aho, Brian Kernighan, and Peter Weinberger. This is the official reference manual for Awk. The title of the book writes the name as "AWK"; however, the authors refer to it as "Awk" starting on the first page of the Preface. Then "awk" is established as the name of the command-line utility used to invoke the tool and language. As a result, all three forms have substantial historical precedent from within the same source. 

And the same inconsistency extends to individual Awk flavors (e.g. Nawk, Gawk, Mawk, etc.). Names may appear with different capitalization depending on whether a source is discussing the project and implementation, the command-line utility, or simply following its own stylistic convention. Consequently, Oawk adopts a consistent distinction throughout its documentation, both for itself and when referring to Awk and its flavors. "Awk" refers to the original implementation and programming language, while "Nawk", "Gawk", "Mawk", and "Oawk" refer to their respective flavors as projects. Lowercase forms such as `awk`, `nawk`, `gawk`, `mawk`, and `oawk` refer specifically to the command-line utilities and will be wrapped in code blocks. This makes statements like "Oawk is invoked with `oawk`" clear and unambiguous. The same capitalization convention is followed by the [Bawk](https://github.com/robertsean1995/bawk) programming methodology.

# 2 Features

The following are the primary language and runtime features introduced by Oawk:

- Classes and Objects — Native class definitions, object instantiation, instance state, methods, method calls, and object references.
- Inheritance — Classes can inherit from other classes, allowing methods and behavior to be extended or overridden.
- Object Lifecycle Methods — Special methods provide behavior for object initialization, string conversion, and destruction.
- First-Class Functions — Functions can be stored in variables, passed as arguments, returned from functions, and invoked dynamically.
- Decorators — Functions can be wrapped or transformed using `@decorator` syntax, building on Oawk's first-class function support.
- Runtime Reflection — Programs can inspect values, functions, classes, and objects while running.
- Dynamic Object Model — Object state and function behavior remain dynamic, rather than relying on a static type system.
- Interactive REPL — Oawk can be used interactively through a persistent Read-Eval-Print Loop ("REPL"), similar to Python. 
- Awk Compatibility — Traditional Awk command syntax and programming remain intact, including pattern-action processing, associative arrays, regular expressions, fields, and records.
  - Mawk Foundation — Oawk remains based directly on Mawk and retains its lightweight, performance-oriented execution model. See [Mawk](https://invisible-island.net/mawk/) for more information. 

### Examples

To review fullf unctionality of Oawk, I will refer you to the tests/oibjects/ directory, rather than further restating them here in great detail. 

Oawk includes a collection of executable examples as part of its regression suite. Rather than duplicating those scripts here, the `tests/objects/` directory contains examples covering Oawk's object-oriented and supporting language features individually.

For a complete example, see `000_integration_project.awk`. This program is intended as an integration demonstration of Oawk's implementation. The remaining files in `tests/objects/` provide focused examples of individual behaviors and can be used as a reference when experimenting with a specific feature.

# 3 Performance Metrics

It is intended for Oawk to preserve Mawk's performance-oriented foundation. To measure the performance impact of these changes, Oawk is benchmarked alongside Mawk, Gawk, Python, and Bash using the same computational workload.

The benchmark performs one billion iterations of a simple arithmetic loop. Each tool is measured using `/usr/bin/time -v`. The test is repeated three (3) times per tool. The reported results are the averages of **User time (seconds)**, representing CPU time spent executing the program in user mode, and **Maximum resident set size (kbytes)**, representing peak physical memory usage during execution. This is not an *exhaustive* comparison. 

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

# 4 Installation

Oawk is built and installed from source using the included build system. The standard installation places `oawk` and its supporting documentation and tools on the system. The following packages are required to build and test Oawk:

- `gcc` — compiler used to build Oawk
- `make` — executes build and installation rules
- `bison` — generates the parser
- `readline` — used by the REPL
- `expect` — used to test REPL behavior

### Building and Testing

I have plans to eventually get this on official Linux distribution repositories for installation. For now, download the source code from this repository, and navigate to that directory. Compile the project and install system-wide with:

```
make && sudo make install
```

Oawk includes a regression suite covering inherited Mawk behavior and Oawk-specific language and runtime features. After building the project, run the complete test suite from the root of the Oawk repository with `make check`. After installation and testing, Oawk can be invoked with `oawk`. Traditional Awk programs can be executed directly from the command line, `oawk 'BEGIN { print "Hello, world!" }'`, or loaded from a file using the standard `-f` option, `oawk -f program.awk`.

### Uninstallation

From the root of the Oawk repository, you can remove the system-wide installation and remove generated build files from the source tree with:

```
sudo make uninstall && make clean
```

# 5 Supporting Tools

### Formatter

I'M GOING FOR PYTHONIC

Oawk includes a built-in formatter through the `-W pretty` and `-W prettier` options. Both options format Oawk source code according to the same formatting rules, with `-W pretty` printing to stdout and `-W prettier` actually replacing the source input file with the formatted code. For example:

`oawk -W prettier example.awk`

The formatting style can be considered controversial. Oawk takes additional inspiration from Python by following a lot of the same formatting conventions; conventions that focus on readability and indentation. All of the syntactic components required by Awk remain present; Oawk's formatter simply makes different stylistic choices about how those components are arranged. This is really the main reason why I wanted to provide a formatter as built-in functionality. It's easier to follow these rules if you can just run the formatter and move on, rather than try and memorize a bunch of new rules. 

One deliberate example is the handling of closing braces. Oawk avoids unnecessarily cascading closing braces across multiple lines. A closing brace may instead remain on the same line as another closing brace where the structure remains clear. This emphasizes the same readability and indentation style as Python. This is a stylistic decision rather than a syntactic requirement. Oawk accepts ordinary Awk formatting. The formatter simply provides a canonical style for users who want consistent formatting across Oawk programs. This is also in direct support of [Bawk](https://github.com/robertsean1995/bawk), where readability is survival. 

For example:

```
class User {
    function describe() {
        if (self.name != "") {
            print self.name } } }
```

rather than:

```
class User {
    function describe() {
        if (self.name != "") {
            print self.name
        }
    }
}
```

### Syntax Highlighting 

Oawk's additional syntax is not recognized by standard Awk syntax definitions; therefore, an updated `awk.tmLanguage` file is included to provide syntax highlighting for Oawk-specific constructs in VS Code. This file is designed to be used with the "Awk" extension for VS Code by Donald Mull Jr.

The extension is published under the identifier `luggage66.awk`. After installing the extension, locate its syntax directory. On Linux, version 0.0.2 is normally located at:

`~/.vscode/extensions/luggage66.awk-0.0.2/syntaxes/awk.tmLanguage`

Replace the existing file with the `awk.tmLanguage` file included in `tools/awk.tmLanguage`. After replacing the file, restart VS Code or run `Developer: Reload Window`. Unsaved files with new Oawk code will often be detected as JavaScript or C++ in VS Code, so it is recommended to save the new file explicitly as an `.awk` file for the highlighting to work as expected. 

<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# AFINN-96

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> A [list][afinn] of English words rated for [valence][valence].

<section class="installation">

## Installation

```bash
npm install @stdlib/datasets-afinn-96
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).
-   To use as a general utility for the command line, install the corresponding [CLI package][cli-section] globally.

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var afinn96 = require( '@stdlib/datasets-afinn-96' );
```

#### afinn96()

Returns a [list][afinn] of `1468` unique English words (and phrases) rated for [valence][valence]. Negative words have a negative [valence][valence] (`[-5,0)`). Positive words have a positive [valence][valence] (`(0,5]`). Neutral words have a [valence][valence] of `0`.

```javascript
var words = afinn96();
/* returns
    [
        ['abandon',-2],
        ['abandons',-2],
        ['abandoned',-2],
        ['absentee',-1],
        ['absentees',-1],
        ['aboard',1],
        ['abducted',-2],
        ['abduction',-2],
        ['abductions',-2],
        ['abuse',-3],
        ['abused',-3],
        ...
    ]
*/
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   The list is an earlier version of [AFINN-111][afinn].
-   The list contains duplicated words.
-   The list includes misspelled words. Their presence is intentional, as such misspellings frequently occur in social media content.
-   All words are lowercase.
-   Some "words" are phrases; e.g., `cashing in`, `cool stuff`.
-   Words may contain apostrophes; e.g., `can't stand`.
-   Words may contain dashes; e.g., `cover-up`, `made-up`. 

</section>

<!-- /.notes -->

<section class="examples">

<!-- TODO: more creative example; possibly counting the number of negative words per sentence in two pieces of text. -->

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var afinn96 = require( '@stdlib/datasets-afinn-96' );

var words;
var dict;
var len;
var i;

words = afinn96();

// Convert to a dictionary...
len = words.length;
dict = {};
for ( i = 0; i < len; i++ ) {
    dict[ words[i][0] ] = words[i][1];
}
console.dir( dict );
```

</section>

<!-- /.examples -->

* * *

<section class="cli">

## CLI

<section class="installation">

## Installation

To use as a general utility, install the CLI package globally

```bash
npm install -g @stdlib/datasets-afinn-96-cli
```

</section>

<!-- CLI usage documentation. -->

<section class="usage">

### Usage

```text
Usage: afinn-96 [options]

Options:

  -h,    --help                Print this message.
  -V,    --version             Print the package version.
         --format fmt          Output format: 'csv' or 'ndjson'.
```

</section>

<!-- /.usage -->

<section class="notes">

### Notes

-   The CLI supports two output formats: comma-separated values ([CSV][csv]) and newline-delimited JSON ([NDJSON][ndjson]). The default output format is [CSV][csv].

</section>

<!-- /.notes -->

<section class="examples">

### Examples

```bash
$ afinn-96
word,valence
abandon,-2
abandons,-2
abandoned,-2
...
```

</section>

<!-- /.examples -->

</section>

<!-- /.cli -->

* * *

<section class="references">

## References

-   Nielsen, Finn Årup. 2011. "A new ANEW: Evaluation of a word list for sentiment analysis in microblogs." In _Proceedings of the ESWC2011 Workshop on 'Making Sense of Microposts': Big things come in small packages._, 718:93–98. CEUR Workshop Proceedings. <http://ceur-ws.org/Vol-718/paper_16.pdf>.
-   Hansen, Lars Kai, Adam Arvidsson, Finn Årup Nielsen, Elanor Colleoni, and Michael Etter. 2011. "Good Friends, Bad News - Affect and Virality in Twitter." In _Future Information Technology: 6th International Conference, FutureTech 2011, Loutraki, Greece, June 28-30, 2011, Proceedings, Part II_, edited by James J. Park, Laurence T. Yang, and Changhoon Lee, 34–43. Berlin, Heidelberg: Springer Berlin Heidelberg. doi:[10.1007/978-3-642-22309-9_5][@hansen:2011a].

</section>

<!-- /.references -->

<!-- <license> -->

## License

The data files (databases) are licensed under an [Open Data Commons Attribution 1.0 License][odc-by-1.0] and their contents are licensed under a [Creative Commons Attribution 4.0 International Public License][cc-by-4.0]. The original dataset is attributed to Finn Årup Nielsen and can be found [here][afinn]. The software is licensed under [Apache License, Version 2.0][apache-license].

<!-- </license> -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/datasets-afinn-111`][@stdlib/datasets/afinn-111]</span><span class="delimiter">: </span><span class="description">A list of English words rated for valence.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## Copyright

Copyright &copy; 2016-2024. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/datasets-afinn-96.svg
[npm-url]: https://npmjs.org/package/@stdlib/datasets-afinn-96

[test-image]: https://github.com/stdlib-js/datasets-afinn-96/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/datasets-afinn-96/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/datasets-afinn-96/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/datasets-afinn-96?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/datasets-afinn-96.svg
[dependencies-url]: https://david-dm.org/stdlib-js/datasets-afinn-96/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[cli-section]: https://github.com/stdlib-js/datasets-afinn-96#cli
[cli-url]: https://github.com/stdlib-js/datasets-afinn-96/tree/cli
[@stdlib/datasets-afinn-96]: https://github.com/stdlib-js/datasets-afinn-96/tree/main

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/datasets-afinn-96/tree/deno
[deno-readme]: https://github.com/stdlib-js/datasets-afinn-96/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/datasets-afinn-96/tree/umd
[umd-readme]: https://github.com/stdlib-js/datasets-afinn-96/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/datasets-afinn-96/tree/esm
[esm-readme]: https://github.com/stdlib-js/datasets-afinn-96/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/datasets-afinn-96/blob/main/branches.md

[afinn]: http://www2.imm.dtu.dk/pubdb/views/publication_details.php?id=6010

[@hansen:2011a]: https://doi.org/10.1007/978-3-642-22309-9_5

[valence]: https://en.wikipedia.org/wiki/Valence_%28psychology%29

[csv]: https://tools.ietf.org/html/rfc4180

[ndjson]: http://specs.frictionlessdata.io/ndjson/

[odc-by-1.0]: http://opendatacommons.org/licenses/by/1.0/

[cc-by-4.0]: http://creativecommons.org/licenses/by/4.0/

[apache-license]: https://www.apache.org/licenses/LICENSE-2.0

<!-- <related-links> -->

[@stdlib/datasets/afinn-111]: https://github.com/stdlib-js/datasets-afinn-111

<!-- </related-links> -->

</section>

<!-- /.links -->

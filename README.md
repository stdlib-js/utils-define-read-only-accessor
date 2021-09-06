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

# Read-Only Accessor

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] [![dependencies][dependencies-image]][dependencies-url]

> [Define][@stdlib/utils/define-property] a **read-only** accessor.

<section class="installation">

## Installation

```bash
npm install @stdlib/utils-define-read-only-accessor
```

</section>

<section class="usage">

## Usage

```javascript
var setReadOnlyAccessor = require( '@stdlib/utils-define-read-only-accessor' );
```

#### setReadOnlyAccessor( obj, prop, getter )

[Defines][@stdlib/utils/define-property] a **read-only** accessor.

<!-- run throws: true -->

```javascript
function getter() {
    return 'bar';
}

var obj = {};

setReadOnlyAccessor( obj, 'foo', getter );

obj.foo = 'boop';
// throws <Error>
```

</section>

<!-- /.usage -->

<section class="notes">
    
## Notes

-   Read-only accessors are **enumerable** and **non-configurable**.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var setReadOnlyAccessor = require( '@stdlib/utils-define-read-only-accessor' );

function Foo( name ) {
    if ( !(this instanceof Foo) ) {
        return new Foo( name );
    }
    setReadOnlyAccessor( this, 'name', getName );
    return this;

    function getName() {
        return name;
    }
}

var foo = new Foo( 'beep' );

try {
    foo.name = 'boop';
} catch ( err ) {
    console.error( err.message );
}
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   [`@stdlib/utils/define-read-only-property`][@stdlib/utils/define-read-only-property]: define a read-only property.
-   [`@stdlib/utils/define-read-write-accessor`][@stdlib/utils/define-read-write-accessor]: define a read-write accessor.
-   [`@stdlib/utils/define-write-only-accessor`][@stdlib/utils/define-write-only-accessor]: define a write-only accessor.

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

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/utils-define-read-only-accessor.svg
[npm-url]: https://npmjs.org/package/@stdlib/utils-define-read-only-accessor

[test-image]: https://github.com/stdlib-js/utils-define-read-only-accessor/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/utils-define-read-only-accessor/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/utils-define-read-only-accessor/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/utils-define-read-only-accessor?branch=main

[dependencies-image]: https://img.shields.io/david/stdlib-js/utils-define-read-only-accessor.svg
[dependencies-url]: https://david-dm.org/stdlib-js/utils-define-read-only-accessor/main

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/utils-define-read-only-accessor/main/LICENSE

[@stdlib/utils/define-property]: https://github.com/stdlib-js/utils-define-property

<!-- <related-links> -->

[@stdlib/utils/define-read-only-property]: https://github.com/stdlib-js/utils-define-read-only-property

[@stdlib/utils/define-read-write-accessor]: https://github.com/stdlib-js/utils-define-read-write-accessor

[@stdlib/utils/define-write-only-accessor]: https://github.com/stdlib-js/utils-define-write-only-accessor

<!-- </related-links> -->

</section>

<!-- /.links -->

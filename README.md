# Test Files

[This repo](https://github.com/neomutt/neomutt-test-files) contains test files
for the main NeoMutt source.

The [NeoMutt source code](https://github.com/neomutt/neomutt) comes with a set
of [unit tests](https://en.wikipedia.org/wiki/Unit_testing).

They cover the [Address](https://neomutt.org/code/lib_address.html),
[Core](https://neomutt.org/code/lib_core.html),
[Email](https://neomutt.org/code/lib_email.html)
and [Mutt](https://neomutt.org/code/lib_mutt.html) libraries.

These files are released under the GPL v2+ (GNU General Public License). 
See [LICENSE.md](LICENSE.md).

See also: [Test code coverage](https://coveralls.io/github/neomutt/neomutt)

## Setup

```sh
git clone https://github.com/neomutt/neomutt
git clone https://github.com/neomutt/neomutt-test-files

# NEOMUTT_TEST_DIR must be an absolute path or the tests will fail
export NEOMUTT_TEST_DIR="$PWD/neomutt-test-files"

(cd neomutt-test-files; ./setup.sh)
```

## Build

Next, build NeoMutt as normal:

```
cd neomutt
./configure [YOUR-OPTIONS]
make

Note: The `--testing` configure option is no longer needed.

```

## Testing

To run the tests use either of:

- `make test`
- `test/neomutt-test`

By calling the test program directly, you can run individual tests.

```sh
test/neomutt-test -l                     # List the test names
test/neomutt-test test_mutt_str_strncmp  # Run a particular test
test/neomutt-test mutt_str               # Run all tests matching this string
test/neomutt-test -v test_url_free       # Run verbosely
```


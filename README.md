# Test Files

[This repo](https://github.com/neomutt/neomutt-test-files) contains test files
for the main NeoMutt source.

The [NeoMutt source code](https://github.com/neomutt/neomutt) comes with a set
of [unit tests](https://en.wikipedia.org/wiki/Unit_testing).

They cover the [Address](https://neomutt.org/code/address.html),
[Core](https://neomutt.org/code/core.html),
[Email](https://neomutt.org/code/email.html)
and [Mutt](https://neomutt.org/code/mutt.html) libraries.

See also: [Test code coverage](https://coveralls.io/github/neomutt/neomutt)

## Setup

```sh
git clone https://github.com/neomutt/neomutt
git clone https://github.com/neomutt/neomutt-test-files

# NEOMUTT_TEST_DIR must be an absolute path or a test will fail
export NEOMUTT_TEST_DIR="$HOME/neomutt-test-files"

(cd neomutt-test-files; ./setup.sh)
```

## Build

Next, add an option to configure, to enable testing:

```
cd neomutt
./configure --testing [YOUR-OTHER-OPTIONS]
make
```

## Testing

To run the tests use either of:

- `make test`
- `test/neomutt-test`

By calling the test program directly, you can run individual tests.

```sh
test/neomutt-test -l                     # List the test names
test/neomutt-test test_mutt_str_strncmp  # Run a particular test
test/neomutt-test mutt_str               # Rul all tests matching this string
test/neomutt-test -v test_url_free       # Run verbosely
```


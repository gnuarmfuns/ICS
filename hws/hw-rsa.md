ICS: Programming Homework: RSA
==============================

[Go up to the ICS HW page](index.html) ([md](index.md))

You will want to see the
[homeworks policies page](../uva/hw-policies.html)
([md](../uva/hw-policies.md)) for formatting and other details.  The
due dates are listed on the [UVa course page](../uva/index.html)
([md](../uva/index.md)).

### Purpose 

This assignment will focus on the implementation of the RSA
algorithm. Specifically, you will have to implement key generation,
encryption and decryption, signing and signature checking, and
cracking of RSA messages.

The intent is to implement this in Java, since the JDK provides the
functionality to handle the necessary math.  You must speak to me
first if you want to use another language!

As Java is meant to be cross-platform, there is no specific reference
platform for this assignment.  We will be using Java 1.8 to compile,
run, and test your program.

### Relevant links

These links are all described below, but are included here, all in one place.

- [RSA.java](rsa/RSA.java) skeleton code, which you ***MUST*** use;
  you can also view an [HTML version](rsa/RSA.java.html)
- Doxygen documentation for the
  [CipherText](rsa/html/classCipherText.html),
  [RSAKey](rsa/html/classRSAKey.html), and
  [RSA](rsa/html/classRSA.html) classes
- [Command line parameter usage](rsa/html/cmdparam.html) -- note that
  the provided RSA.java file calls the correct functions based on the
  parameters passed
- [The encryption lecture](../slides/encryption.html#/rsa), and the
  [Wikipedia article on RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
- [Java SDK documentation](https://docs.oracle.com/javase/8/docs/api/),
  including the
  [java.math.BigInteger](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html)
  and
  [java.security.MessageDigest](https://docs.oracle.com/javase/8/docs/api/java/security/MessageDigest.html)
  classes
- The [test-rsa.sh](rsa/test-rsa.sh)
  ([HTML version](rsa/test-rsa.sh.html)) shell script

### Prerequisites to Review 

You should be familiar with how the RSA algorithm works from the
[the encryption lecture](../slides/encryption.html#/rsa).  More
details are available online (see the
[Wikipedia article on RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))). Keep
in mind, however, that the Wikipedia page uses different variable
names than what the lecture and slide set used. You will also want to
reference the
[Java SDK documentation](https://docs.oracle.com/javase/8/docs/api/),
specifically the
[java.math.BigInteger](https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html)
and
[java.security.MessageDigest](https://docs.oracle.com/javase/8/docs/api/java/security/MessageDigest.html) classes.

### Skeleton Code

To simplify the assignment, and to allow easy interoperability between
your code and our test cases, we have provided a significant amount of
skeleton code in the [RSA.java](rsa/RSA.java) file; you can see an
HTML version of that code [here](rsa/RSA.java.html).  That code is
split into three classes, the first two of which are just to hold data
and have no methods of their own.  Each link in the list below will go
to the Doxygen documentation for that class.

- [CipherText](rsa/html/classCipherText.html): a class to hold the
  cipher text for any RSA encrypted data
- [RSAKey](rsa/html/classRSAKey.html): a class to hold a public or
  private (or both) key
- [RSA](rsa/html/classRSA.html): the main class that implements RSA.
  There are eight methods within that need to be completed for this
  assignment: `convertToASCII()`, `convertFromASCII()`,
  `generateKeys()`, `encrypt()`, `decrypt()`, `crack()`, `sign()`,
  `checkSign()`.

### Assignment Details 

For this assignment, you must implement eight methods in the RSA
algorithm. They are the ones that state "requires completion" in the
comments.  This assignment is to be done in Java, as you will need to
use the BigInteger and MessageDigest classes.

You must start with the [RSA.java](rsa/RSA.java) skeleton code
([HTML version](rsa/RSA.java.html)).  This code, described more
fully below, provides various methods to ensure that the format of the
key files and the encrypted files are consistent, so that we may
easily test your code.  Furthermore, we are going to *EXPLICITLY* call
individual methods from your code, so if they are not named exactly as
they are therein, your code will fail those tests.

***WARNING!!!*** The `convertToASCII()` and `convertFromASCII()`
methods will be used to test your code.  If they don't work properly,
then NONE of your other methods will work.  Our unit tests, which we
use to evaluate your code, will call these to convert back and
forth. So if they arent't working properly, then you will likely end
up with a zero on the assignment.  Thus, please implement them first,
and test them to make sure they work properly.  And you should use
them in your `encrypt()` and `decrypt()` methods, of course.

You may add any other methods or fields that you would like to add.
The following is required for our testing harness to work properly on
your code:

- The `main()` method exactly as provided, as we want to make sure the
  command line parameters are interpreted the way we expect them to be
  interpreted
- The eight methods that you are to implement should not have their
  signatures changed (return type, visibility, static-ness, name, or
  parameter types).  All these methods have `throws Exception` in case
  your implementation decides to throw an exception.
- The two utility classes (`RSAKey` and `CipherText`) should not be
  modified
- The utility methods, which are the six methods that you *don't* have
  to implement, should not be modified.  Those are:
  `writeKeyToFile()`, `readKeyFromFile()`, `readCipherTextFromFile()`,
  `writeCipherTextToFile()`, `getFileContents()`, and `convertHash()`.
- As mentioned above, you may add any other methods or fields that you
  would like to add.

These requirements are meant to allow for easy for interoperability,
and to ensure that your code works with our test cases.

You must implement eight methods within the [RSA.java](rsa/RSA.java)
([HTML version](rsa/RSA.java.html)) file.  Those methods are:
`convertToASCII()`, `convertFromASCII()`, `generateKeys()`,
`encrypt()`, `decrypt()`, `crack()`, `sign()`, `checkSign()`.  Details
for how they should work can be found in the [the encryption
lecture](../slides/encryption.html#/) as well as
[online](http://en.wikipedia.org/wiki/RSA).

The documentation contained in the comments in the skeleton code
details what the methods and classes do (or should do).  That
commenting was run through [Doxygen](http://www.doxygen.nl/), and the
results are: [CipherText](rsa/html/classCipherText.html),
[RSAKey](rsa/html/classRSAKey.html), and
[RSA](rsa/html/classRSA.html).  ***You will want to look at this!***

### Command line parameters 

The `main()` method should not need to be modified for the final
submission (feel free to modify it any way you want to test your
code).  It will call the appropriate methods as indicated by the
command line parameters, which are described
[here](rsa/html/cmdparam.html). In almost all cases, output (progress,
status messages, etc.) should ONLY be printed to the standard output
if the `-verbose` option is set, and should be enough that we can
understand what is happening.  The *only* time output should be
printed to the terminal is when (1) a signature does not match, and
(2) an error condition is encountered (which, in theory, should not
happen with our tests on properly implemented code).

Note that the command-line parameters are parsed __in order__ - this
means that if you call `java RSA -keygen 10 -verbose`, you will not
get any verbosity, as that parameter was specified *after* the
`-keygen` parameter was given.  We provide a `main()` method in the
[RSA.java](rsa/RSA.java) skeleton code, which can handle the parameters
and, again, *should not be modified*.

Note that normal operation (i.e. without the `-verbose` flag) is for
it to print *nothing* - the only exception is the `-checksign` flag.

Again, the command line parameters are listed [here](rsa/html/cmdparam.html).

You may assume (and, in fact, should) that you will only receive one
of `-encrypt`, `-decrypt`, `-sign`, `-checksign`, `-crack`, or
`-keygen`; this specifies what the program is going to do. The program
should not output any messages on normal execution (it should output
error messages, as appropriate -- but we won't be giving any invalid
combination of parameters) other than on `-checksign`. With the
`-showpandq` option, it will of course output *p* and *q*. And with
the `-verbose` option, it can output a lot of informational messages.

Furthermore, you may assume that we will not give you invalid input,
either in the files we provide, or for the command-line parameters.

### Sample test script

A sample usage of the program, in which is Alice and Bob are sending
messages is available.  This code can be found in a shell script named
[test-rsa.sh](rsa/test-rsa.sh) ([HTML version](rsa/test-rsa.sh.html)).
If you are on a UNIX environment, run `chmod 755 test-rsa.sh`, and
then run it via `./test-rsa.sh`.  Note that this is not a complete test
suite!  Just a quick check to see if the basics work.  But if your
program does not work with this, then it's incomplete, and will
receive a low grade.  If you are not on a UNIX system, then you may
have to copy-and-paste those commands into a command terminal.

This file creates two files (message1.txt and message2.txt), and will
overwrite those files if they already exist; those two files are
deleted by the last line in the script.  You are welcome (and
encouraged) to use other, longer, message test files -- might we
suggest some
[great speeches](http://www.historyplace.com/speeches/previous.htm)?
However, make ***SURE*** that the text is all ASCII, since your
program will likely not be able to handle UTF-8 characters -- and when
you cut-and-paste, characters like the dash and quotes often do not
cut-and-paste into their ASCII equivalents. Run `file message1.txt` to
check if it is ASCII or not (not ASCII is typically reported as
'UTF-8').

Assuming you don't have any extraneous output (which you shouldn't),
the only command that should output anything is step 12.  Again, you
can see the test script at [test-rsa.sh](rsa/test-rsa.sh)
([HTML version](rsa/test-rsa.sh.html)).

Note that the last line deletes the intermediate files; during
development, you may want to comment that line out to see those files.

The output should be just:

```
Signatures do not match!
```

While we are not going to try to break your program with strange
combinations of command line parameters (trying to decrypt but not
specifying a key), we would encourage you to put some sanity
error???checking code in your methods for your own sanity while
developing the program.


### Notes

__Determining SHA-256 hashes:__ We are using the SHA-256 hash for this
assignment.  If you want to see if a string has the same SHA-256 as a
file, make sure they are EXACTLY the same.  If the file has a ending
newline (`\n`) character, and the string does not, then the SHA-256
sums will not match!  You can find the SHA-256 hash of a file via the
`sha256sum` command (`CertUtil -hashfile message1.txt SHA256` on Windows):

```
$ sha256sum message1.txt 
bdf712419bb34b8c0f0d08126f191ecab5da9c0dbb4d2711d3c8eed6f5d42f2a  message1.txt
```

If your system does not have sha256sum, you can switch over to MD5
**but only for development**!  To do that, change the value of the
`hashAlgorithm` variable to "MD5".  You can then use the `md5` or
`md5sum` commands similarly to what is shown above for `sha256sum`.
Be sure to change it back to "SHA-256" before submission!

Note that, given an input file, your SHA-256 hash computation should
print out the *exact* same result as the `sha256sum` command on your
favorite Unix system.  But see the warning, above, about making sure
the contents are the exact same.

__Creating the block:__ You will have a series of characters to put
into a block (or, for decryption, to extract out of the block).  There
are a few ways you can do this.  You can convert it to a byte array
(the `String getBytes()` method does this) -- each value in that array
is a single (ASCII-encoded) value.  You can optionally multiply the
current running block by 256, then add the current value to be
appended to the block.  Obviously, your number will need to be in a
`BigInteger`.

__Block size determination:__ To figure out your block size (which
we'll call *b*) -- which is the number of characters you can encode in
one block -- let *x* be the number of bits in *n* (found via the
BigInteger `bitLength()` method).  Divide *x-1* by 8 (the minus one is
important here to prevent rounding issues).  As mentioned below, you
can assume that we will always use keys that support a block size of
at least 2.  This is for *encryption* only.  For decryption, the block
size will be indicated in the ciphertext file which, when read in by
the provided `readCipherTextFromFile()` method, will be in the
`blockLength` field of the returned `CipherText` object.

__Block size minimum:__ Each block will be a whole number of 8-bit
characters, so we will not be splitting characters between blocks.
Thus, if your keys can hold up to 31 bits per block (if 2^^31^^ < *n*
< 2^^32^^), we will only encode 24 bits (3 characters) in that block,
not 31 bits.  That being said, you can assume that all blocks we will
use will allow for at least 2 characters per block.  Note that the
number passed in via `-keygen` is the bit size for *p* and *q*; *n* is
roughly twice that size.

__ASCII:__ All files (messages, keys, ciphertext, what???not) will have
only printable ASCII characters, so you need not worry about binary
files.  But there may be whitespace as well: newlines, tabs,
linefeeds, etc.  Make sure that your code does not have UTF-8
characters in it!  Given a file, you can tell what type of characters
it has via the `file foo.txt` command.

### Submission requirements

You should submit one file: `RSA.java`, which contains all your Java
code.  The compilation command will be `javac *.java`, so your
RSA.java should have only one public class called `RSA`, and not be in
a package.  The submission system will expect to see a `RSA.class`
file after compilation, and will complain if it is not present
(`missing binary executable`, or similar).

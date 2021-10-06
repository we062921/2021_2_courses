#
- [Linux指令](#Linux指令)
- [Python Hash](#Python_Hashlib)


## Linux指令:md5sum, sha1sum

Google Colab實測: !md5sum --help
```
Usage: md5sum [OPTION]... [FILE]...
Print or check MD5 (128-bit) checksums.

With no FILE, or when FILE is -, read standard input.

  -b, --binary         read in binary mode
  -c, --check          read MD5 sums from the FILEs and check them
      --tag            create a BSD-style checksum
  -t, --text           read in text mode (default)

The following five options are useful only when verifying checksums:
      --ignore-missing  don't fail or report status for missing files
      --quiet          don't print OK for each successfully verified file
      --status         don't output anything, status code shows success
      --strict         exit non-zero for improperly formatted checksum lines
  -w, --warn           warn about improperly formatted checksum lines

      --help     display this help and exit
      --version  output version information and exit

The sums are computed as described in RFC 1321.  When checking, the input
should be a former output of this program.  The default mode is to print a
line with checksum, a space, a character indicating input mode ('*' for binary,
' ' for text or where binary is insignificant), and name for each FILE.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Full documentation at: <http://www.gnu.org/software/coreutils/md5sum>
or available locally via: info '(coreutils) md5sum invocation'
```

```
Usage: sha1sum [OPTION]... [FILE]...
Print or check SHA1 (160-bit) checksums.

With no FILE, or when FILE is -, read standard input.

  -b, --binary         read in binary mode
  -c, --check          read SHA1 sums from the FILEs and check them
      --tag            create a BSD-style checksum
  -t, --text           read in text mode (default)

The following five options are useful only when verifying checksums:
      --ignore-missing  don't fail or report status for missing files
      --quiet          don't print OK for each successfully verified file
      --status         don't output anything, status code shows success
      --strict         exit non-zero for improperly formatted checksum lines
  -w, --warn           warn about improperly formatted checksum lines

      --help     display this help and exit
      --version  output version information and exit

The sums are computed as described in FIPS-180-1.  When checking, the input
should be a former output of this program.  The default mode is to print a
line with checksum, a space, a character indicating input mode ('*' for binary,
' ' for text or where binary is insignificant), and name for each FILE.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Full documentation at: <http://www.gnu.org/software/coreutils/sha1sum>
or available locally via: info '(coreutils) sha1sum invocation'
```
```
!echo abc > test.txt
!echo Abc > test2.txt
```
```
!md5sum test.txt  ==> 0bee89b07a248e27c83fc3d5951213c1  test.txt  ==>32*4 bits =128 bits
!md5sum test2.txt ==> 879435373481c222ca1e3346b3b4c4b1  test2.txt
```
```
!sha1sum test.txt ==> 03cfd743661f07975fa2f1220c5194cbaff48451  test.txt ==>40*4 bits =160 bits
!sha1sum test2.txt ==> b686597546683b17bdd1179f339fa32e1b4368c9  test2.txt
```


## Python_Hashlib
- [Python 計算 MD5 與 SHA 雜湊教學與範例](https://blog.gtwang.org/programming/python-md5-sha-hash-functions-tutorial-examples/)
- [python中hashlib模組詳解](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/615922/)

- hashlib主要提供字元加密功能，將md5和sha模組整合到了一起，支援md5,sha1, sha224, sha256, sha384, sha512等演算法

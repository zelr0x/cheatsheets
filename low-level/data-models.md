# Relevant 
## Data models
\*nix and Windows only
<table>
  <tr>
    <th></th>
    <th>char</th>
    <th>short</th>
    <th>int</th>
    <th>long</th>
    <th>long logn</th>
    <th>pointer</th>
    <th>OS</th>
  </tr>
  <tr>
    <td>ILP32</td>
    <td rowspan="3" align="center">8</td>
    <td rowspan="3" align="center">16</td>
    <td rowspan="3" align="center">32</td>
    <td rowspan="2" align="center">32</td>
    <td rowspan="3" align="center">64</td>
    <td align="center">32</td>
    <td>*unix, Windows</td>
  </tr>
  <tr>
    <td>LLP64</td>
    <td rowspan="2" align="center">64</td>
    <td>Windows</td>    
  </tr>
  <tr>
    <td>LP64</td>
    <td align="center">64</td>
    <td>*nix</td>    
  </tr>
</table>

## Integer limits: \<limits\.h\> \(C\), \<climits\> (C++)
Type | Size (b) | Size (10) | MIN (10) | MAX (10) | MAX (16)
:---: | :---: | ---: | ---: | ---: | ---:
signed char | 8 | 256 | `SCHAR_MIN`<br />-128 | `SCHAR_MAX`<br />127 | 0x7f
unsigned char | 8 | 256 | <br />0 | `UCHAR_MAX`<br />255 | 0xff
char | 8 | 256 | `CHAR_MIN`<br />-128<br />0 (MSVC: `/J`<br />GCC/Clang: `-funsigned-char`) | `CHAR_MAX`<br />127<br />255 (flag) | 0x7f<br />0xff (flag)
short | 16 | 65536 | `SHRT_MIN`<br />-32768 | `SHRT_MAX`<br />32767 |0x7fff
unsigned short | 16 | 65536 | <br />0 | `USHRT_MAX`<br />65535 | 0xffff
int | 32 | 4294967296 | `INT_MIN`<br />-2147483648 | `INT_MAX`<br />2147483647 | 0x7fffffff
unsigned int | 32 | 4294967296 | <br />0 | `UINT_MAX`<br />4294967295 | 0xffffffff
long (ILP32, LLP64) | 32 | 4294967296 | `LONG_MIN`<br />-2147483648 | `LONG_MAX`<br />2147483647 | 0x7fffffff
long (LP64) | 64 | 18446744073709551616 | `LONG_MIN`<br />-9223372036854775808 | `LONG_MAX`<br />9223372036854775807 | 0x7fffffffffffffff
ulong (ILP32, LLP64) | 32 | 4294967296 | <br />0 | `ULONG_MAX`<br />4294967295 | 0xffffffff
ulong (LP64) | 64 | 18446744073709551616 | <br />0 | `ULONG_MAX`<br />18446744073709551615 | 0xffffffffffffffff
long long | 64 | 18446744073709551616 | `LLONG_MIN`<br />-9223372036854775808 | `LLONG_MAX`<br />9223372036854775807 | 0x7fffffffffffffff
unsigned long long | 64 | 18446744073709551616 | <br />0 | `ULLONG_MAX`<br />18446744073709551615 | 0xffffffffffffffff

# All data models
<table>
  <tr>
    <th></th>
    <th>char</th>
    <th>short</th>
    <th>int</th>
    <th>long</th>
    <th>long long</th>
    <th>pointer</th>
    <th>OS</th>
  </tr>
  <tr>
    <td>IP16L32 (near)</td>
    <td rowspan="8" align="center">8</td>
    <td rowspan="7" align="center">16</td>
    <td rowspan="3" align="center">16</td>
    <td rowspan="5" align="center">32</td>
    <td rowspan="4" align="center">&#x2717;</td>
    <td align="center">16</td>
    <td rowspan="2" align="center">...</td>
  </tr>
  <tr>
    <td>I16LP32 (far)</td>
    <td rowspan="3" align="center">32</td>
  </tr>
  <tr>
    <td>LP32</td>
    <td>Old Windows (3.1), old *nix</td>
  </tr>
  <tr>
    <td><b>ILP32</b></td>
    <td rowspan="3" align="center">32</td>
    <td><b>*nix, Windows</b></td>
  </tr>
  <tr>
    <td><b>LLP64</b></td>
    <td colspan="2" rowspan="4" align="center">64</td>
    <td><b>Windows (MSVC, MinGW)</b></td>
  </tr>
  <tr>
    <td><b>LP64</b></td>
    <td rowspan="3" align="center">64</td>   
    <td><b>*nix, Windows (cygwin)</b></td>
  </tr>
  <tr>
    <td>ILP64</td>
    <td rowspan="2" align="center">64</td>
    <td>HAL port of Solaris to SPARC64</td>
  </tr>
  <tr>
    <td>SILP64</td>
    <td align="center">64</td>
    <td>Classic UNICOS</td>
  </tr>
</table>

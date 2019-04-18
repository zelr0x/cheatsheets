# Short version

# Full version

## Data model / OS
<table>
  <tr>
    <th>Model</th>
    <th>Bitness</th>
    <th>OS</th>
  </tr>
  <tr>
    <td><b>LP64</b></td>
    <td rowspan="4" align="center">64</td>
    <td>Most of *nix, Windows (cygwin)</td>
  </tr>
  <tr>
    <td><b>LLP64</b></td>
    <td>Windows (MSVC, MinGW)</td>
  </tr>
  <tr>
    <td>ILP64</td>
    <td>HAL port of Solaris to SPARC64</td>
  </tr>
  <tr>
    <td>SILP64</td>
    <td>Classic UNICOS</td>
  </tr>
  <tr>
    <td><b>ILP32</b></td>
    <td rowspan="2" align="center">32</td>
    <td>Windows, *nix</td>
  </tr>
  <tr>
    <td>LP32</td>
    <td>Old Windows (3.1), *nix</td>
  <tr>
    <td>I16LP32 (far)</td>
    <td rowspan="2" align="center">16</td>
    <td rowspan="2"></td>
  </tr>
  <tr>
    <td>IP16L32 (near)</td>
  </tr>
</table>

## Type size / Data model
<table>
  <tr>
    <th></th>
    <th>char</th>
    <th>short</th>
    <th>int</th>
    <th>long</th>
    <th>long long</th>
    <th>pointer</th>
  </tr>
  <tr>
    <td>IP16L32 (near)</td>
    <td rowspan="8" align="center">8</td>
    <td rowspan="7" align="center">16</td>
    <td rowspan="3" align="center">16</td>
    <td rowspan="5" align="center">32</td>
    <td rowspan="4" align="center"></td>
    <td align="center">16</td>
  </tr>
  <tr>
    <td>I16LP32 (far)</td>
    <td rowspan="3" align="center">32</td>
  </tr>
  <tr>
    <td>LP32</td>
  </tr>
  <tr>
    <td>ILP32</td>
    <td rowspan="3" align="center">32</td>
  </tr>
  <tr>
    <td>LLP64</td>
    <td colspan="2" align="center">64</td>
  </tr>
  <tr>
    <td>LP64</td>
    <td colspan="3" align="center">64</td>
  </tr>
  <tr>
    <td>ILP64</td>
    <td colspan="4" align="center">64</td>
  </tr>
  <tr>
    <td>SILP64</td>
    <td colspan="5" align="center">64</td>
  </tr>
</table>

## Size limits
Size (bits) | Size (decimals) | Smallest | Largest
---: | ---: | ---: | ---:

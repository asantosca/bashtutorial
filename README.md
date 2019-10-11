

## Parameters

Positional: $1 $2 ... $8 $9 ${10} <-- after 9 needs ${}

Special parameters:

$*
$@
$#
$-
$$
$0
$!
$?
$_

Parameter Expansion

In these examples, "default" is the value, not another variable, whereas "param" is the name of a variable.

>param="val"; echo ${param-default}
val
>unset param; echo ${param-default}
default
>param=""; echo ${param-default}
    <-- empty

Parameter Indirection

>param="parade"; parade="what?"; echo ${!param}
what?

>param="parade"; parade="what?"; echo ${!pa@}
parade param

>name=(gnu not unix); echo ${!name[*]}
0 1 2

name=(gnu not unix); echo ${!name[@]}
0 1 2


>param="parades are long"; echo ${#param}
16

Parameter Substitution

>param="racecar"; echo ${param/c?/T}
raTcar

>param="racecar"; echo ${param/c/T}
raTecar

>param="racecar"; echo ${param//c/T}
raTeTar

>param="racecar"; echo ${param/#r/T}
Tacecar

>param="racecar"; echo ${param/%r/T}
racecaT

https://wiki.bash-hackers.org/doku.php


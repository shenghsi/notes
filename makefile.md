### [Setting Variables](https://www.gnu.org/software/make/manual/html_node/Setting.html#Setting)
There are two ways that a variable in GNU make can have a value; we call them the two flavors of variables. The two flavors are distinguished in how they are defined and in what they do when expanded.
```bash
=       #recursively expanded variable expande when they are used
:=      #Simply expanded variables     expand when they are defined rather than when they are used.
```
The first flavor of variable is a **recursively expanded variable**. Variables of this sort are defined by lines using ‘=’ (see Setting Variables) or by the define directive (see Defining Multi-Line Variables). The value you specify is installed verbatim; if it contains references to other variables, these references are expanded whenever this variable is substituted (in the course of expanding some other string). When this happens, it is called recursive expansion.

To avoid all the problems and inconveniences of recursively expanded variables, there is another flavor: simply expanded variables. **Simply expanded variables** are defined by lines using ‘:=’ or ‘::=’ (see Setting Variables). Both forms are equivalent in GNU make; however only the ‘::=’ form is described by the POSIX standard


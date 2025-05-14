-----

### Welcome to my profile:

-----

Hello there. I'm Jordan.

Is this my job? No. Just a hobby at the moment. Maybe it will be someday. Or, at least I hope it will be.

I do have: https://www.patreon.com/jordan4ibanez

-----

### Discord:

-----

My discord is here: https://discord.gg/D95q7BHUE4

-----

[Click here for the Fortran section of my profile.](https://github.com/jordan4ibanez/jordan4ibanez/blob/main/fortran.md)

-----

# D Cheat Sheet

-----


### Things that are evaluated at compile time:

#### From: schveiguy

-----

The following expressions are evaluated at compile time:
Initializers for static, module-level, or __gshared variables

1. value of an enum.
2. A template value argument.
3. default initializers for member fields.
4. And that's it. Everything else is runtime.

-----

### Initialize an array with a value

#### From: Me :D

-----

```d
const x = (new int[30_000])[] = 1;
```

-----

### C++ style explicit operator bool for type

#### From: Kapendev

-----

```d
bool opCast(T: bool)() const {
    return isSome;
}
```

-----

### Unimplemented Operator

#### From: ShapeshiftingLizard

-----

```d
bool opCast(T)() const {
    static if (is(T == bool)) {
        return count != -1;
    } else static assert(0, "Not implemented.");
}
```

-----

### Value template class/struct

#### From: Me :D

-----

```d
class cool(int MY_COOL_VALUE) {
    immutable int aCoolValue = MY_COOL_VALUE;
}

void main() {
    auto i = new cool!23();
    writeln(i.aCoolValue);
}
```

-----

### Run tests in release mode

#### From: 0xEAB
-----

```
DFLAGS="-release -unittest" dub test
```

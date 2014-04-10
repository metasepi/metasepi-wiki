# An application using X reboots system

```
+---------------+
| Application A |
+---------------+
        |
        v
+---------------+
| Application B |
+---------------+
        |
        v
+---------------+
|   Library C   |
+---------------+
```

## What?

1. Boot
2. Run startx
3. Run the Application A
4. X and system reboot

## Why?

Library C returns NULL when error occurs.
The Application B code using C++ string. But the string throws exception when input NULL.

```
terminate called after throwing an instance of 'std::logic_error'
  what():  basic_string::_S_construct null not valid
Aborted
```

It returns parent Application A and reboot.
But developer can't understand Application B behavior.

## Prevention

* Do not return NULL on binary interface
* Decide unique location of log (X, application, library)
* Library C's API is bad?

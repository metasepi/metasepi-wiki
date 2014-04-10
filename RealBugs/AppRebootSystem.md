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
3. Run the application
4. X and system reboot

## Why?

A library return NULL when error occur.
The application code using C++ string. But the string throws exception when input NULL.

```
terminate called after throwing an instance of 'std::logic_error'
  what():  basic_string::_S_construct null not valid
Aborted
```

It returns parent application and reboot.

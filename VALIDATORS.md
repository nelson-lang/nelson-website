## Validators functions

Property Validation Functions:
These functions support common use patterns for validation and provide descriptive error messages.

```matlab
function r = myFunction(arg1, arg2)
    mustBeFloat(arg1, 1)
    mustBeFloat(arg2, 2)
    mustBeScalarOrEmpty(arg1, 1)
    mustBeScalarOrEmpty(arg2, 2)
    r = arg1 + arg2
end
```

```matlab
r = myFunction('a', 2)
r = myFunction([1 2], 2)
r = myFunction(1, [3 2])
```

See help about [validations function](https://nelson-lang.github.io/nelson-website/help/en_US/chapter_validators.html)

[Previous page](FEATURES.md)

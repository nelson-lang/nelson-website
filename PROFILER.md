## [Profiling and Coverage Tools](PROFILER.md)

Nelson has a built-in profiler that is very useful to profile your code and find out what script or function is taking the most time.

Example:

```
profile('on')
run('test_profile.nls')
profile('off')
profsave()
```

It generates a html report available [here](https://nelson-numerical-software.github.io/nelson-website/profile_result/index.html)

[Previous page](FEATURES.md)

```@meta
CurrentModule = QuPhys
```

```@eval
using PkgBenchmark
using Markdown

nthreads = Sys.CPU_THREADS

config1 = BenchmarkConfig(env = Dict("JULIA_NUM_THREADS" => nthreads))

result1 = benchmarkpkg("QuPhys", config1)

mdtext = sprint(io -> PkgBenchmark.export_markdown(io, result1))
Markdown.parse(mdtext)
```

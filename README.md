experiment.py
-------------
I use this class to store the results of simulation experiments. To facilitate reproducibility, it
automatically adds a bunch of other information that might be of interest later, such as the time it
took to run the experiment, the current git commit hash, and information about the environment the
experiment was run in.

```python
experiment = Experiment()

# run the experiment

experiment['foo'] = foo
experiment['bar'] = bar
experiment.save('results/foobar.xpck')
```

Calling `save` will store `experiment` using [pickle](https://docs.python.org/2/library/pickle.html).
The script can also help to inspect results via the command line. Use

```
./experiment.py results/foobar.xpck
```

to get a summary of the experiment and

```
./experiment.py results/foobar.xpck foo bar
```

to output the variables `foo` and `bar`.

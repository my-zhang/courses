
Mengyu Zhang
mengyuzhang@uchicago.edu

HW 04
=====

Compile
-------

```
$ make 
```

Outputs

`p1`: serial program; 
`p2a`:parallel program with strategy (a); 
`p2b`:parallel program with strategy (b); 

Run
---

Excutables will ouput the grid to stdout. 

```
$ ./p2a > grid.out
$ ./p2b > grid.out
```

Peformance
----------

(a) The first strategy is statically assigning rows of points to workers, while the later is dynamically dispathing; 

(b) Threadprivate copies of the window, accumulated into a single copy at the end of the simulation. 

With parameters, n = 250, L = (4, 4, -1), Wy = 10, Wmax = 10, C = (0, 12, 0), R = 6, nrays = 100,000 the we have, 

a) 1210000 clocks (1.210000 seconds)

b) 1220000 clocks (1.220000 seconds) 

almost the same. 

If run with n = 2500, nrays = 1,000,000

a) 14320000 clocks (14.320000 seconds)

b) 13990000 clocks (13.990000 seconds)

We can see that, even the memory space overhead is increasing significantly when grid becoming 2500 * 2500, (b) still has neary the same performace with (a). 

Figure
------

The figures `ray.jpg` and `ray.fig` are generated by Matlab, which firstly load `output.txt`, and then run `imagesc`. 

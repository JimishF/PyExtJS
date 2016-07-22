PyExtJS
=======
<sup>(Python Extension Packages in Javascript)</sup>  

### Contents  

- <a href="#what-is-pyextjs">What is PyExtJs?</a>
- <a href="#installation">Installation</a>
- <a href="#sourcecode">Latest source code</a>
- <a href="#bugs">Bug reports</a>
- <a href="#gettingstarted">Getting Started</a>
  * <a href="#numpy">numpy</a>
    * <a href="#linspace">linspace</a>
    * <a href="#exp">exp</a>
    * <a href="#arange">arange</a>
    * <a href="#zeros">zeros</a>
    * <a href="#polyfit">polyfit</a>
  * <a href="#scipy">scipy</a>
    * <a href="#interpolate">interpolate</a>
    * <a href="#linregress">linregress</a>

## <a id="what-is-pyextjs">What is PyExtJs?</a>

Python Extension Packages in Javascript is open-source implementation of some common libraries used 
in the scientific python programming.  
The main goal of this project is to improve migration of 
python language to javascript.

## <a id="installation">Installation</a>

Just include the following libraries in your html.

    <script type="text/javascript" src="ss.js"></script>
    <script type="text/javascript" src="Numpy.js"></script>
    <script type="text/javascript" src="PolySolve.js"></script>
    <script type="text/javascript" src="Scipy.js"></script>
<br>

## <a id="sourcecode">Latest source code</a>  

<br>
The latest development version of Scipy's sources are always available at:

> [https://github.com/fernandezajp/PyExtJs](https://github.com/fernandezajp/PyExtJs)

<br>

## <a id="bugs">Bug reports</a>  
<br>
To search for bugs or report them, please use the Scipy Bug Tracker at:

> [https://github.com/fernandezajp/PyExtJs/issues](https://github.com/fernandezajp/PyExtJs/issues)

## <a id="gettingstarted">Getting Started</a>

### <a id="numpy">numpy</a>

#### *<a id="linspace">Using linspace</a>*

Python

    >>> import numpy
    >>> numpy.linspace(2.0, 3.0, 5)
        array([ 2.  ,  2.25,  2.5 ,  2.75,  3.  ])
  
<br>
Javascript with PyExtJS

    > numpy.linspace(2.0, 3.0, 5);
      [2, 2.25, 2.5, 2.75, 3]

<br>

#### *<a id="exp">Using exp</a>*

Python

    >>> import numpy
    >>> numpy.exp(2.4)
        11.023176380641601
    >>> numpy.exp([2.4, 3.1])
        array([ 11.02317638,  22.19795128])
  
<br>
Javascript with PyExtJS

    > numpy.exp(2.4);
      11.0231763806416
    > numpy.exp([2.4, 3.2])
      [11.0231763806416, 24.53253019710935]

<br>

#### *<a id="arange">Using arange</a>*

Python

    >>> import numpy
    >>> numpy.arange(3)
        array([0, 1, 2])
    >>> numpy.arange(3,7)
        array([3, 4, 5, 6])
    >>> numpy.arange(3,7,2)
        array([3, 5])
  
<br>
Javascript with PyExtJS

    > numpy.arange(3);
      [0, 1, 2]
    > numpy.arange(3,7)
      [3, 4, 5, 6]
    > numpy.arange(3,7,2)
      [3, 5]

<br>

#### *<a id="zeros">Using zeros</a>*

Python

    >>> import numpy
    >>> numpy.zeros(5)
        array([ 0.,  0.,  0.,  0.,  0.])
    >>> numpy.zeros((3, 2))
        array([[ 0.,  0.],
              [ 0.,  0.],
              [ 0.,  0.]])
  
<br>
Javascript with PyExtJS

    > numpy.zeros(5);
      [0, 0, 0, 0, 0]
    > numpy.zeros(3, 2);
      [[0, 0],[0, 0],[0, 0]]

<br>

#### *<a id="polyfit">Using polyfit</a>*

Python

    >>> import numpy
    >>> x = numpy.array([0.0, 1.0, 2.0, 3.0,  4.0,  5.0])
    >>> y = numpy.array([0.0, 0.8, 0.9, 0.1, -0.8, -1.0])
    >>> numpy.polyfit(x, y, 3)
        array([ 0.08703704, -0.81349206,  1.69312169, -0.03968254])
  
<br>
Javascript with PyExtJS

    > x = [0.0, 1.0, 2.0, 3.0,  4.0,  5.0];
      [0, 1, 2, 3, 4, 5]
    > y = [0.0, 0.8, 0.9, 0.1, -0.8, -1.0];
      [0, 0.8, 0.9, 0.1, -0.8, -1]
    > numpy.polyfit(x, y, 3);
      [0.0870370370370341, -0.8134920634920405, 1.6931216931216477, -0.039682539682528106]
    
<br>

### *<a id="scipy">scipy</a>*

#### *<a id="interpolate">Using interpolate</a>*

Python

    >>> import numpy
    >>> from scipy import interpolate
    >>> x = numpy.arange(0, 10)
        array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
    >>> y = numpy.exp(-x/3.0)
        array([ 1.        ,  0.71653131,  0.51341712,  0.36787944,  0.26359714,
        0.1888756 ,  0.13533528,  0.09697197,  0.06948345,  0.04978707])
    >>> f = interpolate.interp1d(x, y)
    >>> f(2.4)
        array(0.4552020478881322)  
<br>
Javascript with PyExtJS

    > x = numpy.arange(0, 10);
      [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    > tmp = x.map(function(v) {
        return -v/3.0;
      });
      [-0, -0.3333333333333333, -0.6666666666666666, -1, -1.3333333333333333, -1.6666666666666667, -2, -2.3333333333333335, -2.6666666666666665, -3]
    > y = numpy.exp(tmp);
      [1, 0.7165313105737892, 0.513417119032592, 0.3678794411714424, 0.26359713811572677, 0.1888756028375618, 0.1353352832366127, 0.09697196786440504, 0.06948345122280153, 0.04978706836786395]
    > var interpolation = new interpolate();
      undefined
    > interpolation.interp1d(x, y);
      undefined
    > interpolation.eval(2.4);
      0.4552020478881322
    > interpolation.eval([3.1, 2.4]);
      [0.35745121086587084, 0.4552020478881322]
<br>

#### *<a id="linregress">Using linregress</a>*

Python

    >>> from scipy import stats
    >>> x = [0.6,0.1,0.7,0.7,0.3,0.6,0.1,0.6,0.7,0.8]
    >>> y = [0.8,0.8,0.2,0.1,0.8,0.3,0.5,0.9,0.1,0.2]
    >>> slope, intercept, r_value, p_value, std_err = stats.linregress(x,y)
    >>> slope
        -0.72818791946308714
    >>> intercept
        0.84865771812080526  
<br>
Javascript with PyExtJS

    > var Stats = new stats();
      undefined
    > x = [ 0.6, 0.1, 0.7, 0.7, 0.3, 0.6, 0.1, 0.6, 0.7, 0.8 ];
      [0.6, 0.1, 0.7, 0.7, 0.3, 0.6, 0.1, 0.6, 0.7, 0.8]
    > y = [ 0.8, 0.8, 0.2, 0.1, 0.8, 0.3, 0.5, 0.9, 0.1, 0.2 ];
      [0.8, 0.8, 0.2, 0.1, 0.8, 0.3, 0.5, 0.9, 0.1, 0.2]
    > Stats.linregress(x, y);
      undefined
    > Stats.get_slope();
      -0.7281879194630861
    > Stats.get_intercept();
      0.8486577181208048
    
<br>

<a href="#performance">Performance</a>
--------------------------------------

This is very important, the test was executed in a MacBookPro i5

The python Code:

    import time
    import numpy

    def test():
        x = numpy.array([0.0, 1.0, 2.0, 3.0,  4.0,  5.0])
        y = numpy.array([0.0, 0.8, 0.9, 0.1, -0.8, -1.0])

        start = time.time()
        for num in range(1,10000):
            numpy.polyfit(x, y, 3)
        end = time.time()

        microsecs = end - start
        print microsecs * 1000

    test()
    
<br>
The Javascript Code:

    function test() {
        x = [0.0, 1.0, 2.0, 3.0,  4.0,  5.0];
        y = [0.0, 0.8, 0.9, 0.1, -0.8, -1.0];

        var start = +new Date();
        for (var i=0;i<10000;i++)
            numpy.polyfit(x, y, 3)
        var end =  +new Date();
        var diff = end - start;
        alert(diff);
    }
    
    test();
    
<br>

Python: 1604 milliseconds  
Javascript: 14 milliseconds

Javascript! Very fast!!!
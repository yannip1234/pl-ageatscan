pl-ageatscan
==============


Abstract
--------

A ChRIS app to take two CSV columns containing dates and finds the difference between them. Appends a new column containing the difference in days or months.

Description
-----------

``ageatscan`` takes two CSV columns containing dates and finds the difference between them. Appends a new column containing the difference in days or months.


Usage
-----

```

        python ageatscan.py
            [-h] [--help]
            [-p <PREFIX>]
            <inputDir>
            <outputDir>
            [-u <days, mths>] [--unit <days, mths>]
	    [-v] [-verbose]
	    [-s <STRING>][--subtrahend <STRING>]
	    [-m <STRING>][--minuend <STRING>]
	    [-r <STRING>][--result <STRING>]
```

## Arguments


## Code
```

        [-h] [--help]
        If specified, show help message and exit.

        [-v] [--verbose]
	Displays the output CSV in stdout

        <inputDir>
        Input directory.

        [-p <PREFIX>]
	The type of file. Usually '*.csv'. Defaults to '*.csv' 
  
        [-u <days, mths>] [--unit <days, mths>]
	The unit for the results column. Choose days or (months, mth, m)

        [-s <STRING>][--subtrahend <STRING>]
	Column name of the subtrahend. Defaults to 'DateOfBirth'

        [-m <STRING>][--minuend <STRING>]
	Column name of the minuend. Defaults to 'DateOfScan'

        [-r <STRING>][--result <STRING>]
	Output header name for results column. Defaults to 'AgeAtScan'
```
## Getting inline help is:

```

    docker run --rm fnndsc/pl-simpledsapp simpledsapp --man
```
## Run


You need you need to specify input and output directories using the `-v` flag to `docker run`.

```

    docker run --rm -u $(id -u)                             \
        -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing      \
        fnndsc/pl-simpledsapp simpledsapp                        \
        /incoming /outgoing
```


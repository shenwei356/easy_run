# easy_run

Run command with default options in configuration file.

Special inner variables ($ncpus) are supported, and default option flags
could be ignored by giving value 'FALSE'.

Note that, only single-value options are supported.

## Installation

easy_run is a single script written in Python using standard library. 
It's Python 2/3 compatible, version 2.7 or later is needed.

You can simply save the [script](https://raw.githubusercontent.com/shenwei356/easy_run/master/easy_run)
to directory included in environment PATH, e.g ```/usr/local/bin```.

Or
    
    git clone https://github.com/shenwei356/easy_run.git
    copy easy_run/eary_run /usr/local/bin

## Usage

    Usage: easy_run [options] command [options of command]

	Run command with default options in configuration file.

	Options:

		-s, --stdin     Pass STDIN to command
		-v, --verbose   Verbosely print information
		-h, --help      Print this help message

## Example

For a configuration file:  ~/.easy_run/blastn.conf

	#!blastn

	-outfmt 11
	-show_gis
	-num_threads $ncpus

	
1) Running ```easy_run -v blastn -query seq.fa -db nr```
  is equal to  ```blastn -query seq.fa -db nr -outfmt 11 -show_gis -num_threads 4```

2) Running  ```easy_run -v blastn -query seq.fa -db nr -show_gis FALSE  -num_threads 8```
  is equal to  ``` blastn -query seq.fa -db nr -num_threads 8 -outfmt 11```

## Copyright

Copyright (c) 2015, Wei Shen (shenwei356@gmail.com)

[MIT License](https://github.com/shenwei356/easy_run/blob/master/LICENSE)
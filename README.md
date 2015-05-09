# easy_run

Run command with default options in configuration file.

Special inner variable ($ncpus for now) is supported, and default option flag
could be ignored by giving value 'FALSE'.

Note that, only single-value option is supported.

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

	
1) Running : ```easy_run -v blastn -query seq.fa -db nr```
  is equal to: ```blastn -query seq.fa -db nr -show_gis -outfmt 11 -num_threads 4```

2) Running : ```easy_run -v blastn -query seq.fa -db nr -show_gis FALSE  -num_threads 8```
  is equal to: ``` blastn -query seq.fa -db nr -num_threads 8 -outfmt 11```

## Copyright

Copyright (c) 2015, Wei Shen (shenwei356@gmail.com)

[MIT License](https://github.com/shenwei356/easy_run/blob/master/LICENSE)
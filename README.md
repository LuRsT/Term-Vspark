[![Build Status](https://travis-ci.org/kablamo/Term-Vspark.svg?branch=master)](https://travis-ci.org/kablamo/Term-Vspark) [![Coverage Status](https://img.shields.io/coveralls/kablamo/Term-Vspark/master.svg)](https://coveralls.io/r/kablamo/Term-Vspark?branch=master)
# NAME

Term::Vspark - Displays a graph in the terminal

# SYNOPSIS

    use Term::Vspark qw/show_graph/;
    binmode STDOUT, ':encoding(UTF-8)';
    print show_graph(
        values  => [0,1,2,3,4,5],
        labels  => [0,1,2,3,4,5], # optional
        max     => 7,             # optional
        columns => 80,            # optional
    );

    # The output looks like this:
    # 0 ▏
    # 1 ██████████▉
    # 2 █████████████████████▊
    # 3 ████████████████████████████████▋
    # 4 ███████████████████████████████████████████▌
    # 5 ██████████████████████████████████████████████████████▍

# DESCRIPTION

This module displays beautiful graphs in the terminal.  It is a companion to
Term::Spark but instead of displaying normal sparklines it displays "vertical"
sparklines.

Note that because the graph is built from utf8 characters, users must setup
UTF-8 encoding for STDOUT if they wish to print the output.

# METHODS

## show\_graph( values => \\@values, labels => \\@labels, max => $max, columns => $columns )

show\_graph returns a string.

The 'values' parameter should be an ArrayRef of numbers.   This is required.

The 'labels' parameter should be an ArrayRef of strings.  This is optional.
Each label will be used with the corresponding value.

The 'max' parameter is the maximum value of the graph.  Without this parameter
you cannot compare graphs because the scaling will change depending on the
data.  This parameter is optional.

The 'columns' parameter is the maximum width of the graph.

# AUTHOR

Gil Gonçalves <lurst@cpan.org>

# SEE ALSO

[Term::Spark](https://metacpan.org/pod/Term::Spark)

Original repo: [https://github.com/LuRsT/vspark](https://github.com/LuRsT/vspark)

Perl Ferment
------------

Yet Another tool to manage perl installs in your home directory.

Perl Ferment builds perls into $HOME/perlferment/perls/ and symlinks them to $HOME/local_perl

One of big advantage of Perl Ferment is that it lets you have multiple Perls with different CPAN libraries without the need to use local_lib.

Tools
-----

Perl Ferment comes with 3 tools:


buildperl
---------

Build a specific version of perl $HOME/perlferment/perls/

Usage: buildperl -version perl-5.12.1 -target clean_5_12_1

The specified version of perl must be present in $HOME/perlferment/build/ - In the future, Perl Ferment will fetch from perl.org


listperls
---------

Usage: listperls

Shows the current perl installs in $HOME/perlferment/build/ and which one is in use at the moment.


switchperl
----------

Usage: switchperl target_name

Switches the symlink ($HOME/local_perl) to point at the specified version in $HOME/perlferment/perls/


Installing
----------

To enable Perl Ferment, add the following to your .bashrc:

    # Perlferment
    export PATH=/home/philc/local_perl/bin:/home/philc/perlferment/bin:${PATH}


-----

Tutorial

Add Perlferment to your path as demonstrated above

cd
mkdir perlferment
cd perlferment
git clone git@github.com:GeneticGenesis/Perl-Ferment.git .
cd build
wget http://www.cpan.org/src/perl-5.10.1.tar.gz
tar -xvzf perl-5.10.1.tar.gz
cd
buildperl -version perl-5.10.1 -target perl_nickname
switchperl perl_nickname
---
layout: post
title:  "Perl XML::Generator notes"
date:   2010-01-01
categories: development
---

```
my $xml = XML::Generator->new( pretty => 2 );
my @people = (
    $xml->Name("Rob"),
    $xml->Name("Sally")
);
print $xml->People(@people) . "\n";
```

```
[user@server ~]$ perl -e 'use XML::Generator; my $xml = XML::Generator->new( pretty => 2 ); my @people = ( $xml->Name("Rob"), $xml->Name("Sally") ); print $xml->People(@people) . "\n";'
<People>
  <Name>Rob</Name>
  <Name>Sally</Name>
</People>
```

```
use XML::Generator;
my $xml = XML::Generator->new( pretty => 2 );
my @people = (
    $xml->Person(
        $xml->Name("Rob"),
        $xml->Age(25)
    ),
    $xml->Person(
        $xml->Name("Sally"),
        $xml->Age(20)
    )
);
print $xml->People(@people) . "\n";
```

```
[user@server ~]$ perl -e 'use XML::Generator; my $xml = XML::Generator->new( pretty => 2 ); my @people = ( $xml->Person( $xml->Name("Rob"), $xml->Age(25) ), $xml->Person( $xml->Name("Sally"), $xml->Age(20) ) ); print $xml->People(@people) . "\n";'
<People>
  <Person>
    <Name>Rob</Name>
    <Age>25</Age>
  </Person>
  <Person>
    <Name>Sally</Name>
    <Age>20</Age>
  </Person>
</People>
```
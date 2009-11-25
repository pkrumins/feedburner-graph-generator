Feedburner graphs suck. This is a program that generates the nice graphs
Feedburner used to have back in 2008.

It was written by Peteris Krumins (peter@catonmat.net).
His blog is at http://www.catonmat.net  --  good coders code, great reuse.

The code is licensed under the MIT license.

The code was written as a part of article "Feedburner Graphs Suck, or How
to Generate Nice Graphs for Feedburner" on my website. The whole article
can be read at:

    http://www.catonmat.net/blog/generating-feedburner-graphs/


------------------------------------------------------------------------------

Table of contents:
    [1] The problem with Feedburner graphs.
    [2] My solution: generate_feedburner_graph.pl


[1]-The-problem-with-Feedburner-graphs----------------------------------------

Feedburner used to have a really nice RSS subscriber growth graph. I loved it.
But then one day they were acquired by Google and they changed their nice chart
to an interactive flash thing that was slow and looked just awful.

See how it looks now and how it used to look here:
http://www.catonmat.net/blog/generating-feedburner-graphs/

The new solution takes 35MB of RAM, responds in 4 seconds and worst of all,
looks very, very ugly.

I didn't want to see this ugliness anymore, therefore I created a Perl program
that generates the awesome graph they used to have.


[2]-My-solution:-generate_feedburner_graph.pl---------------------------------

Use generate_feedburner_graph.pl to generate a nice .gif image for your feed:

    $ generate_feedburner_graph.pl <feed name> [<start date> [<end date>]]

The program can take 3 parameters:
    <feed name> is the Feedburner's feed name, for example, "catonmat".
    <start date> is the date to start generating graph from.
    <end date> is the date to generate graph to.

If the <end date> is not specified, it's set to today's date.
If the <start date> is not specified, it's set to the first day when the feed
had at least one subscriber.

Here is an example run:

    $ generate_feedburner_graph.pl catonmat
    Finding feed's start date...
    Trying 2009-05-17 as start date...
    Trying 2008-11-17 as start date...
    Trying 2008-05-17 as start date...
    Trying 2007-11-17 as start date...
    Trying 2007-05-17 as start date...
    Found 2007-07-15 as start date!
    Getting feed data for catonmat from 2007-07-15 to 2009-11-17
    Creating the awesome feedburner image.
    Done. Image written to catonmat-2007-07-15-2009-11-17.png

It found the feed's start date which happened to be 2007-07-15 and set the
end date to 2009-11-17 (the day I ran the program).

You can see the generated "catonmat-2007-07-15-2009-11-17.png" image at the
bottom of my article:
http://www.catonmat.net/blog/generating-feedburner-graphs/

Oh, one more thing - the program requires DejaVu Sans font (it uses this font
to add text labels). Download it here:
http://dejavu-fonts.org/wiki/index.php?title=Download

------------------------------------------------------------------------------

Have fun generating these awesome graphs for your blogs!

I am soon gonna improve this program and release feedburner graph generator 2,
which will add some more info about min, max, average subscriber count, and
perhaps current trend.


Sincerely,
Peteris Krumins
http://www.catonmat.net


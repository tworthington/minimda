# Introduction<a id="orgheadline2"></a>

Minimda was written in order to avoid having to wade through buckets
of documentation for other mdas (mail delivery agents) when all I
wanted was something that fetchmail could use to drop mail from
different accounts into some folders on my home computer.

## Copyright<a id="orgheadline1"></a>

By [Thomas Worthington](thomas@technouveau.co.uk) (2015); This code is public domain; use it as
you like.

# Installation<a id="orgheadline3"></a>

Simply put minimda into some path where anyone can find it - for
example /usr/local/bin - and grant the world read and execute rights.

Then modify/create a fetchmailrc that looks something like:

    poll outlook.office365.com with proto POP3 port 995
      user 'thomas.worthington@xxxxxxxxx' there with password '?????'
      is thomas here
      keep options ssl
      mda "/usr/local/bin/minimda .maildir/ulcc"
    
    poll pop.1and1.co.uk with proto POP3 port 995
      user 'thomas@technouveau.co.uk' there with password '======'
      is thomas here
      keep options ssl
      mda "/usr/local/bin/minimda .maildir/technouveau"

and so forth, with one fetchmail section per email account, and Bob's
your uncle.
# collectivize

!SLIDE

# Collectivize!

## aram price

### sharethrough, inc.

!SLIDE

# In the beginning

AWS Console

+

`userdata.sh` - manually edited

!SLIDE

# Enter `rake`

`rake launch` - creates userdata.sh

!SLIDE

# Chef Server!

queue installation montage

`rake launch RUN_CHEF=true`

... is Chef Server running?

!SLIDE

# Now we maintain...

Chef Server

CouchDB

Single Point of catastrophe

!SLIDE

# Recipes are awesome

ditch the server

where do we get recipes

!SLIDE

# Capistrano!

recipes go in the repo

`rake launch && cap configure $NODE`

!SLIDE

# uh-oh

http://www.downforeveryoneorjustme.com/github.com

also...

!SLIDE

# Recipe testing is slow

update

`git ci && git push`

`cap configure $NODE`

rinse/repeat

!SLIDE

# Going Old School

`rsync` FTW!

!SLIDE

# Currently

``` shell
cap nodes:web:create
#=> booted ec2-1-2-3-4.compute-1.amazonaws.com
#=> created deploy file at: config/deploy/i-deadbeef.rb
#=> configure via: cap i-deadbeef nodes:web:configure

cap i-deadbeef nodes:web:configure
#=> rsync recipes/. ec2-1-2-3-4.compute-1.amazonaws.com:/tmp/chef/
#=> running: chef-solo
#=> ....
```

!SLIDE

# Problems

launch + configure is slow when there's an outage

packages become unavailable

!SLIDE

# Future

bake recipes into an image (AMI)

launch instances from a known good image

!SLIDE

thanks!

questions?

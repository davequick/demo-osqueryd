# Running on a mac

```console
$ export DOCKERHOST=$(ifconfig | grep -E "([0-9]{1,3}\.){3}[0-9]{1,3}" | grep -v 127.0.0.1 | awk '{ print $2 }' | cut -f2 -d: | head -n1)
$ docker-compose up
```

then demo the data rolling into kibana... 

then to simulate someone doing potential bad things to a system, we'll just copy an executable in sbin... 
```console
$ docker exec demo-osqueryd_osqueryd_1 cp /sbin/zdump /sbin/badactor
```

now go and search for badactor and find the record of a new file being introduced

then change it again... 
```console
$ docker exec demo-osqueryd_osqueryd_1 cp /sbin/hwclock /sbin/badactor
```

and show a second line recorded that details a change in /sbin/ to the same file.


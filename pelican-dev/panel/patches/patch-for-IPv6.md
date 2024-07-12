By default the Pelican Panel does not allow to add a IPv6 address as allocation to a node. For this there's a patch that one could apply.

For this we execute the following on the server console:

```bash
cd /var/www/pelican && curl https://patch-diff.githubusercontent.com/raw/pelican-dev/panel/pull/429.patch | patch -p1
```

Here replace the cd command path with your path where you run your panel. After this applied, we should be able to add a IPv6 address to our node allocations.

This is tested on Pelican Panel version 1.0.0-beta6.
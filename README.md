# HomeServer

Project heavily inspired by [ghostserverd/mediaserver-docker](https://github.com/ghostserverd/mediaserver-docker).  
You will need to add the following to your hosts file:
<details><summary>Click for DNS entries</summary>

```  
127.0.0.1 plex
127.0.0.1 radarr
127.0.0.1 sonarr
127.0.0.1 bazarr
127.0.0.1 prowlarr
127.0.0.1 organizr
127.0.0.1 qbittirrent
127.0.0.1 filebot
127.0.0.1 overseerr  
```

</details>
<details><summary>Location of hosts file per OS</summary>

## Windows
Edit ```C:\Windows\System32\drivers\etc\hosts```

## Linux & Mac
Edit ```/etc/hosts```
</details>

Of course copy ```example_env - rename to .env``` rename to ```.env```. Only thing that **_needs_** to be changed is. 
```
## Media Volumes - MUST CHANGE
TVSHOWS_LOC=/use/your/own/locations/forShows
MOVIES_LOC=/use/your/own/locations/forMovies
DOWNLOADS_LOC=/use/your/own/locations/forDownloads
```
All the rest is optional. But please keep in mind that if you change the ports you **_will_** have to change the ports in the vhosts as well.
  
If everything is setup correctly you can call each service by these names.  
If it defaults to your search engine instead, append ```/``` as in ```plex/``` and it should work. For the moment it is not setup to be easily 
available from the outside, though you could setup apache to do that.  
Just modify 
```apache/conf/httpd.conf``` and the vhosts ```apache/vhosts/0*-<service>.conf``` to the domain you have. Letsencrypt integration is not yet a priority for me.

# Comandos utilizados

```bash
ps -o pid,ppid,stat,nice,vsz,rss,comm | grep 148
top -n 1 | grep -E 'PID|148'
pstree -p 148

cat /proc/148/status
cat /proc/148/stat
cat /proc/148/cmdline | tr '\0' ' '
cat /proc/148/limits

ls /proc/148/task

renice 15 -p 148
ps -o pid,nice,comm | grep 148

kill -STOP 148
ps -o pid,stat,comm | grep 148

kill -CONT 148
ps -o pid,stat,comm | grep 148

kill -TERM 148
ps -o pid,stat,comm | grep 148
```

O `ps` do BusyBox do JSLinux não aceita todas as opções do `ps` tradicional; por isso os comandos foram adaptados.

# Comandos utilizados

## Identificação do processo
ps -o pid,ppid,stat,nice,vsz,rss,comm | grep 148

## Árvore de processos
pstree -p 148

## Estado e recursos — primeiro momento
top -n 1 | grep -E 'PID|148'

## Estado e recursos — segundo momento
top -n 1 | grep -E 'PID|148'

## Threads
ls /proc/148/task

## Prioridade / nice
ps -o pid,nice,comm | grep 148
renice 15 -p 148
ps -o pid,nice,comm | grep 148

## Fontes em /proc
cat /proc/148/status
cat /proc/148/stat
cat /proc/148/cmdline | tr '\0' ' '
cat /proc/148/limits

## Sinais
kill -STOP 148
ps -o pid,stat,comm | grep 148

kill -CONT 148
ps -o pid,stat,comm | grep 148

kill -TERM 148
ps -o pid,stat,comm | grep 148

## Observação
O ambiente utilizado foi JSLinux com Alpine Linux x86_64. Algumas opções do comando ps não estavam disponíveis por causa das limitações do BusyBox.

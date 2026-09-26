# Evidência 05 — /proc

Nesta pasta estão as evidências obtidas no diretório `/proc/148`, utilizado para consultar informações internas do processo analisado.

Foram consultadas as seguintes fontes:

- `/proc/148/status` — informações gerais do processo, incluindo estado e quantidade de threads.
- `/proc/148/stat` — informações e contadores do processo.
- `/proc/148/cmdline` — linha de comando utilizada para iniciar o processo.
- `/proc/148/limits` — limites de recursos aplicados ao processo.

Comandos utilizados:

```bash
cat /proc/148/status
cat /proc/148/stat
cat /proc/148/cmdline | tr '\0' ' '
cat /proc/148/limits

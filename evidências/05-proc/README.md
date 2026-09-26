# Evidência 05 — /proc

Nesta pasta estão as evidências obtidas no diretório `/proc/148`, utilizadas para consultar informações internas do processo analisado.

Foram consultadas as seguintes fontes:

- `/proc/148/status` — informações gerais sobre o estado e características do processo.
- `/proc/148/stat` — informações e contadores relacionados ao processo.
- `/proc/148/cmdline` — linha de comando utilizada para iniciar o processo.
- `/proc/148/limits` — limites de recursos aplicados ao processo.

O processo analisado foi o PID 148 (`app.sh`).

A linha de comando identificada foi:

`/bin/sh ./app.sh`

Também foi consultado `/proc/148/task`, que apresentou o identificador `148`, indicando uma única thread observável no processo analisado.

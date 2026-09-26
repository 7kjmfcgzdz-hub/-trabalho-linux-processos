# Relatório técnico — Diagnóstico de Processos em Linux

## PID e PPID
O processo analisado foi `app.sh`, PID 148, com PPID 67.

## Árvore de processos
`pstree -p 148` apresentou `app.sh(148)---dormir(149)`, demonstrando a relação pai/filho.

## Estado e recursos
O processo foi observado em `S`/`SN`. Em dois momentos, `top` registrou 0% de CPU e cerca de 1% de VSZ. A consulta com `ps` registrou VSZ 1648 e RSS 724.

## Prioridade e nice
O nice inicial era 10. Após `renice 15 -p 148`, a verificação mostrou `148 15 app.sh`, comprovando a alteração.

## Threads
`ls /proc/148/task` retornou apenas `148`, indicando uma única thread observável nesse ambiente.

## /proc/148
Foram analisados `status`, `stat`, `cmdline` e `limits`. O `cmdline` confirmou `/bin/sh ./app.sh`.

## Sinais
`SIGSTOP` mudou o estado para `T` (parado). `SIGCONT` fez o estado voltar para `S`. `SIGTERM` encerrou o processo; a consulta posterior não mostrou o PID 148.

## Limitação do ambiente
O JSLinux utiliza BusyBox, cuja versão de `ps` tem sintaxe e campos diferentes. Os comandos foram adaptados e essa limitação deve ser registrada na entrega.

## Diagnóstico final
As evidências permitem acompanhar o processo durante identificação, observação de recursos, alteração de prioridade, verificação de threads, consulta de `/proc`, interrupção, retomada e encerramento controlado.

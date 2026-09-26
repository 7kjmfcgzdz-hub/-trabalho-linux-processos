# Evidência 06 — Sinais

Foram realizados testes com sinais sobre o processo PID 148.

## SIGSTOP

O comando `kill -STOP 148` suspendeu o processo.
A verificação mostrou o estado `T`.

## SIGCONT

O comando `kill -CONT 148` retomou a execução do processo.
A verificação mostrou novamente o estado `SN`.

## SIGTERM

O comando `kill -TERM 148` encerrou o processo.
Após o comando, o processo PID 148 não apareceu mais na consulta do `ps`.

Esses testes demonstram, respectivamente, a suspensão,
retomada e finalização do processo.

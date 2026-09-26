# Trabalho 1 — Diagnóstico de Processos em Linux

**Aluno:** Ana Keliny Romão de Souza  
**Disciplina:** Sistemas Operacionais — ADS  
**Ambiente:** JSLinux / Alpine Linux x86_64  
**Processo analisado:** `app.sh` (PID 148)

## Diagnóstico realizado

- PID: 148
- PPID: 67
- Estado inicial observado: `S`/`SN`
- Árvore: `app.sh(148)---dormir(149)`
- CPU em dois momentos: 0%
- VSZ: 1648; RSS: 724 na consulta com `ps`
- Nice inicial: 10
- Nice após `renice 15 -p 148`: 15
- Threads observáveis: uma (`/proc/148/task/148`)
- Fontes analisadas em `/proc/148`: `status`, `stat`, `cmdline` e `limits`
- `cmdline`: `/bin/sh ./app.sh`
- SIGSTOP: estado passou para `T`
- SIGCONT: estado voltou para `S`
- SIGTERM: `app.sh` foi encerrado e o PID 148 deixou de aparecer na consulta

## Limitação do ambiente

O JSLinux utiliza BusyBox e seu `ps` possui opções diferentes do `ps` tradicional. Os comandos foram adaptados ao ambiente real utilizado, preservando as evidências exigidas.

## Conclusão

O experimento demonstrou a identificação e hierarquia do processo, seu estado, consumo de recursos, prioridade/nice, threads, informações de `/proc` e as mudanças provocadas por SIGSTOP, SIGCONT e SIGTERM.

**Importante:** as capturas reais do terminal devem ser colocadas nas pastas `evidencias/` correspondentes antes da entrega.

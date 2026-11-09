# MedAgenda — plano de testes e validação

Repositório do trabalho de Teste de Software da Unifacisa (2026.2). O MedAgenda é uma aplicação de referência fornecida pelo professor para simular a rotina de uma clínica. O trabalho avalia o comportamento do sistema e reúne os artefatos de teste da equipe.

## Escopo

- Autenticação e permissões de administrador, recepção, médico e paciente.
- Cadastro de pacientes, horários disponíveis, agendamento e ciclo da consulta.
- Atendimento, prontuário, notificações, PDFs, relatórios e assistente virtual.
- Segurança, desempenho, acessibilidade, compatibilidade e tratamento de erros.

A aplicação fornecida é a referência para os testes. A equipe mantém seus artefatos neste repositório e registra defeitos sem modificar o código da aplicação.

## Ambiente local

Pré-requisitos: Docker com Compose e o pacote `medagenda.zip` disponibilizado no Canvas. Extraia o pacote e execute na pasta que contém `docker-compose.yml`:

```sh
docker compose up --build
```

| Serviço | Endereço local |
| --- | --- |
| Interface React | `http://localhost:8080` |
| API Node.js | `http://localhost:3000/api` |
| Saúde da API | `http://localhost:3000/api/saude` |
| MongoDB | `mongodb://localhost:27017/medagenda` |

Use as contas fictícias do guia da disciplina. Para restaurar os dados locais entre rodadas, execute:

```sh
docker compose exec api npm run seed
```

O comando restaura a massa de teste e recalcula as datas de exemplo. Para cenários que dependem do calendário, derive a data do dia da execução e registre o horário usado.

## Etapas

| Etapa | Trabalho previsto |
| --- | --- |
| Planejamento | Escopo, requisitos, diagramas, ferramentas e cronograma. |
| Projeto de testes | Casos vinculados aos requisitos, cenários Gherkin e matriz de rastreabilidade. |
| Execução e validação | Testes manuais e automatizados, evidências, defeitos e parecer final. |

Os testes automatizados serão organizados em `tests/` por tipo. A integração contínua está prevista para executar a suíte com GitHub Actions e Docker Compose.

## Registro de defeitos

Abra uma issue por defeito com requisito, ambiente, perfil, passos de reprodução, resultado esperado, resultado obtido e evidência. Use dados fictícios e remova tokens ou outras credenciais das evidências.

## Referências

- [Modelo de entrega do MedAgenda](https://unifacisa.instructure.com/courses/17141/files/4636543?wrap=1)
- [Guia de execução](https://unifacisa.instructure.com/courses/17141/files/4636544?wrap=1)
- [Instruções de entrega](https://unifacisa.instructure.com/courses/17141/files/4636675?wrap=1)

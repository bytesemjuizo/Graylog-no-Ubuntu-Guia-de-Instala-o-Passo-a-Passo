# Graylog-no-Ubuntu-Guia-de-Instala-o-Passo-a-Passo
# Graylog no Ubuntu — Guia de Instalação Passo a Passo

Este guia mostra, de forma simples e prática, como instalar o **Graylog** num servidor **Ubuntu**, incluindo as dependências necessárias:

- **MongoDB**
- **OpenSearch**
- **Graylog Server**

Foi escrito para quem quer montar um ambiente de testes, laboratório ou pequena infraestrutura sem complicações desnecessárias.

---

## O que é o Graylog?

O **Graylog** é uma plataforma de centralização e análise de logs.  
Com ele, podes:

- receber logs de servidores, firewalls, switches e aplicações
- pesquisar eventos rapidamente
- criar dashboards
- configurar alertas
- melhorar troubleshooting e auditoria

Em vez de veres logs em vários servidores separados, o Graylog permite reunir tudo num só lugar.

---

## Como funciona esta instalação?

Neste guia, o ambiente será composto por:

- **1 servidor Ubuntu**
- **MongoDB** → usado pelo Graylog para metadados e configurações
- **OpenSearch** → usado para indexar e pesquisar logs
- **Graylog Server** → interface web e motor principal da plataforma

> Este cenário é ideal para laboratório, testes, prova de conceito ou ambientes pequenos.

---

## Requisitos mínimos recomendados

Para um ambiente simples de testes:

- **Sistema operativo:** Ubuntu Server 22.04 ou 24.04
- **CPU:** 4 vCPU
- **Memória RAM:** 8 GB
- **Disco:** 50 GB
- **Acesso:** utilizador com permissões `sudo` ou `root`
- **Rede:** acesso à internet para instalar pacotes

> Para produção, recomenda-se mais RAM, mais disco e separação de serviços.

---

## Portas utilizadas

Durante a instalação e utilização do Graylog, estas portas são as mais comuns:

| Porta | Protocolo | Uso |
|------:|-----------|-----|
| 9000  | TCP | Interface web do Graylog |
| 1514  | UDP | Exemplo de receção Syslog |
| 27017 | TCP | MongoDB |
| 9200  | TCP | OpenSearch API |
| 9300  | TCP | Comunicação interna OpenSearch |

---

## Antes de começar

É importante garantir que:

- o servidor tem acesso à internet
- o relógio está certo
- o hostname do servidor está corretamente definido
- tens permissões administrativas

Podes verificar o hostname com:

```bash
hostnamectl

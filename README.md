# Computação em Nuvem — Aula 04

Nesta aula estudamos sobre virtualização, máquinas virtuais, contêineres e Docker, relacionando esses conceitos com a computação em nuvem.

A parte prática foi realizada no Killercoda, utilizando comandos do Docker para criar, executar, testar e remover contêineres.

## Conteúdo da aula

Durante a aula foram trabalhados os seguintes assuntos:

- Virtualização e máquinas virtuais
- Hypervisor
- Contêineres
- Docker
- Imagens e contêineres
- Diferenças entre máquinas virtuais e contêineres
- Utilização de portas
- Contêineres em ambientes de nuvem

## Atividade prática

Na prática, primeiro verifiquei se o Docker estava funcionando no ambiente e depois executei o contêiner `hello-world`.

Também criei um servidor web utilizando o Nginx:

```bash
docker run -d --name web-aula4 -p 8080:80 nginx:alpine
Depois utilizei o docker ps para verificar o contêiner e o curl para testar o acesso ao servidor:

docker ps
curl localhost:8080

Após confirmar que o Nginx estava funcionando, alterei a página inicial do servidor diretamente dentro do contêiner utilizando o docker exec.

Também utilizei o docker stats --no-stream para verificar informações sobre o uso de CPU, memória e rede.

No final, parei e removi o contêiner utilizado na atividade.

Desafio prático

No desafio da aula, a proposta foi criar um novo contêiner utilizando a imagem nginx:alpine, mas utilizando a porta 8081.

O comando utilizado foi:

docker run -d --name desafio-aula4 -p 8081:80 nginx:alpine

Depois verifiquei se o contêiner estava em execução e testei o acesso com:

docker ps
curl localhost:8081

Após realizar o teste, o contêiner foi parado e removido.

Atividade final

Também respondi às perguntas finais da aula sobre a diferença entre máquinas virtuais e contêineres, a diferença entre imagem Docker e contêiner e a utilização de contêineres em ambientes de nuvem.

O que eu aprendi

Essa aula ajudou a entender melhor na prática como o Docker trabalha com imagens e contêineres.

Através dos comandos, consegui acompanhar todo o processo desde a criação do contêiner até o teste de uma aplicação web rodando com Nginx. Também consegui entender melhor como funciona o mapeamento de portas e como podemos alterar uma aplicação que está dentro de um contêiner.

A prática acabou facilitando bastante o entendimento da parte teórica, principalmente sobre a diferença entre imagem, contêiner e máquina virtual.

Arquivos deste repositório
ATIVIDADE- PRATICA AULA 4.docx — atividade prática realizada durante a aula.
Desafio_Pratico_Aula_4.docx — desafio proposto na aula.
Respostas_perguntas_Aula_4.docx — respostas das perguntas finais.

Disciplina: Computação em Nuvem
Aula: 04 — Virtualização e Contêineres na Nuvem
Ambiente utilizado: Killercoda

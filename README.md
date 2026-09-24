# Aula 4 — Virtualização e Contêineres na Nuvem

Nesta aula de Computação em Nuvem, estudamos sobre virtualização, máquinas virtuais, contêineres e Docker.

Além da parte teórica, fizemos algumas atividades práticas no Killercoda para entender melhor como funciona um contêiner e como podemos executar uma aplicação dentro dele.

## O que foi estudado

Durante a aula, vimos:

- Virtualização;
- Máquinas virtuais;
- Hypervisor;
- Contêineres;
- Docker;
- Imagens e contêineres;
- Diferença entre máquina virtual e contêiner;
- Uso de portas para acessar uma aplicação.

Uma das diferenças que vimos é que a máquina virtual possui seu próprio sistema operacional, enquanto o contêiner compartilha o kernel do sistema que está executando ele. Por isso, os contêineres são mais leves e iniciam mais rapidamente.

## Atividade prática

A primeira coisa que fiz foi verificar se o Docker estava funcionando corretamente no ambiente:

```bash
docker info | head

Depois executei o primeiro contêiner usando a imagem `hello-world`:

```bash
docker run hello-world
```

Também verifiquei quais imagens estavam disponíveis:

```bash
docker images
```

Depois disso, criei um contêiner utilizando o Nginx para funcionar como um servidor web:

```bash
docker run -d --name web-aula4 -p 8080:80 nginx:alpine
```

Usei o comando `docker ps` para verificar se o contêiner estava rodando e depois testei o servidor com:

```bash
docker ps
curl localhost:8080
```

O Nginx respondeu normalmente e mostrou a página HTML padrão.

## Alterando a página

Depois que o Nginx estava funcionando, fiz uma alteração na página que estava dentro do contêiner usando o `docker exec`.

A página passou a mostrar:

```text
Aula 4 - Computacao em Nuvem
Meu Primeiro Conteiner
```

Depois testei novamente com o `curl` para conferir se a alteração tinha funcionado.

Também utilizei:

```bash
docker stats --no-stream
```

para verificar informações sobre o uso de CPU, memória e rede do contêiner.

No final dessa parte, parei e removi o contêiner:

```bash
docker stop web-aula4
docker rm web-aula4
```

## Desafio prático

No desafio da aula, a proposta era criar outro contêiner usando a mesma imagem `nginx:alpine`, mas utilizando uma porta diferente.

Criei o contêiner com:

```bash
docker run -d --name desafio-aula4 -p 8081:80 nginx:alpine
```

Depois verifiquei se ele estava funcionando:

```bash
docker ps
```

E fiz o teste utilizando a nova porta:

```bash
curl localhost:8081
```

O Nginx respondeu normalmente, mostrando que o segundo contêiner estava funcionando. Depois parei e removi o contêiner:

```bash
docker stop desafio-aula4
docker rm desafio-aula4
```

Esse desafio foi importante para praticar novamente a criação e o gerenciamento de um contêiner, além de entender melhor como funciona o mapeamento de portas.

## Atividade final

No final da aula também respondi algumas perguntas sobre o conteúdo estudado, envolvendo:

* Diferença entre máquina virtual e contêiner;
* Diferença entre imagem Docker e contêiner;
* Por que os contêineres são utilizados em ambientes de nuvem.

As respostas foram feitas com base no conteúdo da aula.

## O que eu aprendi

Essa aula me ajudou a entender melhor como funciona o Docker na prática. Antes de fazer os comandos, alguns conceitos sobre imagens, contêineres e portas ficavam mais na parte teórica.

Fazendo a atividade, consegui ver na prática como criar um contêiner, colocar um servidor Nginx para funcionar, acessar esse servidor, alterar uma página e depois parar e remover o contêiner.

Também consegui entender melhor a diferença entre uma imagem e um contêiner. A imagem funciona como a base usada para criar o contêiner, enquanto o contêiner é o ambiente que está sendo executado.

---

**Disciplina:** Computação em Nuvem
**Aula:** 04 — Virtualização e Contêineres na Nuvem
**Práticas:** Docker, Nginx e Contêineres
**Ambiente utilizado:** Killercoda

```
```



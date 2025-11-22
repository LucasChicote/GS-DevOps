# DevOps e Cloud Computing
## MentalCheck – Bem-estar emocional como parte da rotina de trabalho

O MentalCheck é um aplicativo desenvolvido com foco em promover o equilíbrio emocional de trabalhadores, prevenindo casos de burnout e aumentando a autoconsciência sobre fatores que influenciam motivação, estresse, cansaço e satisfação profissional.
A proposta central do sistema é oferecer um método simples, rápido e inteligente para que colaboradores realizem check-ins diários sobre seu estado emocional, possibilitando o acompanhamento contínuo e a identificação de padrões comportamentais ao longo das semanas e meses. Além disso, o projeto contribui para que gestores tenham acesso a métricas anônimas e agregadas, permitindo decisões mais estratégicas e humanizadas, sem violar a privacidade dos usuários.

### GlobalSolution
Nessa primeira parte da GS foi criada uma Máquina Virtual no provedor de Nuvem(Azure) por Debian/Ubuntu. E a solução foi planejada e arquitetada por *container docker* para e melhorar a experiência do projeto e fazer crud pelo docker

## Como foi planejado a estrutura de deploy

* Virtualização --> **Containers em Docker** 
* Provedor de Nuvem --> Máquina Virtual Debian pelo **Microsoft Azure** 
* Root --> Tabelas SQL

## Diagrama de Arquitetura Macro
<img width="2226" height="681" alt="DiagramaDeAquiteturaMacro_BackEnd" src="https://github.com/user-attachments/assets/8c44bd4d-d9eb-489c-9c8e-a60d0d718c75" />


## Comandos para o deploy para o crud

1. Aqui foi criado um container para o MYSQL
```bash
docker run --name tabelas-banco-de-dados -p 3306:3306 -e MYSQL_ROOT_PASSWORD=RM559366 -v "C:/Users/lucas/Desktop/GS_BACKEND/BancoDeDados":/docker-entrypoint-initdb.d -d mysql:8.0
```
2. Acessando  o mysql por root
```bash
winpty docker exec -it tabelas-banco-de-dados mysql -u root -p
```
## Comandos para criação de uma database

1. Criação de uma database
```bash
CREATE DATABASE mentalcheck;
```

```bash
USE mentalcheck
```

## Crud

1. CREATE
```bash
INSERT INTO GS_USUARIO (nome, email, senha, cargo, modalidade_trabalho)
VALUES ('Lucas Chicote', 'lucas@teste.com', '123456', 'Analista', 'Home Office');
```
2. READ
```bash
SELECT * FROM GS_USUARIO;

SELECT * FROM GS_USUARIO
WHERE id_usuario = 1;
```
3. UPDATE
```bash
UPDATE GS_USUARIO
SET cargo = 'Gestor', modalidade_trabalho = 'Presencial'
WHERE id_usuario = 1;
```
4. DELETE
```bash
DELETE FROM GS_USUARIO
WHERE id_usuario = 1;
```

# Vídeo demonstrativo do CRUD

[![Vídeo de Demonstração da Sprint 2](https://img.youtube.com/vi/zdbPgIbVH-s/hqdefault.jpg)](https://youtu.be/zdbPgIbVH-s?si=DIloXwdbeYgNG8x4)

   




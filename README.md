#  SoloLab - Arquitetura de Backend para IoT 

> O código-fonte deste projeto está em repositórios privados (`SoloLab_Back`, `SoloLab_Front`, `SoloLab_Hardware`) pertencentes à organização da disciplina de Projeto de Engenharia de Computação da UFMT. 
> 
> Este repositório serve para demonstrar as decisões técnicas, a stack e os padrões de projeto utilizados no desenvolvimento do Backend.

##  Visão Geral do Sistema
O **SoloLab** é uma solução integrada de hardware e software voltada para o monitoramento inteligente de plantas domésticas. O sistema preenche a lacuna do mercado com um modelo de intervenção ativa baseado em dados quantitativos.

Meu papel geral foi desenvolver o **Back-end**, minhas funções giraram em torno de planejar e criar a ponte entre a telemetria do hardware (umidade, luz e temperatura) e as interfaces de usuário.

## Stack Tecnológica
O backend foi construído com foco em performance e ferramentas modernas de ecossistema Python:
* **Framework:** Django 
* **Banco de Dados:** MySQL 
* **Gerenciamento de Pacotes:** `uv` 
* **Infraestrutura:** Docker e Docker Compose
* **Qualidade de Código:** Ruff 
* **Documentação de API:** Swagger

##  Arquitetura do Sistema e Fluxo de Dados
A visão geral de como o sistema se comunica, desde o embarcado (ESP32) passando pela nossa API em Django, até ao banco de dados e aos serviços de IA externos (Groq), está documentada nos diagramas.

Usamos a separação de responsabilidades prevista no Django, dividido nos seguintes apps modulares:

1. `authentication`: Gestão de usuários, tokens e segurança criptografada.
2. `plants`: Lógica de negócios de botânica, cadastro de espécies e parâmetros ideais de calibração.
3. `iot`: Ingestão de dados de telemetria em tempo real recebidos do hardware físico.
4. `recommendations`: Módulo integrado com Inteligência Artificial para gerar diagnósticos em linguagem natural sobre o estado de saúde da planta.
5. `integrations`: Serviços de comunicação externa e disparos de notificações push.

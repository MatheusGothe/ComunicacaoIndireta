# Sistema Distribuído de Mineração e Coordenação via MQTT

Este projeto implementa um sistema distribuído que simula um ambiente de mineração de criptomoedas (Proof of Work), utilizando o paradigma de comunicação indireta **Publish/Subscribe**. O sistema realiza descoberta de pares, eleição de líder (algoritmo Bully adaptado) e processamento de transações de forma descentralizada.

Desenvolvido como parte da disciplina de **Programação Paralela e Distribuída**.

## 📋 Funcionalidades

* **Descoberta de Pares (Discovery):** Sincronização inicial para garantir que todos os nós estejam online antes de começar.
* **Eleição de Líder (Bully):** Algoritmo de consenso para decidir quem será o **Controlador** (gera desafios) e quem serão os **Mineradores** (resolvem desafios).
* **Mineração (Proof of Work):** Uso de *Multithreading* para resolver desafios criptográficos (SHA-1) em paralelo.
* **Tolerância a Falhas:** Mecanismo de "Descoberta Implícita" que permite aceitar votos de nós desconhecidos para evitar *deadlocks* em redes instáveis.
* **Comunicação Indireta:** Uso de protocolo MQTT para desacoplamento total entre os processos.

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Python 3.x
* **Middleware:** MQTT (via `paho-mqtt`)
* **Broker Público:** `broker.emqx.io` (Porta 1883)
* **Bibliotecas:** `threading`, `json`, `hashlib`, `random`

## 🚀 Como Executar

Siga os passos abaixo para configurar e rodar o projeto em sua máquina local.

### 1. Configuração do Ambiente (Windows)

Abra o terminal (PowerShell) na pasta raiz do projeto e execute os comandos em sequência:

```powershell
# 1. Cria o ambiente virtual (venv) para isolar as dependências
python -m venv venv

# 2. Ativa o ambiente virtual
.\venv\Scripts\activate

# 3. Instala as bibliotecas necessárias (paho-mqtt)
pip install -r requirements.txt

# 4. Configuração do Número de Participantes
#No arquivo main.py, ajuste o número total de nós que irão participar do sistema:
NUM_PARTICIPANTES = 3

# 5. Execução 
python main.py
```



# 📘 Projeto Java + Spring Boot: Leitor de Extrato Bancário Legado

Este projeto simula a leitura de um extrato bancário em formato `.txt` e exibe os dados no navegador em formato JSON usando Spring Boot.
Aqui vai um resumo, mas confira tudo no arquivo PDF neste mesmo diretório

---

## 🧱 PARTE 1 – Configurando o Ambiente

### 1. Instale o Java JDK 17
- Baixe em: https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
- Instale normalmente (duplo clique e seguir os passos).

### 2. Instale o IntelliJ IDEA
- Baixe a versão **Community** (gratuita): https://www.jetbrains.com/idea/download/
- Instale o programa.

---

## 🧰 PARTE 2 – Criando o Projeto Spring Boot

### 1. Abra o IntelliJ IDEA
- Clique em **“New Project”**
- Escolha **“Spring Initializr”**
- Clique em **“Next”**

### 2. Configurações do projeto
- **Group**: `com.extrato`
- **Artifact**: `extratobridge`
- **Name**: `extratobridge`
- **Type**: Maven
- **Language**: Java
- **Java version**: 17
- Clique em **Next**

### 3. Dependências
Marque as seguintes:
- **Spring Web**
- **Spring Boot DevTools**

Clique em **Finish**.

---

## 📁 PARTE 3 – Estrutura de Pastas

### Boas práticas: criar 3 pacotes principais
| Pasta        | Finalidade                                               |
|--------------|-----------------------------------------------------------|
| `model`      | Representa os dados (ex: classe `Transacao`)             |
| `service`    | Lógica de negócio (leitura e processamento de dados)     |
| `controller` | Define as rotas da API (URLs que acessamos via navegador)|

### Criando os pacotes
1. Na aba lateral esquerda (Project), vá até:  
   `src/main/java/com/extrato/extratobridge`
2. Clique com o botão direito > **New > Package**
3. Crie os pacotes:  
   - `model`  
   - `service`  
   - `controller`

---

## ✍️ PARTE 4 – Criar as Classes

### 1. Classe `Transacao.java` (pasta `model`)

```java
package com.extrato.extratobridge.model;

public class Transacao {
    private String data;
    private String descricao;
    private double valor;

    public Transacao(String data, String descricao, double valor) {
        this.data = data;
        this.descricao = descricao;
        this.valor = valor;
    }

    public String getData() { return data; }
    public void setData(String data) { this.data = data; }

    public String getDescricao() { return descricao; }
    public void setDescricao(String descricao) { this.descricao = descricao; }

    public double getValor() { return valor; }
    public void setValor(double valor) { this.valor = valor; }
}

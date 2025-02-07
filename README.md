# 🚀 Testando CI com GitHub Actions

## 📌 Sobre o Projeto  
Este repositório tem como objetivo testar a configuração de uma pipeline de **integração contínua (CI)** usando **GitHub Actions** para uma aplicação escrita em **Go**.  

## O que é Integração Contínua (CI)?  
A **Integração Contínua (CI - Continuous Integration)** é uma prática de desenvolvimento que busca automatizar a integração de código, garantindo que novas mudanças sejam testadas e validadas antes de serem incorporadas ao projeto.  

O **GitHub Actions** permite configurar fluxos de trabalho automatizados dentro do próprio GitHub, ajudando a implementar CI/CD de forma eficiente.  

## Configuração da Pipeline  
O fluxo de trabalho principal está definido em **`.github/workflows/go.yml`** e realiza os seguintes passos:  

1. **Disparo do workflow:**  
   - Aciona em `push` ou `pull_request` na branch `main`.  

2. **Execução do job de CI:**  
   - Usa `ubuntu-latest` como sistema operacional.  
   - Faz checkout do código.  
   - Configura a versão do Go.  
   - Sobe um banco de dados PostgreSQL via Docker Compose.  
   - Executa linting no código.  
   - Roda os testes, passando as credenciais do banco via `secrets`.  
   - Compila a aplicação.  
   - Faz upload do binário compilado como artefato.  

## Testes com Falhas no GitHub Actions  
Durante os testes com o **GitHub Actions**, algumas **actions falharam propositalmente** para entender como o workflow se comporta diante de erros. Os testes incluíram:  

- ❌ Configurar uma versão incorreta do Go.  
- ❌ Introduzir erros de sintaxe para falhar no `lint`.  
- ❌ Remover variáveis de ambiente para falhar nos testes.  
- ❌ Modificar dependências para quebrar a instalação.  

Esses experimentos ajudaram a entender como os logs do **GitHub Actions** podem ser usados para depuração e melhoria do pipeline.  

## 📌 Conclusão  
Este projeto serviu como um experimento para explorar a **Integração Contínua** com **GitHub Actions**. A automação da pipeline torna o desenvolvimento mais confiável e eficiente, garantindo que mudanças no código sejam testadas e validadas antes de serem aplicadas à branch principal.  

---

✍️ _Criado para aprendizado e testes com GitHub Actions_  

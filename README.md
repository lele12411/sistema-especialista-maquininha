# 💳 Sistema Especialista para Suporte de Maquininha de Cartão

Sistema especialista em Python, executado no terminal, que ajuda a diagnosticar problemas comuns de maquininhas de cartão (POS). O usuário digita um código de erro ou descreve o problema com as próprias palavras, e o sistema devolve o **diagnóstico**, a **explicação** e a **ação sugerida**.

## ✨ Funcionalidades

- **Diagnóstico de códigos de erro** (51, 01/05, 54, 62/63, 55, 75, 68, 91/96, entre outros), por código ou por descrição.
- **Diagnóstico de problemas físicos**: atolamento de papel, comprovante saindo em branco e bateria fraca.
- **Operações básicas**: guia de como navegar pelo sistema e dos tipos de pagamento permitidos.
- **Base de conhecimento separada do código** (`base_conhecimento.json`), o que facilita adicionar novos erros sem mexer no Python.

## 🧠 Como funciona

O motor de diagnóstico compara o texto digitado com uma lista de **sintomas** cadastrados em cada regra da base de conhecimento:

1. Se o texto digitado for exatamente um código cadastrado, a regra correspondente é retornada na hora.
2. Caso contrário, cada regra recebe uma **pontuação** pela quantidade de sintomas encontrados no texto.
3. A regra com maior pontuação é exibida como resultado.
4. Se nenhuma regra pontuar, o sistema informa que não conseguiu identificar o problema.

## 📁 Estrutura do projeto

```
.
├── sistema_especialista.py   # Menu, motor de diagnóstico e exibição dos resultados
├── base_conhecimento.json    # Regras: erros de código e problemas físicos
└── README.md
```

## ▶️ Como executar

Requisito: **Python 3.8+** (não precisa instalar nenhuma biblioteca externa).

```bash
git clone https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git
cd NOME-DO-REPOSITORIO
python sistema_especialista.py
```

> Mantenha o `base_conhecimento.json` na mesma pasta do arquivo Python.

## 💬 Exemplo de uso

```
1- Operações Básicas
2- Diagnóstico de Erro
3- Sair
Digite uma opção: 2

1- Códigos de Erro
2- Problemas de Comprovante
3- Voltar
Digite uma opção: 1

Digite o código ou descreva o problema:
> cartao sem limite

==================================================
Diagnóstico: Código 51 - Saldo/Limite Insuficiente
Explicação:  O banco emissor recusou a compra porque a conta não tem saldo (débito) ou o limite de crédito acabou.
Ação Sugerida: Orientar o cliente a utilizar outra forma de pagamento (outro cartão, Pix ou dinheiro).
==================================================
```

## 🛠️ Tecnologias

- Python 3
- JSON (base de conhecimento)

## 🚀 Melhorias futuras

- Ignorar acentos e maiúsculas/minúsculas de forma automática na busca.
- Interface gráfica ou versão web.
- Ampliar a base com mais códigos de erro e problemas de conexão.
- Voltar ao menu principal após cada diagnóstico, sem precisar reiniciar o fluxo.




# 🛒 Daudas Xianyu Helper — BETA

<div align="center">

![Chrome Extension](https://img.shields.io/badge/Chrome-Extension-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)
![Manifest V3](https://img.shields.io/badge/Manifest-V3-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-BETA-ffda00?style=for-the-badge&labelColor=2c3e50)

**Extensão Chrome para análise de vendedores e produtos no Goofish (Xianyu) e CSSBuy.**  
Cotação automática CNY → BRL, score de risco e detecção inteligente de produto — sem cadastro.

[📦 Como instalar](#-como-instalar) • [✨ Funcionalidades](#-o-que-essa-extensão-faz) • [🆕 Novidades](#-novidades-desta-versão) • [⚖️ Licença](#%EF%B8%8F-licença--cc-by-nc-sa-40)

</div>

---

## ✨ O que essa extensão faz

Ao abrir qualquer anúncio no Goofish ou CSSBuy, um painel aparece automaticamente no canto da tela:

| Recurso | Descrição |
|---|---|
| 🧑‍💼 **Score do vendedor** | Risco calculado com base em vendas, nota e tempo de loja |
| 🔍 **Análise do produto** | Detecta automaticamente iPhone, Notebook ou Periférico |
| 💱 **Cotação em tempo real** | Converte Yuan (CNY) → Real (BRL) via AwesomeAPI |
| 🛍️ **Botão CSSBuy** | Abre o item no CSSBuy com um clique |
| ⚡ **Recargas integradas** | Atalhos para ByteMax Exchange e NoobExchange |

---

## 🆕 Novidades desta versão

### 🎮 Módulo de Periféricos — totalmente reescrito

Detecção de marcas ocidentais e chinesas: Logitech, Razer, Endgame Gear, WL Mouse, Mchose, Darmoshark, Akko, Skyloong, Ajazz e mais.

**Estado de conservação inteligente:**

| Texto em chinês | Estado detectado |
|---|---|
| `刚到手` / `使用不超过1天` | 🟡 Seminovo — quase sem uso |
| `全新未拆` / `未拆封` | 🟢 Lacrado / Novo |
| `99新` / `无拆无修` | 🟡 Seminovo — quase novo |
| `二手` / `有划痕` | 🟠 Usado |
| `故障` / `双击` / `漂移` | 🔴 Com defeito |

- **Garantia inteligente** — detecta data de compra (`26年3月购买`) e calcula se ainda está no prazo
- **Caixa original** — reconhece `箱说全`, `原包装盒`, `盒说全`
- **Acessórios** — detecta `配件全齐`, `线材都在`, `接收器都在`

### 🔄 Auto-identificação com retry automático
- Tenta identificar o produto até **5 vezes** com intervalo de 3.5s
- Exibe `⏳ Identificando produto... (tentativa X/5)` enquanto a página carrega
- Só marca como Genérico após esgotar todas as tentativas

### 🔧 Melhorias gerais
- Seletor de modo e cotação 100% clicáveis
- Botões de recarga e CSSBuy sempre posicionados acima da cotação
- Captura de texto ampliada (15.000 chars + `extraBlocks`) para páginas de carregamento lento
- Correção do seletor de preço do CSSBuy: `.price.flex` com limpeza automática de `CNY`

---

## 🗂️ Modos de análise

| Modo | O que analisa |
|---|---|
| **Auto** | Detecta automaticamente o tipo (com retry 5×) |
| **iPhone** | Modelo, bateria, Face ID, bloqueio iCloud, peças trocadas, score |
| **Notebook** | Marca, CPU, GPU, RAM, SSD, tela, bateria, score |
| **Periférico** | Estado, caixa, acessórios, garantia |
| **Genérico** | Memória, armazenamento, bateria |

---

## 📦 Como instalar

> ⚠️ A extensão ainda não está publicada na Chrome Web Store. Instalação manual em 5 passos.

1. Clique em **Code → Download ZIP** e extraia a pasta
2. Abra o Chrome em `chrome://extensions`
3. Ative o **Modo do desenvolvedor** no canto superior direito
4. Clique em **Carregar sem compactação**
5. Selecione a pasta extraída (onde está o `manifest.json`)

Pronto! O painel aparece automaticamente ao abrir qualquer anúncio no [Goofish](https://www.goofish.com) ou [CSSBuy](https://www.cssbuy.com).

> 🔄 Após editar o `content.js`, clique em **Atualizar** na página `chrome://extensions`.

---

## 📁 Estrutura do projeto

```
daudas-xianyu-helper/
├── manifest.json       ← configuração da extensão (Manifest V3)
├── content.js          ← toda a lógica da extensão
├── logo.png            ← ícone Goofish
├── logodaudas.png      ← ícone do painel principal
└── logocss.png         ← ícone do botão CSSBuy
```

---

## 💱 Sobre a cotação

A extensão usa a [AwesomeAPI](https://economia.awesomeapi.com.br) — gratuita e sem cadastro.

- Cache de **15 minutos** para não sobrecarregar a API
- Modo **Automático** (API) ou **Manual** (você define a taxa)
- Nenhum dado do usuário é enviado na requisição

---

## 🙏 Créditos

Este projeto é um fork com melhorias significativas. Créditos completos:

| Autor | Contribuição |
|---|---|
| [**Slet**](https://github.com/Squ3let0n/slet-xianyu-helper) | Criador do projeto original |
| [**Santanna / Carlos**](https://github.com/SantannaCarlos/santanna-xianyu-helper) | Fork intermediário |
| **Daudas** | Módulo de periféricos, CSSBuy, score de vendedor, cotação auto, melhorias gerais |

---

## ⚖️ Licença — CC BY-NC-SA 4.0

| | |
|---|---|
| ✅ Permitido | Usar, compartilhar e modificar com créditos |
| ✅ Obrigatório | Manter créditos ao **Slet**, **Santanna** e **Daudas** |
| ✅ Obrigatório | Redistribuir sob a mesma licença |
| ❌ Proibido | Vender ou usar comercialmente sem autorização |

[![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

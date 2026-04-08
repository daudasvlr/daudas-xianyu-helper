# 🛒 Daudas Xianyu Helper — BETA

> Extensão para Chrome que turbina sua experiência de compra no **Goofish (Xianyu)** e **CSSBuy**.  
> Análise de produtos, cotação automática CNY → BRL e muito mais, direto no navegador, sem cadastro.

Baseado no trabalho de:
- **Slet** — autor original
- **Santanna / Carlos** — fork intermediário

---

## ✨ O que essa extensão faz

Ao abrir qualquer anúncio no Goofish, um painel aparece automaticamente no canto da tela com:

- 🧑‍💼 **Análise do vendedor** — score de risco, vendas, nota e tempo de loja
- 🔍 **Análise do produto** — detecta automaticamente iPhone, Notebook ou Periférico
- 💱 **Cotação em tempo real** — converte Yuan (CNY) para Real (BRL) automaticamente
- 🛍️ **Botão CSSBuy** — abre o item diretamente no CSSBuy com um clique
- ⚡ **Atalhos de recarga** — ByteMax Exchange e NoobExchange integrados

---

## 🆕 Novidades desta versão

### 🎮 Módulo de Periféricos (totalmente reescrito)
- Detecção de **marcas ocidentais e chinesas**: Logitech, Razer, Endgame Gear, WL Mouse, ATK, Mchose, Darmoshark, Akko, Skyloong, Ajazz e mais
- Modelos populares: OP1W, OP1WE, GP Pro, Superlight, Deathadder, Viper, Model O/D, Haste 2...
- **Estado de conservação inteligente** — distingue corretamente:
  - `刚到手` / `使用不超过1天` → 🟡 Seminovo (quase sem uso)
  - `全新未拆` / `未拆封` → 🟢 Lacrado / Novo
  - `99新` / `无拆无修` → 🟡 Seminovo (quase novo)
  - `二手` / `有划痕` → 🟠 Usado
  - `故障` / `双击` / `漂移` → 🔴 Com defeito
- **Garantia inteligente** — detecta data de compra (`26年3月购买`) e calcula se ainda está no prazo
- **Caixa original** — reconhece `箱说全`, `原包装盒`, `盒说全`
- **Acessórios** — detecta `配件全齐`, `线材都在`, `接收器都在`

### 🔄 Auto-identificação com retry automático
- Modo **Auto** tenta identificar o produto até **5 vezes** com intervalo de 3.5s
- Mostra `⏳ Identificando produto... (tentativa X/5)` enquanto aguarda a página carregar
- Só marca como Genérico após esgotar todas as tentativas

### 🔧 Melhorias gerais
- Seletor de modo e cotação 100% clicáveis
- Botões de recarga e CSSBuy sempre acima da cotação
- Campo "Selado" oculto no modo Periférico (irrelevante para esse tipo)
- Captura de texto ampliada (15.000 chars + `extraBlocks`) para páginas com carregamento lento
- Correção do seletor de preço do CSSBuy: `.price.flex` com limpeza de `CNY`

---

## 🗂️ Modos de análise

| Modo | O que analisa |
|---|---|
| **Auto** | Detecta automaticamente o tipo (com retry 5x) |
| **iPhone** | Modelo, bateria, Face ID, bloqueio, peças trocadas, score |
| **Notebook** | Marca, CPU, GPU, RAM, SSD, tela, bateria, score |
| **Periférico** | Estado, caixa, acessórios, garantia |
| **Genérico** | Memória, armazenamento, bateria genérica |

---

## 📦 Como instalar

1. Baixe ou clone este repositório
2. Abra o Chrome em `chrome://extensions`
3. Ative o **Modo do desenvolvedor** (canto superior direito)
4. Clique em **Carregar sem compactação**
5. Selecione a pasta do projeto (onde está o `manifest.json`)
6. Clique no ícone e fixe a extensão na barra do Chrome

> Após editar o `content.js`, clique em **Atualizar** na página `chrome://extensions`.

---

## 📁 Estrutura do projeto

```
daudas-xianyu-helper/
├── manifest.json       ← configuração da extensão (v3)
├── content.js          ← toda a lógica da extensão
├── logo.png            ← ícone do painel (Goofish)
├── logodaudas.png      ← ícone do painel principal
└── logocss.png         ← ícone do botão CSSBuy
```

---

## 💱 Sobre a API de cotação

A extensão usa a [AwesomeAPI](https://economia.awesomeapi.com.br) para buscar a cotação CNY→BRL.

- ✅ 100% gratuita, sem cadastro obrigatório
- ✅ Sem autenticação necessária para a extensão funcionar
- ✅ Cache de 15 minutos para não sobrecarregar a API
- ℹ️ Com API Key gratuita: até 100.000 requisições/min em tempo real

---

## ⚖️ Licença — CC BY-NC-SA 4.0

| | |
|---|---|
| ✅ Permitido | Usar, compartilhar e modificar com créditos |
| ✅ Obrigatório | Manter créditos ao **Slet**, **Santanna** e **Daudas** |
| ✅ Obrigatório | Redistribuir sob a mesma licença |
| ❌ Proibido | Vender ou usar comercialmente sem autorização |

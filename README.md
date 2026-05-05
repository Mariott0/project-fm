# 🎙️ SynthFM - A sua Rádio Pessoal Inteligente

**SynthFM** é um projeto de rádio personalizada integrada com Inteligência Artificial. A proposta é unir o melhor dos dois mundos: a curadoria musical das suas playlists favoritas com a dinâmica, o calor e as informações em tempo real de uma rádio tradicional — tudo gerado de forma inteligente, sob medida para você e com custo otimizado.

---

## 🚀 Como Funciona (Arquitetura Otimizada)

Para garantir **latência zero** (sem silêncios esperando a IA pensar) e **baixo custo de APIs**, o projeto trabalha com um modelo assíncrono:

1. **Geração de Conteúdo (Back-end / Offline):** Um script roda periodicamente, busca notícias de portais (via RSS/APIs), usa IA para redigir roteiros de locução rápidos e amigáveis, e gera os áudios (`.mp3`) usando síntese de voz ultra-realista.
2. **Armazenamento:** Esses áudios de notícias são categorizados (ex: *#tecnologia*, *#games*, *#geral*) e salvos em um banco de dados/storage pronto para uso.
3. **Player (Front-end / Usuário):** O player reproduz a playlist de música do usuário. A cada término de música, o sistema roda um sorteio dinâmico. Se o "locutor" for acionado, ele simplesmente consome um áudio de notícia que já está pronto e otimizado no storage, tocando-o instantaneamente.

---

## 🛠️ Stack Tecnológica Proposta

* **Back-end & Automação:** Python (ideal para manipulação de dados, scripts de raspagem de notícias e integração rápida com SDKs de IA).
* **Banco de Dados & Storage:** Supabase ou Firebase (plano gratuito) para armazenar os metadados das notícias e hospedar os arquivos `.mp3` gerados pelo locutor.
* **Front-end (Player):** React (Vite) ou HTML/JS puro para o MVP (interface simples com controles de reprodução e lógica do player).
* **Inteligências Artificiais:**
    * **Texto (Roteiro):** Gemini API ou OpenAI API (para formatação e estilo do texto).
    * **Voz (Text-to-Speech):** ElevenLabs API (vozes ultra-realistas com pausas e entonações humanas).

---

## 🗺️ Roadmap de Desenvolvimento (O que fazer agora e no futuro)

### 📌 Fase 1: O MVP (Onde focar AGORA)
O objetivo desta fase é validar a dinâmica e a experiência do player com o menor custo possível.

* [ ] **Setup do Ambiente:** Configurar o repositório e estruturar a pasta do projeto em Python.
* [ ] **Player de Áudio Local:** Criar um script básico que consome uma pasta local com músicas `.mp3` e simula a reprodução contínua.
* [ ] **Lógica do Sorteio:** Implementar o algoritmo que decide de forma aleatória (ex: 30% ou 40% de chance) se o locutor vai entrar entre as músicas.
* [ ] **Script de Pré-processamento:**
    * Consumir um feed de notícias simples (RSS gratuito).
    * Enviar o texto para a API de IA criar o roteiro no estilo "locutor de rádio".
    * Enviar o roteiro para a API de TTS (ElevenLabs) e salvar o arquivo `.mp3` final localmente.
* [ ] **Integração do Fluxo:** Fazer o player tocar: *Música 1 ➔ Sorteio ➔ Toca Locutor Pré-gravado (se sorteado) ➔ Música 2*.

---

### 📌 Fase 2: Robustez e Interface (Curto/Médio Prazo)
Melhorar a experiência de uso e profissionalizar a infraestrutura do projeto.

* [ ] **Migração para Nuvem (Database/Storage):** Salvar os áudios gerados no Supabase Storage em vez de localmente na máquina.
* [ ] **Interface Web Básica:** Criar uma tela simples usando Streamlit ou React para o usuário dar "Play", "Pause", ver qual música está tocando e qual foi a última notícia narrada.
* [ ] **Categorização de Notícias:** Permitir que o usuário escolha os assuntos de seu interesse (ex: apenas tecnologia ou esportes) e filtrar os áudios de locutor com base nisso.
* [ ] **Vinhetas e Plástica de Rádio:** Adicionar uma trilha sonora de fundo (trilha branca) bem baixinha enquanto o locutor fala, além de vinhetas curtas de transição (*"Você está ouvindo a SynthFM!"*).

---

### 📌 Fase 3: Recursos Avançados (Longo Prazo / Visão de Futuro)
Transformar o protótipo em um produto de mercado altamente escalável e interativo.

* [ ] **Integração com Plataformas de Streaming:** Integração oficial via APIs do Spotify, YouTube Music ou Deezer para rodar as músicas reais do usuário direto do player dele.
* [ ] **Notícias Locais & Clima:** Coletar a localização aproximada do usuário para que o locutor fale o clima atualizado da cidade dele em tempo real (*"E por aqui em Toledo o sol vai abrindo..."*).
* [ ] **Hora Certa Inteligente:** Adicionar pequenas vinhetas dinâmicas dizendo as horas antes de começar a notícia.
* [ ] **Locutor Clone de Voz:** Permitir que o usuário clone a própria voz ou a voz de um amigo para ser o locutor da rádio dele.
* [ ] **IA Generativa de DJ:** Uma IA que analisa a energia das músicas da playlist e adapta a animação/tom de voz do locutor (ex: voz mais calma para playlists de estudo, voz mais enérgica para playlists de treino).

---

## 👥 Autores

* [Seu Nome]
* Eric

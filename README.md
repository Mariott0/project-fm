# 🎙️ SelFM - A sua Rádio Pessoal Inteligente

**SelFM** é um projeto de rádio personalizada integrada com Inteligência Artificial. A proposta é unir o melhor dos dois mundos: a curadoria musical das suas playlists favoritas com a dinâmica, o calor, efeitos sonoros divertidos e as informações em tempo real de uma rádio tradicional — tudo gerado de forma inteligente, sob medida para você e com custo otimizado.

---

## 🚀 Como Funciona (Arquitetura Otimizada)

Para garantir **latência zero** (sem silêncios esperando a IA pensar) e **baixo custo de APIs**, o projeto trabalha com um modelo assíncrono:

1. **Geração de Conteúdo (Back-end / Offline):** Um script roda periodicamente na nuvem, busca notícias de portais (via RSS/APIs), usa IA para redigir roteiros de locução rápidos e amigáveis, e gera os áudios (`.mp3`) usando síntese de voz ultra-realista.
2. **Armazenamento e Controle (Nuvem):** Esses áudios de notícias são categorizados e salvos em um banco de dados/storage na nuvem para evitar qualquer perda de dados. O sistema mantém um histórico de reprodução para garantir que uma mesma locução nunca seja repetida para o usuário.
3. **Player (Front-end / Usuário):** O player reproduz a playlist de música do usuário. A cada término de música, o sistema roda um sorteio dinâmico. Se o "locutor" for acionado, ele consome um áudio de notícia que já está pronto no storage, tocando-o instantaneamente.

---

## 📱 Estratégia de Plataforma & Lançamento

* **Foco do Produto:** O foco principal do desenvolvimento será **Mobile** (onde o consumo de áudio e rádio é majoritário). A versão para **Desktop** funcionará via Web.
* **Política de Lançamento:** O projeto permanecerá em testes internos e **só será divulgado ao público geral após a integração robusta com plataformas de streaming de áudio** (como Spotify). Até lá, funcionará de forma privada em formato de MVP.

---

## 🛠️ Stack Tecnológica Proposta

* **Back-end & Automação:** Python (ideal para manipulação de dados, scripts de raspagem de notícias e integração rápida com SDKs de IA).
* **Banco de Dados & Storage (100% Nuvem):** Supabase ou Firebase para armazenar os metadados, controle de histórico de roteiros e hospedagem dos arquivos `.mp3` gerados.
* **Front-end (Player):** React Native (para o aplicativo Mobile focado) e React (Vite) para a versão web de Desktop.
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
    * Enviar o roteiro para a API de TTS (ElevenLabs) e salvar o arquivo `.mp3` final.
* [ ] **Integração do Fluxo:** Fazer o player tocar: *Música 1 ➔ Sorteio ➔ Toca Locutor Pré-gravado (se sorteado) ➔ Música 2*.

---

### 📌 Fase 2: Robustez, Nuvem e Controle (Curto Prazo)
Melhorar a experiência de uso, salvar dados na nuvem e evitar repetições.

* [ ] **Infraestrutura 100% em Nuvem:** Migrar armazenamento de áudios e metadados para o Supabase/Firebase, garantindo que nenhum progresso seja perdido.
* [ ] **Controle de Repetição de Roteiros:** Desenvolver um sistema de controle no banco de dados que marca os áudios já ouvidos pelo usuário para impedir que a mesma fala seja repetida.
* [ ] **Interface Web Básica (Desktop):** Criar uma tela simples em React para o usuário dar "Play", "Pause", ver qual música está tocando e qual foi a última notícia narrada.
* [ ] **Categorização de Notícias:** Permitir que o usuário escolha os assuntos de seu interesse (ex: apenas tecnologia ou esportes) e filtrar os áudios de locutor com base nisso.
* [ ] **Efeitos de Sonoplastia ("Zueiras"):** Integrar efeitos sonoros clássicos e divertidos de rádio (ex: disparar um áudio curto de *"dança gatinho, dança!"*, *"demais!"* ou vinhetas engraçadas) antes, durante ou depois da fala do locutor.
* [ ] **Vinhetas e Plástica de Rádio:** Adicionar uma trilha sonora de fundo (trilha branca) bem baixinha enquanto o locutor fala, além de vinhetas de transição (*"Você está ouvindo a SelFM!"*).

---

### 📌 Fase 2.5: O Ecossistema de Anúncios (Futuro Próximo)
Integrar propagandas de forma inteligente para trazer o realismo das rádios comerciais e viabilizar a monetização do projeto.

* [ ] **Lógica de Blocos Comerciais:** Criar a estrutura clássica de rádio (*Música ➔ Notícia ➔ Comercial de 15/30s ➔ Música*).
* [ ] **Anúncios Contextuais (Segmentação):** Associar anúncios ao perfil de interesse do usuário (ex: se o usuário ouve muito sobre tecnologia, ele ouve propagandas de cursos de programação ou eletrônicos).
* [ ] **Anúncios Sintéticos (Gerados por IA):**
    * Criar uma ferramenta interna onde pequenos comércios apenas escrevem um texto institucional sobre sua marca.
    * A IA reescreve no formato de um comercial dinâmico de rádio, adiciona uma trilha de fundo comercial e a voz do locutor narra o anúncio de forma automatizada.
* [ ] **Plano Premium (Ad-Free):** Criar uma chave no banco de dados para usuários "Premium" que desativa a reprodução dos blocos de comerciais, deixando apenas música e notícias.

---

### 📌 Fase 3: Desenvolvimento Mobile, Streaming & Público (Médio/Longo Prazo)
Fase onde o produto atinge maturidade para lançamento oficial de mercado.

* [ ] **Desenvolvimento do App Mobile:** Criar o aplicativo principal focado em dispositivos móveis (iOS e Android).
* [ ] **Integração com Plataformas de Streaming (Marco de Lançamento):** Integrar oficialmente com APIs do Spotify, YouTube Music ou Deezer para rodar as músicas reais do usuário direto do player dele.
* [ ] **Abertura ao Público:** Divulgação oficial e lançamento do app após a conclusão das integrações de streaming.
* [ ] **Notícias Locais & Clima:** Coletar a localização aproximada do usuário para que o locutor fale o clima atualizado da cidade dele em tempo real.
* [ ] **Rádios Compartilhadas (Estilo Jam):** Permitir a criação de salas virtuais onde amigos podem ouvir a mesma playlist simultaneamente, com interrupções do locutor personalizadas para aquele grupo de ouvintes.
* [ ] **Hora Certa Inteligente:** Adicionar pequenas vinhetas dinâmicas dizendo as horas antes de começar a notícia.
* [ ] **Locutor Clone de Voz:** Permitir que o usuário clone a própria voz ou a voz de um amigo para ser o locutor da rádio dele.
* [ ] **IA Generativa de DJ:** Uma IA que analisa a energia das músicas da playlist e adapta a animação/tom de voz do locutor (ex: voz mais calma para playlists de estudo, voz mais enérgica para playlists de treino).

---

## 👥 Autores

* Nathan Mariotto
* Eric Andrade

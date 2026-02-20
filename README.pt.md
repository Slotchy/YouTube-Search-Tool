# 📺 Ferramenta de Busca YouTube

Uma ferramenta baseada na web para pesquisar vídeos e transmissões ao vivo do YouTube em ordem cronológica real usando sua própria chave de API do YouTube. Sem necessidade de login — apenas cole sua chave e pesquise.

## **Ferramenta de Busca YouTube:** https://slotchy.github.io/YouTube-Search-Tool

---

## ✨ Recursos

* 🔍 Pesquise vídeos ou transmissões ao vivo ordenados pelos mais recentes primeiro
* 📅 Filtrar por data — escolha um único dia ou um intervalo de datas personalizado usando um calendário interativo
* 🕐 Filtro de hora — restrinja os resultados a uma janela de tempo específica dentro de uma data selecionada (converte automaticamente seu fuso horário local para UTC)
* 🚫 Filtrar Shorts — oculta vídeos que contêm hashtags (`#`) no título ou descrição
* ⏱️ Filtro de duração de vídeo — quando Vídeos está selecionado, filtre por Curto (<4 min), Médio (4–20 min) ou Longo (20+ min)
* 🎨 8 temas de cores — Roxo, Ciano, Esmeralda, Rosa, Âmbar, Azul, Pink e Lima via painel de amostras
* 💾 Chave de API e tema de cor salvos automaticamente no seu navegador
* ✨ Fundo de partículas animadas, pré-preenchido ao carregar
* 🕒 Exibe o tempo decorrido para cada resultado
* 🖱️ Clique em qualquer resultado para abrir o vídeo diretamente

> **Nota:** O modo de transmissões ao vivo é desativado quando o filtro de data está ativo. O filtro de duração de vídeo só está disponível no modo Vídeos.

---

## 🔑 Como Obter uma Chave de API do YouTube

1. Acesse [console.cloud.google.com](https://console.cloud.google.com)
2. Crie um novo projeto ou selecione um existente
3. Ative o **YouTube Data API v3**
4. Navegue até **Credenciais → Criar Credenciais → Chave de API**
5. Copie sua chave de API e cole na ferramenta

> **Cota:** O nível gratuito fornece 10.000 unidades/dia. Cada pesquisa custa ~100 unidades (~100 pesquisas/dia gratuitamente).

---

## 🚀 Como Usar

1. Cole sua chave de API do YouTube — ela é salva automaticamente para visitas futuras
2. Escolha **Vídeos** ou **Transmissões ao Vivo**
3. Digite o tema de pesquisa
4. *(Opcional)* Selecione uma **Duração de Vídeo** para filtrar pela duração (somente modo Vídeos)
5. *(Opcional)* Marque **Filtrar Shorts** para excluir vídeos com hashtags no título ou descrição
6. *(Opcional)* Ative **Filtrar por Data** e selecione um dia ou intervalo de datas no calendário
7. *(Opcional)* Se uma data for selecionada, defina uma hora de **Início** e **Fim** para filtrar pelo horário do dia
8. Clique em **Encontrar Mais Recentes** (ou **Buscar** quando o filtro de data estiver ativo)
9. Clique em qualquer cartão de resultado para abrir o vídeo
10. Use as amostras de cor à direita para alterar o tema — lembrado entre visitas

---

## 🔒 Privacidade

* Chave de API armazenada localmente no seu navegador (`localStorage`) — nunca enviada a lugar algum, exceto ao Google
* Preferência de tema de cor armazenada localmente no seu navegador
* Sem backend — todo o processamento ocorre no lado do cliente
* As únicas solicitações externas são feitas ao Google YouTube Data API v3

---

## 🛠️ Detalhes Técnicos

| Detalhe | Informação |
|---|---|
| Stack | HTML, CSS, JavaScript puro — sem frameworks |
| Backend | Nenhum — totalmente no lado do cliente |
| API | YouTube Data API v3 |
| Resultados | Até 50, ordenados por data |
| Filtro de data | Usa os parâmetros `publishedAfter` / `publishedBefore` da API |
| Filtro de duração | Usa o parâmetro `videoDuration` da API (`short` / `medium` / `long`) |
| Filtro de Shorts | No lado do cliente — remove qualquer resultado com `#` no título ou descrição |
| Temas | Propriedades personalizadas CSS (`var(--accent)`) trocadas via JavaScript |
| Partículas | Valores negativos de `animation-delay` para que as partículas pré-preencham a tela ao carregar |
| Armazenamento | `localStorage` para chave de API e preferência de tema |

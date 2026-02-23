🌐 [English](README.md) · [Español](README.es.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Français](README.fr.md) · [日本語](README.ja.md)

# 📺 YouTube Search Tool

Uma ferramenta web para pesquisar vídeos e transmissões ao vivo do YouTube em ordem cronológica real usando sua própria chave de API do YouTube. Sem necessidade de login — basta colar sua chave e pesquisar.

## **YouTube Search Tool:** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutorial de Chave de API:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Funcionalidades

* 🔍 Pesquise vídeos ou transmissões ao vivo ordenados pelos mais recentes primeiro
* 📅 Filtrar por data — escolha um único dia ou um intervalo de datas personalizado usando um calendário interativo
* 🕐 Filtro de hora — restrinja os resultados a uma janela de tempo específica dentro da data selecionada (converte automaticamente seu fuso horário local para UTC)
* 🚫 Filtrar Shorts — oculta vídeos que contêm hashtags (`#`) no título ou descrição
* ⏱️ Filtro de duração de vídeo — quando Videos está selecionado, filtre por Curto (<4 min), Médio (4–20 min) ou Longo (20+ min)
* 🎨 8 temas de cores — Roxo, Ciano, Esmeralda, Rosa, Âmbar, Azul, Pink e Lima via painel de amostras
* 💾 Chave de API e tema de cor salvos automaticamente no seu navegador
* ✨ Fundo de partículas animadas, pré-carregado ao abrir
* 🕒 Mostra há quanto tempo cada resultado foi publicado
* 🖱️ Clique em qualquer resultado para abrir o vídeo diretamente

> **Nota:** O modo Transmissões ao vivo é desativado quando o filtro de data está ativo. O filtro de duração de vídeo só está disponível no modo Videos.

---

## 🔑 Como Obter uma Chave de API do YouTube

1. Abra uma nova aba, vá para o [Gmail](https://mail.google.com) e faça login na sua conta Google
2. Navegue até [console.cloud.google.com](https://console.cloud.google.com)
3. Quando solicitado, aceite os **Termos de Serviço** e clique em **Concordo e continuo**
4. No canto superior esquerdo da página, clique em **Selecionar um projeto**, depois no canto superior direito dessa janela clique em **Novo projeto**
5. Dê um nome ao seu projeto e clique em **Criar** — aguarde a conclusão da criação
6. Abra o **Menu de navegação** (as três barras no canto superior esquerdo), role para baixo até **APIs e serviços** e clique em **Biblioteca**
7. Role para baixo até encontrar **YouTube Data API v3** e clique nela
8. Clique em **Ativar** e aguarde a ativação completa
9. No lado esquerdo, clique em **Credenciais**
10. No topo, clique em **Criar credenciais → Chave de API**, depois clique em **Criar**
11. Após a geração da chave, clique na **Chave de API** para abrir suas configurações
12. Em **Restrições de API**, clique em **Restringir chave**, depois clique em **Selecionar APIs**
    - Se a YouTube Data API v3 não aparecer imediatamente, atualize a página
    - Role para baixo, selecione **YouTube Data API v3** e clique em **OK**
13. Clique em **Salvar**
14. Clique em **Mostrar chave**, depois copie sua chave
15. Vá para o [YouTube Search Tool](https://slotchy.github.io/YouTube-Search-Tool), cole sua chave e faça uma pesquisa para confirmar que está funcionando

> **Cota:** O nível gratuito fornece 10.000 unidades/dia. Cada pesquisa custa ~100 unidades (~100 pesquisas/dia gratuitamente).

---

## 🚀 Como Usar

1. Cole sua chave de API do YouTube — salva automaticamente para visitas futuras
2. Escolha **Videos** ou **Livestreams**
3. Digite seu tema de pesquisa
4. *(Opcional)* Selecione uma **Duração de vídeo** para filtrar por duração (somente modo Videos)
5. *(Opcional)* Marque **Filtrar Shorts** para excluir vídeos com hashtags no título ou descrição
6. *(Opcional)* Ative **Filtrar por data** e selecione um dia ou intervalo de datas no calendário
7. *(Opcional)* Se uma data estiver selecionada, defina uma hora de **Início** e **Fim** para filtrar por hora do dia
8. Clique em **Encontrar mais recentes** (ou **Pesquisar** quando o filtro de data estiver ativo)
9. Clique em qualquer cartão de resultado para abrir o vídeo
10. Use as amostras de cor à direita para alterar o tema de destaque — lembrado entre visitas

---

## 🔒 Privacidade

* Chave de API armazenada localmente no seu navegador (`localStorage`) — nunca enviada a nenhum lugar exceto ao Google
* Preferência de tema de cor armazenada localmente no seu navegador
* Sem backend — todo o processamento ocorre no lado do cliente
* As únicas solicitações externas são para a Google YouTube Data API v3

---

## 🛠️ Detalhes Técnicos

| Detalhe | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript puro — sem frameworks |
| Backend | Nenhum — totalmente no lado do cliente |
| API | YouTube Data API v3 |
| Resultados | Até 50, ordenados por data |
| Filtro de data | Usa parâmetros `publishedAfter` / `publishedBefore` da API |
| Filtro de duração | Usa parâmetro `videoDuration` da API (`short` / `medium` / `long`) |
| Filtro de Shorts | No lado do cliente — remove qualquer resultado contendo `#` no título ou descrição |
| Temas | Propriedades personalizadas CSS (`var(--accent)`) trocadas via JavaScript |
| Partículas | Valores negativos de `animation-delay` para que partículas se preencham ao carregar |
| Armazenamento | `localStorage` para chave de API e preferência de tema |

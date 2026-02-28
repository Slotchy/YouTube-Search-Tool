🌐 [English](README.md) · [Español](README.es.md) · [中文](README.zh.md) · [हिन्दी](README.hi.md) · [العربية](README.ar.md) · [Français](README.fr.md) · [日本語](README.ja.md)

# 📺 Ferramenta de Busca YouTube

Uma ferramenta web para buscar vídeos e transmissões ao vivo do YouTube em ordem cronológica real usando sua própria chave API. Sem necessidade de login — basta colar sua chave e buscar.

## **Ferramenta de Busca YouTube:** <https://slotchy.github.io/YouTube-Search-Tool>
## **Tutorial de Chave API:** <https://www.youtube.com/watch?v=eE5WGiwqlFE>

---

## ✨ Recursos

* 🔍 Busque vídeos ou transmissões ao vivo ordenados pelos mais recentes primeiro
* 📅 Filtre por data — escolha um único dia ou um intervalo personalizado usando um calendário interativo
* 🕐 Filtro de hora — restrinja os resultados a uma janela de tempo específica (converte automaticamente seu fuso horário local para UTC)
* 🚫 Filtrar Shorts — oculta vídeos que contêm hashtags (`#`) no título ou descrição
* ⏱️ Filtro de duração — no modo Vídeos, filtre por Curto (<4 min), Médio (4–20 min) ou Longo (20+ min)
* 🎨 8 temas de cor — Roxo, Ciano, Esmeralda, Rosa, Âmbar, Azul, Pink e Lima
* 💾 Chave API e tema de cor salvos automaticamente no seu navegador
* ✨ Fundo de partículas animadas
* 🕒 Mostra o tempo decorrido para cada resultado
* 🖱️ Clique em qualquer resultado para abrir o vídeo diretamente
* ⭐ Favorite qualquer vídeo com um toque — favoritos persistem entre sessões
* 📋 Adicione notas a qualquer vídeo — toque no botão Notes em um cartão para expandir a área de texto, salvo automaticamente
* 📄 Exporte sua sessão completa como arquivo `.md` — inclui todos os resultados de cada busca realizada, com URLs, links de miniaturas, favoritos e notas, sem cota adicional

> **Nota:** O modo Transmissões ao vivo é desativado quando o filtro de data está ativo. O filtro de duração só está disponível no modo Vídeos.

---

## 🔑 Como Obter uma Chave API do YouTube

1. Abra uma nova aba, acesse o [Gmail](https://mail.google.com) e entre na sua conta Google
2. Navegue até [console.cloud.google.com](https://console.cloud.google.com)
3. Aceite os **Termos de Serviço** e clique em **Concordo e continuo**
4. No canto superior esquerdo, clique em **Selecionar projeto**, depois em **Novo projeto**
5. Dê um nome ao projeto e clique em **Criar** — aguarde a conclusão
6. Abra o **Menu de Navegação** (três barras no canto superior esquerdo), vá para **APIs e Serviços → Biblioteca**
7. Role até encontrar **YouTube Data API v3** e clique nele
8. Clique em **Ativar** e aguarde a ativação completa
9. No lado esquerdo, clique em **Credenciais**
10. No topo, clique em **Criar Credenciais → Chave API → Criar**
11. Após gerar a chave, clique na **Chave API** para abrir suas configurações
12. Em **Restrições de API**, clique em **Restringir chave → Selecionar APIs**
    - Se YouTube Data API v3 não aparecer imediatamente, atualize a página
    - Selecione **YouTube Data API v3** e clique em **OK**
13. Clique em **Salvar**
14. Clique em **Mostrar chave**, depois copie-a
15. Acesse a [Ferramenta de Busca YouTube](https://slotchy.github.io/YouTube-Search-Tool), cole sua chave e faça uma busca para confirmar que está funcionando

> **Cota:** O nível gratuito fornece 10.000 unidades/dia. Cada busca custa ~100 unidades (~100 buscas/dia gratuitamente).

---

## 🚀 Uso

1. Cole sua chave API do YouTube — salva automaticamente para visitas futuras
2. Escolha **Vídeos** ou **Ao vivo**
3. Digite seu tema de pesquisa
4. *(Opcional)* Selecione uma **Duração de Vídeo** para filtrar (somente modo Vídeos)
5. *(Opcional)* Marque **Filtrar Shorts** para excluir vídeos com hashtags
6. *(Opcional)* Ative **Filtrar por Data** e selecione um dia ou intervalo no calendário
7. *(Opcional)* Se uma data for selecionada, defina a hora de **Início** e **Fim**
8. Clique em **Encontrar Mais Recentes** (ou **Buscar** com filtro de data ativo)
9. Clique em qualquer cartão de resultado para abrir o vídeo
10. *(Opcional)* Clique em **☆ Favorite** em qualquer cartão para salvá-lo como favorito
11. *(Opcional)* Clique em **📋 Notes** para expandir a área de notas e digitar uma nota
12. Clique em **Export .MD** para baixar sua sessão completa como arquivo Markdown
13. Use os swatches de cor à direita para mudar o tema — lembrado entre visitas

---

## 📄 Exportação

O botão de exportação aparece automaticamente após a primeira busca e acumula resultados durante toda a sessão.

O arquivo `.md` é organizado assim:

* **⭐ Favoritos** — todos os vídeos marcados com estrela, listados primeiro
* **📝 Notas** — todos os vídeos com notas anexadas
* **Todos os Resultados** — cada resultado agrupado por termo de busca

Favoritos e notas persistem no seu navegador entre atualizações de página via `localStorage`.

---

## 🔒 Privacidade

* Chave API armazenada localmente no seu navegador (`localStorage`) — nunca enviada a nenhum lugar exceto o Google
* Tema de cor, favoritos e notas armazenados localmente
* Sem backend — todo o processamento acontece no lado do cliente
* As únicas requisições externas são para a YouTube Data API v3 do Google

---

## 🛠️ Detalhes Técnicos

| Detalhe | Info |
| --- | --- |
| Stack | HTML, CSS, JavaScript puro — sem frameworks |
| Backend | Nenhum — totalmente no lado do cliente |
| API | YouTube Data API v3 |
| Resultados | Até 50 por busca, ordenados por data |
| Filtro de data | Usa parâmetros `publishedAfter` / `publishedBefore` |
| Filtro de duração | Usa o parâmetro `videoDuration` |
| Filtro de Shorts | No lado do cliente — remove resultados com `#` no título ou descrição |
| Temas | Propriedades CSS personalizadas trocadas via JavaScript |
| Partículas | Valores negativos de `animation-delay` para pré-popular a tela ao carregar |
| Armazenamento | `localStorage` para chave API, tema, favoritos e notas |
| Exportação | Download Blob no lado do cliente — sem chamadas API adicionais |

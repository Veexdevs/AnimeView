# AnimeView

Um catálogo de descoberta de animes e mangás com visual inspirado em plataformas de streaming. Os dados vêm da API pública [Jikan](https://jikan.moe/), não oficialmente ligada ao MyAnimeList. O catálogo é consultado ao abrir o aplicativo, incluindo a temporada atual; novos títulos aparecem conforme disponibilizados pela API. Pesquise, veja detalhes e salve favoritos no dispositivo.

**O AnimeView não hospeda nem fornece reprodução de vídeos ou leitura de mangás.** Os links levam à página informativa do MyAnimeList. O site de referência não foi usado como fonte de código ou conteúdo. A disponibilidade e os limites da API são responsabilidade do serviço externo; sinopses podem estar em inglês. Os favoritos ficam no armazenamento local, sem sincronização entre dispositivos.

## Executar

Requisitos: Node.js 20 ou superior.

```sh
npm ci
npm run dev
```

Para gerar o site: `npm run build`. Publique a pasta `dist` em qualquer hospedagem estática HTTPS. Para desktop local, execute `npm run build` e `npm run desktop`.

## Builds no GitHub Actions

O workflow gera artefatos para download na página da execução: site estático, APK Android **debug**, instalador Windows e IPA iOS **não assinado**. O APK debug e o executável não são assinados para distribuição comercial. O IPA não assinado não pode ser instalado normalmente: distribuição em aparelhos iOS exige conta Apple Developer, certificados, provisioning profiles e assinatura apropriados. Para publicar nas lojas, configure assinatura e identidade próprias. Os builds dependem dos ambientes e ferramentas disponibilizados pelos runners do GitHub.

Para publicar no GitHub Pages, escolha **GitHub Actions** como origem em Settings → Pages e execute manualmente o workflow “Publicar site no GitHub Pages” na branch desejada.

### Disponibilidade do catálogo

Cada seleção da Jikan é carregada separadamente, para que uma falha não esconda as demais. Se a API estiver indisponível, o aplicativo mostra uma seleção local de metadados e informa que está no modo salvo. A busca também consulta essa seleção enquanto tenta a API. As capas continuam dependendo dos servidores externos; quando não carregam, o título é exibido no lugar. A seleção local foi preparada a partir dos dados públicos de [Ani-Mangalist](https://github.com/edivaldolluisb/animeData) (MIT) e não representa novidades em tempo real.

### Imagens

A interface usa imagens promocionais de obras de terceiros como referência visual. Fontes: [Attack on Titan](https://www.cbr.com/attack-on-titan-best-official-posters/), [Naruto](https://displate.com/licensed/naruto), [One Piece](https://www.cbr.com/one-piece-luffy-toei-official-artwork-new-release/), [Jujutsu Kaisen](https://amazon.com/Jujutsu-Kaisen-Visual-Unframed-Version/dp/B0FWKV1KRL), [Demon Slayer](https://fr.pinterest.com/pin/demon-slayer-key-visual-1-poster--253397916526569550), [Solo Leveling](https://www.reddit.com/r/sololeveling/comments/1fhv5gl/official_solo_leveling_s2_key_visual/) e [Blue Lock](https://www.reddit.com/r/BlueLock/comments/1ev4psn/blue_lock_season_2_key_visual/). Os direitos pertencem aos respectivos titulares; verifique as permissões antes de distribuir o aplicativo.

Imagens adicionais usadas no visual: [Attack on Titan](https://wall.alphacoders.com/big.php?i=937865) e [One Piece](https://wallpapers.com/picture/anime-pictures-o1vi5ds9at18b66x.html). Os direitos pertencem aos respectivos titulares; verifique as permissões antes de distribuir.

Imagem da seção Explorar: [Live Wallpapers](https://livewallpapers.com/wallpapers/anime-character-red-eye-wallpaper-1.html). Verifique as permissões dos titulares antes de distribuir.

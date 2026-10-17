# Gunship Strike

Jogo de helicóptero de ataque no navegador, no estilo *Drone Strike: Gunship War*. Pilote um helicóptero armado, ou assuma a minigun da porta, e elimine alvos terrestres em ondas: infantaria, picapes armadas, tanques, baterias antiaéreas e lançadores SAM, todos revidando.

**Jogar:** https://azamba.github.io/gunship-strike/

Tudo fica num único `index.html` (Three.js via CDN), sem build. Também dá para abrir o arquivo direto no navegador.

## Recursos

- **Quatro aeronaves:**
  - **Mi-24 Hind:** canhão 30mm + minigun, foguetes, mísseis e minigun de porta.
  - **UH-60 Black Hawk:** duas miniguns de porta. No online leva piloto + 2 atiradores.
  - **AH-64 Apache:** ágil, com 16 mísseis, mas pouca blindagem.
  - **AC-130 Spectre:** canhoneira em órbita alta com gatling 25mm, Bofors 40mm e obuseiro 105mm. A mira (câmera estabilizada no solo) alcança o mapa todo e a órbita segue o ponto mirado.
- **Loja entre ondas:** gaste os pontos em blindagem, munição, refrigeração das armas, ogivas mais fortes, flares extras e motor.
- **Atirador de porta:** visão de dentro da cabine, atrás de uma minigun M134, enquanto o helicóptero orbita sozinho o alvo.
- **Multiplayer cooperativo P2P** (WebRTC/PeerJS): crie uma partida e passe o código. Cada jogador pode pilotar o próprio helicóptero ou embarcar como atirador no helicóptero de outro.
- **Helicópteros inimigos:** chegam como reforço no meio das ondas, cercam você atirando com metralhadora, foguetes e mísseis ar-ar, e caem girando em chamas quando abatidos.
- **Chefe a cada 5 ondas:** um gunship pesado e blindado com escolta, com barra de vida no topo da tela.
- **Três mapas:**
  - **Deserto:** vilas de adobe e dunas.
  - **Cidade portuária:** prédios altos, pátios de contêineres destrutíveis, guindastes, navios que afundam e lanchas armadas patrulhando o mar.
  - **Montanhas:** vales com vilas, pinheiros e picos nevados. O relevo bloqueia a linha de tiro, então dá para se esconder atrás dos morros.
- **Modo escolta de comboio:** proteja os blindados aliados pelas estradas até o destino. Eles param quando são emboscados e revidam, mas precisam da sua ajuda.
- **Modo defesa da base:** hordas de insurgentes, picapes armadas, caminhões que desembarcam tropas, tanques e carros-bomba avançam de várias direções contra a base aliada. Se ela cair, a missão fracassa. A cada onda vencida, a base recebe 10% de reparo.
- Ciclo dia, entardecer, noite e amanhecer: missões noturnas com visão térmica, holofote, janelas acesas e estrelas.
- Gráficos: iluminação PBR, bloom, oclusão ambiente (GTAO), distorção de calor, partículas de fogo e fumaça, prédios destrutíveis.
- Áudio sintetizado com WebAudio.
- **Celular e tablet:** analógico para voar, arraste na tela para mirar, botões de fogo, zoom, arma, flares e outros. Jogue na horizontal.

## Controles

| Tecla | Ação |
|---|---|
| Mouse | Mirar e girar o helicóptero |
| W A S D | Voar |
| Espaço / Shift (ou C) | Subir / descer |
| Botão esquerdo | Atirar |
| Botão direito | Zoom |
| 1 2 3 / roda | Canhão + minigun · Foguetes · Mísseis |
| V | Piloto ↔ atirador de porta (piloto automático em órbita) |
| E | (Atirador / AC-130) recentrar a órbita onde você mira |
| B | (Online) embarcar como atirador no helicóptero de outro jogador |
| F | Flares (desviam mísseis SAM) |
| T | Visão térmica |
| L | Holofote |
| N | Avançar horário (no online, só o anfitrião) |
| G | Alternar qualidade gráfica / desempenho |
| K | Abrir a loja (entre as ondas) |
| Esc | Pausar (no online, a partida continua) |

## Mapas e modos

No menu, escolha a **AERONAVE**, o **MAPA** (Deserto, Cidade portuária ou Montanhas) e o **MODO** (Ondas, Defesa da base ou Escolta). Também dá para abrir direto pelo link, por exemplo `?map=porto&mode=defesa`.

## Multiplayer

1. Um jogador escolhe mapa e modo, clica em **CRIAR PARTIDA ONLINE** e passa o código de 5 letras (ou o link) para os amigos. O próprio código já leva o mapa e o modo.
2. Os amigos digitam o código e clicam em **ENTRAR**.
3. Cada um escolhe a aeronave e clica em **DECOLAR**, ou em **ATIRADOR DE \<nome\>** para ir na porta de outro jogador. O Black Hawk tem duas portas.

O anfitrião controla os inimigos, as ondas e o dano. Se ele sair, a partida termina. É preciso internet, porque o servidor público do PeerJS faz o primeiro contato entre os navegadores.

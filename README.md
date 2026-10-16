# Gunship Strike

Jogo de helicóptero de ataque no navegador, no estilo *Drone Strike: Gunship War*. Pilote um helicóptero armado, ou assuma a minigun da porta, e elimine alvos terrestres em ondas: infantaria, picapes armadas, tanques, baterias antiaéreas e lançadores SAM, todos revidando.

**Jogar:** https://azamba.github.io/gunship-strike/

Tudo fica num único `index.html` (Three.js via CDN), sem build. Também dá para abrir o arquivo direto no navegador.

## Recursos

- Helicóptero no estilo Mi-24 com canhão 30mm e minigun no nariz, foguetes Hydra e mísseis Hellfire guiados.
- **Atirador de porta:** visão de dentro da cabine, atrás de uma minigun M134, enquanto o helicóptero orbita sozinho o alvo.
- **Multiplayer cooperativo P2P** (WebRTC/PeerJS): crie uma partida e passe o código. Cada jogador pode pilotar o próprio helicóptero ou embarcar como atirador no helicóptero de outro.
- **Helicópteros inimigos:** chegam como reforço no meio das ondas, cercam você atirando com metralhadora, foguetes e mísseis ar-ar, e caem girando em chamas quando abatidos.
- **Chefe a cada 5 ondas:** um gunship pesado e blindado com escolta, com barra de vida no topo da tela.
- Ciclo dia, entardecer, noite e amanhecer: missões noturnas com visão térmica, holofote, janelas acesas e estrelas.
- Gráficos: iluminação PBR, bloom, oclusão ambiente (GTAO), distorção de calor, partículas de fogo e fumaça, prédios destrutíveis.
- Áudio sintetizado com WebAudio.

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
| E | (Atirador) recentrar a órbita onde você mira |
| B | (Online) embarcar como atirador no helicóptero de outro jogador |
| F | Flares (desviam mísseis SAM) |
| T | Visão térmica |
| L | Holofote |
| N | Avançar horário (no online, só o anfitrião) |
| G | Alternar qualidade gráfica / desempenho |
| Esc | Pausar (no online, a partida continua) |

## Multiplayer

1. Um jogador clica em **CRIAR PARTIDA ONLINE** e passa o código de 5 letras (ou o link) para os amigos.
2. Os amigos digitam o código e clicam em **ENTRAR**.
3. Cada um escolhe **DECOLAR** (helicóptero próprio) ou **ATIRADOR DE \<nome\>**.

O anfitrião controla os inimigos, as ondas e o dano. Se ele sair, a partida termina. É preciso internet, porque o servidor público do PeerJS faz o primeiro contato entre os navegadores.

# Sampa Burger — site 2026

Site estático de página única. Sem build, sem dependências: abra `index.html`.

```bash
cd ~/Documents/sampa-burger-site && python3 -m http.server 4178
```

## Estrutura
- `index.html` — página inteira (CSS e JS inline)
- `assets/img/` — fotos oficiais dos produtos (do cardápio digital da marca) e o logo
- `assets/img/ig/` — miniaturas dos posts do Instagram, nomeadas `NN-<id do post>.jpg`

## Dados que vêm da operação real
- Cardápio e descrições dos lanches: cardápio digital da unidade Chácara Santo Antônio (Verbo Divino)
- Horários por unidade e WhatsApps de reserva: site atual + Linktree oficial
- Cor da marca: `#9A1B24`, extraída do logo

## Decisões de design
- Base clara (branco + osso) com o vermelho `#9A1B24` em blocos inteiros: hero, Obelisco, Clube e rodapé
- Home mostra só os 5 burgers mais pedidos — todos com foto real. O resto do cardápio fica no cardápio digital
- O cardápio da home é vitrine, não balcão: sem preço. Preço só no cardápio digital e no iFood, onde a unidade mantém atualizado
- O status "aberto agora" recalcula no load, a cada minuto e quando a aba volta ao primeiro plano
- Preto só aparece como cor de texto

## A área de Instagram é um retrato, não um feed ao vivo
As miniaturas foram baixadas do perfil público em 03/10/2026 e ficam no repositório.
Isso foi de propósito: a URL que o Instagram serve no CDN é assinada e expira em
cerca de um dia, então apontar direto para lá quebraria o site sozinho.

Cada tile leva para o post real no Instagram, então o conteúdo continua acessível.
Para atualizar, baixe as novas miniaturas em `assets/img/ig/` e troque os 8 blocos
`<a class="ig-tile">`. Os dois posts de "Dia do Cliente 15/09" foram deixados de fora
de propósito: promoção datada envelhece mal em página estática.

Para virar feed de verdade (atualiza sozinho), as opções são:
- Um serviço de widget (Behold, SnapWidget, Elfsight) — exige conectar a conta
- A API do Instagram com Instagram Login, via app no Meta for Developers — exige
  que a marca autorize o app. A Basic Display API foi descontinuada em 2024.

## Conferir antes de publicar
- Os "5 mais pedidos" foram escolhidos por critério editorial (clássico, salada, bacon, duplo, assinatura), não por dado de venda — trocar pela lista real do PDV
- Endereços de Tatuapé, Santana e Taboão da Serra vieram de busca pública — confirmar com a operação
- Carapicuíba está sem número (só "região do Calçadão") — faltou fonte confiável
- Horários estão gravados em `data-hours` em cada card de loja; mudou o funcionamento, edite ali
- O status não conhece feriado nem fechamento extraordinário — só o horário fixo
- "260 mil Sampeiros" é o número de seguidores em 03/10/2026 — revisar de tempos em tempos

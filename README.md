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

## Próximo passo: seção dos donos (pendente)

A pesquisa já foi feita, falta construir.

**Quem são**
- Giulio Mirante — [@giuliomirante](https://www.instagram.com/giuliomirante/), 64,3 mil seguidores.
  Bio: "@sampaburgeroficial (13 unidades) · Eleita Top 3 Melhor de São Paulo ·
  Sampa, Rio, Minas e aonde você quiser abrir"
- Gian Mirante — [@gianmirante](https://www.instagram.com/gianmirante/), 13,3 mil seguidores.
  Bio: "@sampaburgeroficial · @santowich.burger · @gruposuburbanos · 17 lojas SP/RJ"

**Fotos**
- `assets/img/giulio.jpg` (740×740) já está no projeto — é a foto da antiga seção
  "Especialistas em: Qualidade" do site atual. Não está sendo usada em lugar nenhum ainda.
- Falta uma foto do Gian. As fotos de perfil do Instagram saem em 150×150 e o CDN
  bloqueia download fora do navegador. O caminho é pedir as fotos à operação.

**Contexto do Grupo Suburbanos** (gruposuburbanos.com.br)
- Nasceu em 2022, da aquisição das marcas Santowich e Rutz
- Marcas: Suburbanos Pizza, Sampa Burger, Santowich — mais de 50 unidades em RJ, SP, MG, DF, ES, SC, PR
- Franquia Sampa: investimento mínimo R$ 250 mil, faturamento médio mensal R$ 230 mil,
  margem líquida de 12% a 15%. Por modelo/ano: dark kitchen R$ 1,6 mi · delivery e retirada
  R$ 1,75 mi · salão com delivery R$ 2 mi · mega loja R$ 3,9 mi

## ATENÇÃO: quantas unidades a Sampa tem?

Três fontes, três números — o site usa 11 e pode estar desatualizado.

| Fonte | Número |
|---|---|
| Site atual (lojas nomeadas: 6 SP + 5 RJ) | 11 |
| Bio do @giuliomirante, sobre a Sampa | 13 unidades |
| Bio do @gianmirante | 17 lojas SP/RJ (provavelmente somando a Santowich) |

A seção de franquia do site diz "11 unidades em operação" e a de lojas lista 11 por nome.
Se o número certo for 13, faltam dados de 2 unidades (endereço, horário, WhatsApp).
Confirmar com a operação antes de mudar.

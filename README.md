# Sampa Burger — site 2026

Site estático de página única. Sem build, sem dependências: abra `index.html`.

```bash
cd ~/Documents/sampa-burger-site && python3 -m http.server 4178
```

## Estrutura
- `index.html` — página inteira (CSS e JS inline)
- `assets/img/` — fotos oficiais dos produtos (do cardápio digital da marca) e o logo

## Dados que vêm da operação real
- Cardápio, descrições e preços: cardápio digital da unidade Chácara Santo Antônio (Verbo Divino)
- Horários por unidade e WhatsApps de reserva: site atual + Linktree oficial
- Cor da marca: `#9A1B24`, extraída do logo

## Decisões de design
- Base clara (branco + osso) com o vermelho `#9A1B24` em blocos inteiros: hero, Obelisco, Clube e rodapé
- Home mostra só os 5 burgers mais pedidos — todos com foto real. O resto do cardápio fica no cardápio digital
- Preto só aparece como cor de texto

## Conferir antes de publicar
- Os "5 mais pedidos" foram escolhidos por critério editorial (clássico, salada, bacon, duplo, assinatura), não por dado de venda — trocar pela lista real do PDV
- Endereços de Tatuapé, Santana e Taboão da Serra vieram de busca pública — confirmar com a operação
- Carapicuíba está sem número (só "região do Calçadão") — faltou fonte confiável
- Preços variam por unidade e no delivery; o rodapé do cardápio já avisa isso

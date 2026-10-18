# Poker HUD pessoal (PokerStars)

Notebook Jupyter que lê os *hand histories* do PokerStars (`.txt`) e calcula estatísticas
por jogador, sem precisar de software pago.

## Estatísticas

- **Pré-flop:** VPIP, PFR, RFI, 3Bet, Fold to 3Bet, 4Bet, Fold to 4Bet, steal (ATS), fold to steal, resteal
- **Cbet:** flop, turn e river, além de fold to cbet e raise vs cbet
- **Pós-flop:** agressão (AF), WTSD, Win at Showdown, W$WSF
- **Por posição:** UTG, MP, CO, BTN, SB e BB
- **Mesa atual:** detecta a mesa ativa e mostra o HUD dos adversários

## Como usar

```bash
git clone https://github.com/vitorpigatto/poker-hud.git
cd poker-hud
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab poker_hud.ipynb
```

1. Rode as células em ordem. Os passos 1 a 4 usam mãos de exemplo para testar o parser.
2. No **Passo 6**, troque `HAND_HISTORY_FOLDER` e `HERO_NAME` pelo caminho da sua pasta de
   hand history e pelo seu nick.
3. As estatísticas ficam em cache em `poker_stats_db.json`, então só mãos novas são lidas a cada execução.
   Se mudar a lógica de uma stat, aumente `SCHEMA_VERSION` para recalcular tudo.

## Privacidade

Hand histories e o cache `poker_stats_db.json` contêm nomes de outros jogadores e estão no
`.gitignore`. Não faça commit deles.

## Observação

Confira a política do PokerStars sobre ferramentas de terceiros antes de usar o HUD durante as sessões.

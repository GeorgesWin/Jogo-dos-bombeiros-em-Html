# Jogo-dos-bombeiros-em-Html
Jogo de bombeiros em html para trilhas 
Mini jogo de aventura feito apenas com HTML (e duas regras de CSS para mostrar um cômodo por vez).

## Objetivo

Você é um bravo bombeiro. Sua missão é encontrar o cômodo que ainda tem uma pessoa nesta casa em chamas! O jogo começa na rua e termina quando você entra no **Quarto 2**.

O jogo não dá dicas: a cada rodada ele mostra apenas onde você está e as opções de caminho disponíveis.

## Como jogar

1. Abra o arquivo `index.html` no navegador (clique duas vezes nele).
2. Clique em **Começar o jogo**.
3. Escolha uma opção a cada rodada para navegar pela casa.
4. Ao entrar no cômodo final, o jogo mostra a mensagem de sucesso.

Não precisa instalar nada nem ter internet.

## Mapa da casa

```
              ┌──────────────── cozinha ────────────────┐
              │                                         │
  corredor    │    [porta]                [porta]       │
     │        ├──── quarto 2 (destino) ─┬── banheiro ───┤
     │        │                         │               │
  sala ───────┼─────────[porta]──────── quarto 1        │
     │                                       │ [janela]
  [porta]                                    │
     └───────────────── rua ─────────────────┘
```

### Conexões

| Cômodo    | Opções                                                       |
|-----------|--------------------------------------------------------------|
| Rua       | porta → sala · janela → quarto 1                             |
| Sala      | porta da frente → rua · porta → quarto 1 · corredor          |
| Quarto 1  | porta → sala · janela → rua                                  |
| Corredor  | sala · cozinha                                               |
| Cozinha   | corredor · porta da esquerda → quarto 2 · porta da direita → banheiro |
| Banheiro  | porta → cozinha                                              |
| Quarto 2  | **fim do jogo** (sucesso)                                    |

## Como o código funciona

- Cada cômodo é uma `<section>` com um `id` (por exemplo, `id="sala"`).
- Cada opção é um link para o `id` de outro cômodo (por exemplo, `<a href="#sala">`).
- O CSS esconde todas as seções e mostra só a que está no endereço da página (`section:target`).

## Como personalizar

- **Mudar o cômodo final:** coloque a mensagem de sucesso em outra `<section>` e aponte os links para ela.
- **Adicionar um cômodo:** copie uma `<section>`, troque o `id`, o título e as opções, e crie links para ela nos cômodos vizinhos.
- **Mudar o tema:** troque os textos e títulos (por exemplo, uma caça ao tesouro).

## Estrutura

```
heroi-das-chamas/
├── index.html   # o jogo completo
└── README.md    # este arquivo
```


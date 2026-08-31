# Pacote de Design: Client Telecom

Nível 1, jornada única de 6 segundos. Escrito antes da construção, consumido inteiro pela Fase 8.
Cada linha voltada ao visitante embarca ao pé da letra.

## 1. A premissa da marca

**A luz não para.**

Numa rede óptica o sinal é luz atravessando vidro, e todo o valor está em ela nunca parar. Os seis produtos da Client são seis formas de manter essa luz inteira: o monitoramento vigia, o link dedicado impede que dividam, a VPN MPLS protege no caminho, o anti-DDoS defende, o trânsito IP dá estrada própria, o transporte dá largura. O site inteiro ensina e vende essa ideia. Seção que não serve a premissa não entra.

O contraponto que a pesquisa entregou: no mercado brasileiro a luz para o tempo todo, e o que trava a venda não é preço, é descrença. "Contratei SLA de 4 horas e na verdade é de 24." O site responde isso de frente.

## 2. A paleta como tokens CSS

Amostrada da filmagem aprovada, pixel a pixel. Os escuros vêm dos fundos mais frequentes do quadro; o acento vem dos filamentos mais luminosos.

```css
:root{
  --canvas:#060b18;        /* fundo da página, navy quase preto, nunca preto puro */
  --canvas-deep:#03060f;   /* poços de profundidade entre seções */
  --panel:#0c1426;         /* cartões e superfícies elevadas */
  --line:#16233d;          /* divisórias e bordas quietas */
  --accent:#1e9be8;        /* o CTA e a ênfase rara (o filamento aceso) */
  --accent-hover:#45b4f2;
  --accent-muted:#0d4f80;  /* nível de sussurro: bordas, brilhos, partículas */
  --brand-navy:#23417a;    /* o azul do próprio logotipo, tom de apoio */
  --text-primary:#e8f0fa;
  --text-secondary:#8fa6c4;
}
```

Contraste medido, não chutado:
- `--text-primary` sobre `--canvas`: **16,7:1**
- `--text-secondary` sobre `--canvas`: **7,7:1**
- `--accent` sobre `--canvas`: **6,3:1**
- Texto `#04101f` sobre botão `--accent`: **6,1:1**

## 3. O trio de fontes

- **Display: Archivo**, pesos 600 e 700. Grotesca industrial de x alto, que ecoa a própria letra do logotipo (bold, ligeiramente condensada).
- **Texto: Instrument Sans**, pesos 400 e 500. Quieta, moderna, boa em tamanho pequeno.
- **Mono: JetBrains Mono**, pesos 400 e 500. Para rótulos técnicos: portas, Gb, ASN, janelas de SLA. É a voz do mundo de engenharia de rede.

Nenhuma é Inter nem Roboto. Só os pesos em uso são carregados, com `preconnect`.

## 4. O mapa de faixas

Hero de 480vh. Intervalos são pontos de partida, validados depois pelo teste de flick.

| Faixa | Intervalo | Momento da filmagem | Texto (ao pé da letra) | Entrada |
|---|---|---|---|---|
| 1 | 0.00 a 0.20 | a câmera se aproxima da marca acesa | **"A luz não para."** / "Rede óptica própria, vigiada segundo a segundo." | subida palavra por palavra, já montada no carregamento |
| 2 | 0.24 a 0.46 | a travessia do anel: estouro de luz e batida de desfoque | **"Sua banda é sua."** / "Link dedicado não divide velocidade com ninguém." | soco de palavra com overshoot, ecoando o impacto da passagem |
| 3 | 0.50 a 0.72 | descida pelo corredor de fibras | **"De 100 Mb a 40 Gb."** / "A porta cresce junto com a sua operação." | deriva para baixo, ecoando a queda |
| 4 | 0.76 a 1.00 | o plano de luz assentando | **"23 anos no ar."** / "E um telefone que alguém atende." / [Quero uma proposta] | subida palavra por palavra em três chegadas |

Faixa 1 abre assentada (rampa de carregamento que passa o bastão para o scroll). Faixa 4 pula a suavização de saída.

Texto vive no terço esquerdo e na metade superior, que é onde a filmagem deixou espaço calmo. A faixa da ação fica livre.

## 5. O bloco de texto do hero estático

Para celular e movimento reduzido, composto sobre o pôster:

- Título: **"A luz não para."**
- Subtítulo: "Rede óptica própria, 23 anos, e um telefone que alguém atende."
- CTA: **"Quero uma proposta"**

## 6. O esboço abaixo da dobra

Tudo afunila para UMA âncora: `#proposta`, que abre o WhatsApp (16) 99715-3724 com a mensagem pronta.

**a) O assentamento.** A premissa dita simples.
> "Fibra é luz dentro de vidro. Enquanto ela não para, sua empresa não para. Todo o resto do que a gente faz existe para isso."

**b) O que a gente mais ouve.** As dores reais, nas palavras dos próprios compradores, tiradas de reclamações públicas do setor. Cinco linhas em citação, sem nomear concorrente:
> "Contratei SLA de 4 horas. Na verdade era 24."
> "Contratei 4 Mb. Mede 2 Mb."
> "Já abri mais de dez chamados."
> "Caiu sexta. Voltou domingo."
> "Pedi upgrade. Esperei nove meses."

Fecho da seção: "Nenhuma dessas frases é sobre a Client. E o site inteiro abaixo existe para você conferir isso."

**c) Os seis produtos.** Grade de seis, cada um com o motivo real reescrito curto. Tratamento igual nos seis.

1. **Link dedicado** — "Banda exclusiva. 100% do que você contratou, o tempo todo, sem dividir com ninguém."
2. **Trânsito IP** — "ASN e IP seus. Estrada própria para as principais rotas da internet."
3. **VPN MPLS/IP** — "Suas unidades conversando numa rede privada, com os dados protegidos no caminho inteiro."
4. **Anti-DDoS** — "Filtra o ataque, mantém o DNS de pé. Você continua trabalhando."
5. **Transporte** — "Portas de 100 Mb a 40 Gb, com SLA e suporte dedicado."
6. **Monitoramento** — "A rede olhada em cada detalhe, o tempo todo. A falha aparece antes de você sentir."

**d) O momento interativo.** Título: "Segure para manter a luz passando."
O visitante pressiona e segura; um pulso corre pelo fio de luz da página. Soltar cedo faz o brilho descer suave, nunca estala para zero. Completar acende a seção em sequência e revela a linha: "É isso que a gente faz o dia inteiro. Só que sem você precisar segurar."
Movimento reduzido recebe o estado final direto, sem segurar.

**e) Como funciona.** Três passos, tratamento idêntico, cada um com motivo vetorial desenhado (nenhum com foto, para não criar assimetria):
1. **Diagnóstico** — "A gente escuta o que sua operação precisa de verdade."
2. **Proposta** — "Capacidade, prazo e SLA por escrito, antes de assinar."
3. **Instalação** — "Data marcada e cumprida. Depois, monitoramento desde o primeiro minuto."

**f) Onde a Client se conecta.** Parceiros: Equinix, AWS, Microsoft Azure, Google Cloud, Oracle, Alibaba Cloud. Fileira de rótulos em mono, sem logotipo de terceiro embarcado.

**g) FAQ.** Responde as objeções reais da pesquisa:
- "O SLA de vocês é o mesmo do contrato?"
- "Quanto tempo leva da assinatura até o link no ar?"
- "E se cair de madrugada ou no fim de semana?"
- "Vocês entregam a velocidade que eu contratei?"
- "Preciso ter ASN próprio para contratar trânsito IP?"
- "Atendem a minha cidade?"

As respostas ficam para a construção, escritas simples e sem promessa que a empresa não tenha dado. Onde eu não souber o número real, a resposta diz o que a Client faz, não inventa prazo.

**h) A chamada final.** Título: "Conta o que sua operação precisa." Subtítulo: "A gente responde com capacidade, prazo e SLA. Por escrito."
Formulário: nome, empresa, cidade, o que precisa. Botão: **"Falar no WhatsApp"**. Ele monta a mensagem e abre o WhatsApp (16) 99715-3724. O estado de sucesso diz a verdade: "Abrindo o WhatsApp com sua mensagem pronta." Telefone 0800 200 7575 fica visível ao lado, para quem prefere ligar.

**i) Rodapé.** Símbolo em SVG, os seis produtos, 0800, WhatsApp, e a linha de direitos. A marca é real, então não há declaração de marca fictícia.

## 7. O plano da camada vetorial

**O elemento assinatura: o fio de luz.** Um único traço SVG contínuo que desce a página inteira, do hero até o rodapé, desenhando-se sozinho conforme o visitante rola. Ele engrossa ao entrar em cada seção, se ramifica em seis nos produtos, é o fio que o visitante segura no momento interativo, e termina entrando no botão da chamada final. Nunca se rompe, porque a premissa é essa. Se ele fosse removido, a página mudaria de verdade.

Além dele:
- Partículas em nível de sussurro na camada de ambiente fixa, ciclo de 60s ou mais.
- Divisórias que são traços do mesmo fio, não linhas retas de estoque.
- Um elemento vivo por seção, discreto, pausado fora da tela e em aba escondida.

Tudo honra movimento reduzido: estados finais mostrados, motores parados.

## 8. A lista de engenharia

O padrão completo de `pipeline-scrub.md`, nomeado para a construção não lembrar pela metade: busca do vídeo como Blob com anel de carregamento e watchdog de 20s; interpolação normalizada por dt num loop rAF que descansa; seeks travados com saída de deadlock no `error`; escritas de DOM só na mudança; ritmo de faixas em vh com teste de flick; sistema de legibilidade de quatro camadas com auditoria de pior quadro em 3.5:1; os cinco portões do hero estático batendo caractere por caractere entre CSS e JS, com listeners de mudança; página completa e bonita sem o vídeo; `overflow-x: clip` nos dois; movimento reduzido honrado ao vivo nas duas direções.

Arquitetura: um `index.html` mais `assets/`. HTML puro, CSS e JavaScript vanilla. Sem framework, sem build, sem npm.

## 9. A linha do gate de texto

Cada linha acima embarca ao pé da letra. Antes de o usuário ver qualquer coisa, a página construída passa o gate: zero travessões, zero palavras de estoque (alavancar, robusto, empoderar, destravar, acionável, orientado a dados, soluções, sinergia, escalável), mais a varredura do corpo por sinais de IA. Os dispositivos deliberados deste pacote ficam: o staccato das cinco citações de dor, e o trio "Diagnóstico. Proposta. Instalação." são ofício, escolhidos aqui de propósito.

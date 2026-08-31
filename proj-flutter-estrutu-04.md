Num projeto Flutter, a maior parte das pastas é gerada automaticamente pela ferramenta — são estruturas de suporte para cada plataforma (Android, iOS, web) e arquivos de compilação. O trabalho real da equipe fica concentrado em um lugar só: a pasta lib/. É ali que vive praticamente todo o código que define o que o ROTA é e faz. 


Link do arquivo: https://fiapcom-my.sharepoint.com/:u:/g/personal/rm564693_fiap_com_br/IQB85V0P_kzeR7YWWez_aGBmAaS0es4eGvJ5uHPz5JMxC4w?e=h4gqBk


**Árvore de pastas**
```
rota_app/                         raiz do projeto
│
├── lib/                          ★ o coração — todo o código Dart do app
│   ├── main.dart                 ponto de entrada; inicia o app
│   ├── core/                     configurações base compartilhadas
│   │   └── app_colors.dart       paleta central de cores
│   ├── screens/                  as telas inteiras do app
│   │   ├── splash_screen.dart    abertura com o logo ROTA
│   │   └── dashboard_screen.dart tela principal (carga + entregas)
│   └── widgets/                  peças reutilizáveis das telas
│       ├── week_card.dart        barra de carga de uma semana
│       ├── task_card.dart        card de uma entrega
│       ├── priority_tag.dart     etiqueta de prioridade
│       ├── add_task_modal.dart   modal de cadastro de entrega
│       ├── custom_button.dart    botão padrão reutilizável
│       └── custom_input.dart     campo de texto reutilizável
│
├── assets/                       ★ imagens do app
│   ├── logoRota.png              logo escrito ROTA
│   └── iconeRota.png             ícone (capelo)
│
├── pubspec.yaml                  ★ config + lista de dependências
├── pubspec.lock                  versões exatas travadas (auto)
├── analysis_options.yaml         regras de qualidade do código
├── README.md                     apresentação do repositório
├── .gitignore                    o que NÃO sobe pro Git
│
├── android/  ios/  web/          plataformas alvo (auto-geradas)
├── windows/  macos/  linux/      plataformas desktop (não usadas)
├── test/                         espaço para testes automatizados
├── build/  .dart_tool/           gerados na compilação (ignorados)
└── .idea/  .metadata  rota_app.iml   config do editor/ferramenta

**★ = criado pela equipe | demais itens gerados pelo Flutter**
```

**A Pasta Lib/**

Dentro de lib/, a organização segue uma separação por responsabilidade, que mantém o projeto limpo e fácil de crescer.

O arquivo main.dart é a porta de entrada do aplicativo. É o primeiro trecho de código que o Flutter executa: ele liga o app e determina qual tela será exibida primeiro. Todo projeto Flutter começa por aqui.

A pasta core/ guarda o que é compartilhado por todo o aplicativo — decisões centrais que várias telas precisam consultar. Hoje ela contém o app_colors.dart, que define a paleta de cores do ROTA em um único lugar. Centralizar as cores assim significa que, para mudar a identidade visual, basta editar um arquivo, e a mudança se propaga por todo o app.

A pasta screens/ contém as telas completas. Cada arquivo aqui representa uma página inteira que o usuário vê: a splash_screen.dart é a tela de abertura, exibida por alguns segundos com o logo ROTA; a dashboard_screen.dart é a tela principal, onde aparecem a carga acumulada das semanas e a lista de próximas entregas.

A pasta widgets/ contém as peças reutilizáveis com que as telas são montadas. Em vez de uma tela desenhar tudo do zero, ela combina componentes menores já prontos. Aqui estão o week_card.dart (a barra que mostra a carga de uma semana), o task_card.dart (o card de uma entrega), o priority_tag.dart (a etiqueta de prioridade), o add_task_modal.dart (a janela de cadastro de uma nova entrega), além do custom_button.dart e do custom_input.dart, que são o botão e o campo de texto padrão usados em vários pontos.

Essa divisão entre telas e widgets é uma boa prática importante: uma tela não repete código, ela reaproveita peças. É o que permite, por exemplo, usar o mesmo estilo de botão em lugares diferentes sem reescrevê-lo, e o que torna a manutenção mais simples à medida que o app cresce.

**Os outros arquivos da equipe**

Fora de lib/, dois itens também são responsabilidade da equipe.

A pasta assets/ guarda as imagens do aplicativo — no caso, o logoRota.png e o iconeRota.png. Toda imagem que o app exibe precisa ficar aqui e ser registrada no pubspec.yaml.

O arquivo pubspec.yaml é o documento de identidade do projeto. Nele ficam o nome e a versão do app, a lista de bibliotecas externas que ele utiliza e o registro dos assets. Sempre que a equipe adiciona uma nova imagem ou uma nova biblioteca, é neste arquivo que a alteração é anotada. O pubspec.lock, ao lado dele, é gerado automaticamente e apenas trava as versões exatas de cada biblioteca para garantir que todos no grupo usem o mesmo.

**O que o Flutter gera sozinho?**

O restante da estrutura é criado e mantido pela própria ferramenta, e raramente precisa ser tocado. As pastas android/, ios/ e web/ contêm o código de suporte específico de cada plataforma onde o app pode rodar. As pastas windows/, macos/ e linux/ cumprem o mesmo papel para computadores de mesa — não são o alvo do projeto, mas foram geradas junto. A pasta test/ é o espaço reservado para testes automatizados. As pastas build/ e .dart_tool/ são resultado da compilação: pesadas, mudam a cada execução e são recriadas automaticamente. Por isso estão listadas no .gitignore, o arquivo que instrui o Git a nunca enviar esses itens ao repositório — o que mantém o repositório leve e evita subir centenas de megabytes de arquivos temporários. Por fim, .idea/, .metadata e rota_app.iml são configurações do editor e da ferramenta de desenvolvimento.

**Em resumo**

Para trabalhar no ROTA, o foco é a pasta lib/, complementada pelos assets e pelo pubspec.yaml. Todo o resto é infraestrutura que o Flutter administra. Manter essa separação clara — telas em screens/, peças em widgets/, decisões centrais em core/ — é o que garante que o projeto continue organizado e compreensível à medida que novas funcionalidades forem construídas nos próximos checkpoints.


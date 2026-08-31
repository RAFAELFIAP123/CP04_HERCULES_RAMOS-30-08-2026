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

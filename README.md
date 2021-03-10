# Minecraft Mod Tool
Minecraft Mod Tool é um projeto pessoal feito para aprendizado das tecnologias: microsserviços, comunicação interprocessos com [gRPC](https://grpc.io/), e webpage com [EmberJS](https://emberjs.com/).

Basicamente, o projeto se baseia numa ideia parecida com a do [Technic Launcher](https://www.technicpack.net/): instalar modpacks de maneira rápida e simples. 

O programa terá uma página web como front-end que irá controlar todas as configurações. Sendo possível: visualizar mods baixados ou instalados no diretório `.minecraft/mods`, criar modpacks customizados e instalá-los de maneira fácil.

## Funcionamento
O servidor web irá rodar em cima do [NodeJS](https://nodejs.org/), junto com o framework web [EmberJS](https://emberjs.com/). Ele se comunicará por [JSON](https://www.json.org/) com outros 8 microsserviços programados em [GoLang](https://golang.org/), cada um será responsável por uma ação:

- List Downloaded Mods
- List Mods from .minecraft
- Copy Mods to .minecraft
- Remove Mod(s) from .minecraft
- Remove Downloaded Mod(s)
- Create Modpack
- List Modpacks
- Use Modpack
- Remove Modpack

*&ast; Poderá ser utilizado um microsserviço intermediário para gerenciar as comunicações.*

Ainda não foi decidido qual base de dados utilizar. Inicialmente será utilizado [SQLite](https://www.sqlite.org/), porém pode mudar futuramente.

### Ideias secundárias
- [ ] Criar um Local de Criação. Uma página com funções para agilizar o processo de criação e teste de um modpack; contendo anotações gerais e individuais (para cada mod) e árvore de passos a serem completos.
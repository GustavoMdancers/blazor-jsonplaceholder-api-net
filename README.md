# Blazor Users JSONPlaceholder API

Aplicação de exemplo desenvolvida com **Blazor WebAssembly** e **.NET 10**. A página inicial consome a API pública [JSONPlaceholder](https://jsonplaceholder.typicode.com/) e exibe os dados do primeiro usuário retornado, incluindo informações pessoais, endereço, localização e empresa.

## Funcionalidades

- Consulta `https://jsonplaceholder.typicode.com/users` ao carregar a página inicial.
- Exibe nome, nome de usuário, e-mail, telefone, website, endereço, coordenadas geográficas e dados da empresa do primeiro usuário.
- Apresenta uma mensagem durante o carregamento e informa erros caso a chamada à API falhe.
- Registra no console do navegador o nome, a cidade e a empresa do usuário.
- Inclui também as páginas de demonstração Counter e Weather do template Blazor.

## Tecnologias

- C# e .NET 10
- Blazor WebAssembly
- Bootstrap
- JSONPlaceholder REST API

## Pré-requisitos

- [.NET 10 SDK](https://dotnet.microsoft.com/download/dotnet/10.0)
- Navegador moderno
- Acesso à internet para consultar a API JSONPlaceholder

Confira se o SDK está instalado:

```bash
dotnet --version
```

## Executar localmente

No terminal, entre na pasta do projeto:

```bash
cd BlazorUsersJsonPlaceHolderApi
```

Restaure as dependências e inicie a aplicação:

```bash
dotnet restore
dotnet watch
```

O perfil HTTP está configurado em `http://localhost:5114` e o perfil HTTPS em `https://localhost:7193`. Também é possível iniciar sem o watcher:

```bash
dotnet run
```

Ao abrir a aplicação, a rota `/` apresenta os dados do primeiro usuário. As rotas `/counter` e `/weather` mostram as páginas de demonstração do template.

## Estrutura do projeto

```text
BlazorUsersJsonPlaceHolderApi/
├── Layout/                 # Layout e navegação
├── Models/                 # Modelos User, Address, Geo e Company
├── Pages/                  # Páginas Home, Counter e Weather
├── Properties/             # Perfis de execução local
├── wwwroot/                # Arquivos estáticos e recursos da aplicação
├── App.razor               # Roteamento e configuração raiz do Blazor
└── Program.cs              # Inicialização do host WebAssembly e HttpClient
```

## Solução de problemas

### Limite de instâncias inotify no Linux

Se `dotnet watch` falhar com uma mensagem indicando que o limite de instâncias `inotify` foi atingido, use o watcher por polling:

```bash
DOTNET_USE_POLLING_FILE_WATCHER=1 dotnet watch
```

Como alternativa, feche processos que estejam observando muitos arquivos ou peça ao administrador do sistema para aumentar `fs.inotify.max_user_instances`. O valor depende da configuração do sistema; não é necessário alterar o projeto.

## API utilizada

- [JSONPlaceholder — Users](https://jsonplaceholder.typicode.com/users)
- [Documentação do JSONPlaceholder](https://jsonplaceholder.typicode.com/guide/)

## Licença

Consulte o arquivo [LICENSE](LICENSE) na raiz do repositório.
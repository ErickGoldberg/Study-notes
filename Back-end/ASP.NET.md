# ASP.NET
ASP.NET é um framework de desenvolvimento web criado pela Microsoft. Ele permite a criação de aplicativos web robustos, escaláveis e de alto desempenho utilizando a plataforma .NET. O ASP.NET oferece uma abordagem baseada em servidor para o desenvolvimento web, em que as páginas são processadas no servidor antes de serem enviadas ao navegador do usuário.

Existem duas principais versões do ASP.NET: o ASP.NET Web Forms e o ASP.NET MVC (Model-View-Controller). O ASP.NET Web Forms é uma abordagem baseada em controles, em que os desenvolvedores constroem a interface do usuário usando componentes de servidor, eventos e estado de visualização. Ele é útil para desenvolvedores com experiência em aplicações Windows Forms, pois possui um modelo de programação semelhante.

Já o ASP.NET MVC é uma estrutura baseada no padrão de design Model-View-Controller. Ele separa a lógica de negócios (Model), a interface do usuário (View) e a interação entre eles (Controller). Essa abordagem promove uma melhor separação de preocupações, facilita os testes e permite uma maior flexibilidade no desenvolvimento de aplicativos web.

Além disso, o ASP.NET Core é uma evolução do ASP.NET, oferecendo uma versão multiplataforma e de código aberto. Ele foi projetado para ser rápido, modular e escalável, sendo compatível com Windows, macOS e Linux. O ASP.NET Core é uma opção popular para o desenvolvimento de aplicativos web modernos e tem um desempenho excelente, mesmo em ambientes de alto tráfego.

O ASP.NET também possui recursos poderosos para lidar com segurança, gerenciamento de sessão, acesso a dados e integração com outros serviços e tecnologias da Microsoft, como o Azure e o SQL Server. Ele suporta diferentes linguagens de programação, incluindo C# e VB.NET, e fornece um ambiente de desenvolvimento integrado (IDE) chamado Visual Studio, que oferece recursos avançados de depuração, criação de interfaces e publicação de aplicativos web.

Em resumo, o ASP.NET é um framework poderoso e versátil para o desenvolvimento de aplicativos web. Ele oferece diversas opções e abordagens para atender às necessidades dos desenvolvedores e é amplamente utilizado na indústria para criar soluções web escaláveis, seguras e de alto desempenho.

## Estruturação das pastas:
A estrutura de pastas em um projeto ASP.NET pode variar dependendo da versão do ASP.NET e do tipo de projeto (Web Forms ou MVC). No entanto, irei fornecer uma visão geral da estrutura de pastas comumente usada no ASP.NET MVC, que é uma abordagem popular para o desenvolvimento web.

Em um projeto ASP.NET MVC típico, você pode encontrar as seguintes pastas:

- App_Data: Essa pasta é usada para armazenar dados de aplicativos, como arquivos de banco de dados, arquivos XML ou qualquer outro arquivo de dados relacionado ao aplicativo.
- App_Start: Essa pasta contém classes e arquivos de configuração que são executados no início do aplicativo. Por exemplo, você pode encontrar o arquivo RouteConfig.cs que configura as rotas de URL do aplicativo.
- Content: Essa pasta é usada para armazenar arquivos estáticos, como folhas de estilo CSS, arquivos de imagem e arquivos JavaScript.
- Controllers: Essa pasta contém as classes de controladores do ASP.NET MVC. Os controladores são responsáveis por processar solicitações HTTP, executar a lógica de negócios e retornar as respostas apropriadas.
- Models: Essa pasta contém as classes de modelo do aplicativo. Os modelos representam as entidades e os dados manipulados pelo aplicativo.
- Scripts: Essa pasta é usada para armazenar arquivos JavaScript usados no aplicativo.
- Views: Essa pasta contém as visualizações do aplicativo, que são responsáveis por exibir a interface do usuário. Ela é geralmente organizada em subpastas correspondentes a cada controlador, contendo arquivos .cshtml ou .vbhtml que definem a estrutura e o conteúdo das páginas.
- Areas: Essa pasta é opcional e é usada para organizar o aplicativo em áreas funcionais separadas. Cada área pode ter sua própria estrutura de pastas semelhante à estrutura principal do aplicativo.
- App.config ou Web.config: Esses arquivos de configuração são usados para configurar o aplicativo, definindo valores de chave-valor, conexões de banco de dados, configurações de autenticação, entre outros.

Além dessas pastas principais, você também pode encontrar outras pastas, dependendo das necessidades do seu projeto e das bibliotecas ou ferramentas utilizadas. É importante lembrar que a estrutura de pastas pode ser personalizada e ajustada de acordo com as preferências da equipe de desenvolvimento e os requisitos do projeto.

É válido ressaltar que essa é apenas uma visão geral da estrutura de pastas do ASP.NET MVC. Outras versões do ASP.NET, como o ASP.NET Web Forms ou o ASP.NET Core, podem ter estruturas de pastas um pouco diferentes, mas o conceito geral de separar modelos, visualizações e controladores ainda é aplicado.

## Principais classes:
1. System.Web.UI.Page: Essa classe é a base para todas as páginas do ASP.NET Web Forms. Ela fornece recursos para gerenciar o ciclo de vida da página, manipular eventos, acessar controles e interagir com dados.

2. System.Web.Mvc.Controller: Essa classe é a base para os controladores no ASP.NET MVC. Ela gerencia as ações e a lógica de processamento das solicitações HTTP, bem como a interação com modelos e visualizações.

3. System.Web.HttpApplication: Essa classe é a base para a classe Global.asax no ASP.NET. Ela gerencia o ciclo de vida da aplicação web e permite a execução de código em eventos específicos, como a inicialização da aplicação ou o tratamento de erros.

4. System.Web.UI.WebControls: Esse namespace contém várias classes para criar controles de interface do usuário, como botões, caixas de texto, listas suspensas, entre outros. Essas classes permitem interações com o usuário e manipulação de dados na interface web.

5. System.Web.Security.Membership: Esse namespace contém classes para gerenciar a autenticação e a autorização de usuários em um aplicativo web. Ele fornece recursos para criar e gerenciar contas de usuário, autenticar usuários e controlar o acesso a recursos protegidos.

6. System.Data.SqlClient.SqlConnection: Essa classe faz parte do namespace System.Data.SqlClient e é usada para estabelecer conexões com bancos de dados SQL Server. Ela permite a execução de consultas e a manipulação de dados no contexto de um aplicativo ASP.NET.

7. System.Web.Caching.Cache: Essa classe fornece um mecanismo de cache para armazenar dados em memória, reduzindo o acesso ao banco de dados e melhorando o desempenho do aplicativo. Ela permite armazenar e recuperar objetos em cache de forma eficiente.

8. System.Web.Services.WebService: Essa classe é usada para criar serviços web no ASP.NET. Ela permite que os aplicativos web exponham métodos como serviços web, que podem ser acessados por outros aplicativos através de chamadas HTTP.

Essas são apenas algumas das principais classes do ASP.NET. O framework possui uma ampla gama de classes e bibliotecas adicionais que fornecem recursos para diferentes aspectos do desenvolvimento web, como manipulação de cookies, gerenciamento de sessão, manipulação de arquivos, entre outros.

## Exemplo de controller api:

~~~
using Microsoft.AspNetCore.Mvc;

namespace NomeDoProjeto.Controllers
{
    [Route("api/[controller]")]
    [ApiController]
    public class ExemploController : ControllerBase
    {
        [HttpGet]
        public IActionResult Get()
        {
            return Ok("API funcionando!");
        }

        [HttpPost]
        public IActionResult Post([FromBody] string mensagem)
        {
            // Lógica para processar a mensagem recebida
            return Ok();
        }
        [HttpPut("{id}")]
        public IActionResult Put(int id, [FromBody] string mensagem)
        {
            // Lógica para atualizar o recurso com o ID especificado
            return Ok();
        }

        [HttpDelete("{id}")]
        public IActionResult Delete(int id)
        {
            // Lógica para excluir o recurso com o ID especificado
            return Ok();
        }

    }
}
~~~

## IsPostBack:
IsPostBack é uma propriedade em ASP.NET, especificamente no ambiente WebForms, que é usada para determinar se a página está sendo carregada ou reenviada em resposta a uma interação do usuário, como o clique de um botão ou o envio de um formulário.

Em uma aplicação ASP.NET WebForms, a interação do usuário pode causar o envio de dados do cliente de volta ao servidor para processamento. Por exemplo, quando um usuário preenche um formulário e clica em um botão "Enviar", os dados do formulário são enviados de volta ao servidor para serem processados. Essa interação pode fazer com que a página seja carregada novamente.

A propriedade IsPostBack é usada para distinguir entre o carregamento inicial da página e o carregamento causado por um evento de postback (como o clique de um botão). Ela retorna um valor booleano:

- true: Indica que a página está sendo carregada como resultado de um postback, ou seja, em resposta a uma interação do usuário que enviou dados para o servidor.
- false: Indica que a página está sendo carregada pela primeira vez, sem postback, ou seja, é o carregamento inicial da página.
Essa distinção é útil em várias situações, principalmente quando você deseja executar determinadas ações apenas no carregamento inicial da página e evitar que essas ações sejam repetidas em postbacks subsequentes.

Exemplo de uso em C#:
~~~
protected void Page_Load(object sender, EventArgs e)
{
    if (!IsPostBack)
    {
        // Código a ser executado apenas no carregamento inicial da página
        // por exemplo, carregar dados iniciais, definir valores padrão, etc.
    }
    else
    {
        // Código a ser executado nos postbacks subsequentes, caso necessário
    }
}
~~~
Em resumo, IsPostBack é uma propriedade útil em ASP.NET WebForms para identificar se a página está sendo carregada pela primeira vez ou em resposta a um postback, permitindo que você tome ações apropriadas com base nessa informação.

## Tokens JWT:
Tokens JWT (JSON Web Tokens) são frequentemente usados em aplicativos ASP.NET (e em muitos outros tipos de aplicativos) como um mecanismo para autenticação e autorização. Aqui estão algumas razões pelas quais os tokens JWT são amplamente utilizados em ASP.NET:

- Segurança: Os tokens JWT são assinados digitalmente e podem ser verificados para garantir sua autenticidade. Eles são protegidos contra adulteração e, quando usados corretamente, são uma forma segura de autenticação.

- Stateless (sem estado): Os tokens JWT são projetados para serem "stateless", o que significa que o servidor não precisa armazenar informações sobre o token em si. Isso permite que os servidores sejam escalonados horizontalmente e simplifica a arquitetura do aplicativo.

- Portabilidade: Os tokens JWT são baseados em padrões abertos e podem ser usados em diferentes tecnologias e plataformas. Isso significa que um token JWT gerado por um servidor ASP.NET pode ser verificado e usado por outro serviço, independentemente da tecnologia que está sendo usada.

- Informações personalizadas: Os tokens JWT são estruturados como objetos JSON, permitindo que informações adicionais sejam incluídas no token. Isso possibilita a inclusão de dados personalizados relevantes para a aplicação, como permissões, níveis de acesso e outras informações do usuário.

- Escalabilidade: Como os tokens JWT são autocontidos e não exigem armazenamento de estado no servidor, eles podem ser facilmente distribuídos em um ambiente distribuído e escalável, como um sistema de microsserviços.

- Integração com serviços de terceiros: Os tokens JWT são amplamente suportados por serviços e frameworks de terceiros, como serviços de autenticação e autorização baseados em nuvem, APIs RESTful e muito mais. Isso torna mais fácil integrar seu aplicativo ASP.NET com outros sistemas.

Em resumo, os tokens JWT são populares em aplicativos ASP.NET devido à sua segurança, facilidade de uso, portabilidade e capacidade de integrar-se facilmente com outros serviços e plataformas. Eles fornecem uma maneira eficaz de autenticar e autorizar usuários em aplicativos web.

## Secrets:
Em aplicações ASP.NET, os "secrets" (segredos) referem-se a informações sensíveis, como senhas de banco de dados, chaves de API ou outras configurações que precisam ser protegidas. Manter esses segredos em um local seguro é essencial para garantir a segurança do seu aplicativo.

Antes do ASP.NET Core 2.0, era comum armazenar segredos diretamente no arquivo de configuração (appsettings.json ou web.config). No entanto, isso não é recomendado, pois esses arquivos geralmente são armazenados em repositórios de controle de versão, o que pode expor acidentalmente informações confidenciais.

Com o ASP.NET Core, você pode usar o recurso de gerenciamento de segredos fornecido pelo pacote Microsoft.Extensions.Configuration.UserSecrets para armazenar e acessar seus segredos de forma segura durante o desenvolvimento. Esses segredos são armazenados em um local específico no seu sistema de arquivos, fora do controle de versão do projeto.

Links úteis:
- https://learn.microsoft.com/en-us/aspnet/core/?view=aspnetcore-7.0&utm_source=aspnet-start-page&utm_campaign=vside
- https://dotnet.microsoft.com/en-us/learn/dotnet/architecture-guides?utm_source=aspnet-start-page&utm_campaign=vside

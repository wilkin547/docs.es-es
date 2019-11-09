---
title: Creación de un nuevo ASP.NET Core proyecto de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo crear un proyecto de gRPC con Visual Studio o desde la línea de comandos.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: a30d19e1e48692ad68a648406d4bf369937744d7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841664"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Creación de un nuevo proyecto gRPC de ASP.NET Core

.NET Core incluye una eficaz herramienta de la CLI, `dotnet`, que permite crear y administrar proyectos y soluciones desde la línea de comandos. La herramienta está estrechamente integrada con Visual Studio, por lo que todo está disponible a través de la interfaz GUI familiar. En este capítulo se muestran las dos maneras de crear un nuevo proyecto de gRPC ASP.NET Core: en primer lugar con Visual Studio, con el CLI de .NET Core.

## <a name="create-the-project-using-visual-studio"></a>Crear el proyecto mediante Visual Studio

> [!IMPORTANT]
> Para desarrollar una aplicación ASP.NET Core 3,0, necesita Visual Studio 2019,3 o posterior con la carga de trabajo de **desarrollo web y ASP.net** instalada.

Cree una solución vacía denominada **Traders** a partir de la plantilla de *solución en blanco* . Agregue una carpeta de soluciones llamada `src`, haga clic con el botón derecho en la carpeta y elija **agregar** > **nuevo proyecto** en el menú contextual. Escriba `grpc` en el cuadro de búsqueda de plantillas y debería ver una plantilla de proyecto denominada `gRPC Service`.

![Cuadro de diálogo Agregar nuevo proyecto que muestra la plantilla de proyecto de servicio gRPC](media/create-project/new-grpc-project.png)

Haga clic en **siguiente** para continuar con el cuadro de diálogo **configurar proyecto** , asigne al proyecto el nombre `TraderSys.Portfolios`y agregue un subdirectorio `src` a la **Ubicación**.

![Cuadro de diálogo Configurar proyecto](media/create-project/configure-project.png)

Haga clic en **siguiente** para continuar en el cuadro de diálogo **nuevo proyecto de gRPC** .

![Cuadro de diálogo nuevo proyecto de gRPC](media/create-project/create-new-grpc-service.png)

En la actualidad, hay opciones limitadas para la creación del servicio. Docker se introducirá más adelante en el libro, de modo que deje la casilla desactivada por ahora y simplemente haga clic en **crear**. Se genera el primer ASP.NET Core 3,0 gRPC proyecto y se agrega a la solución. Si no desea saber cómo trabajar con el `dotnet CLI`, vaya a la sección [limpieza del código de ejemplo](#clean-up-the-example-code) .

## <a name="create-the-project-using-the-net-core-cli"></a>Cree el proyecto mediante el CLI de .NET Core

En esta sección se describe la creación de soluciones y proyectos desde la línea de comandos.

Cree la solución como se muestra a continuación. La marca `-o` (o `--output`) especifica el directorio de salida, que se creará en el directorio actual si no existe. La solución tendrá el mismo nombre que el directorio, es decir, `TraderSys.sln`. Puede proporcionar un nombre diferente mediante la marca `-n` (o `--name`).

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 3,0 incluye una plantilla de CLI para gRPC Services. Cree el nuevo proyecto con esta plantilla y colóquelo en un subdirectorio de `src` como la Convención de ASP.NET Core proyectos. El proyecto se denominará después del directorio (es decir, `TraderSys.Portfolios.csproj`) a menos que especifique otro nombre con la marca `-n`.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Por último, agregue el proyecto a la solución con el comando `dotnet sln`.

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Dado que el directorio especificado solo contiene un único archivo de `.csproj`, puede empezar a especificar solo el directorio para guardar escribiendo.

Ahora puede abrir esta solución en Visual Studio 2019, Visual Studio Code o cualquier editor que prefiera.

## <a name="clean-up-the-example-code"></a>Limpieza del código de ejemplo

Ahora ha creado un servicio de ejemplo con la plantilla gRPC, que se ha revisado anteriormente en el libro. Esto no es útil en nuestro contexto de transacciones bursátiles, por lo que editaremos cosas para nuestro primer proyecto.

### <a name="rename-and-edit-the-proto-file"></a>Cambiar el nombre y editar el archivo proto

Continúe y cambie el nombre del archivo de `Protos/greet.proto` a `Protos/portfolios.proto` y ábralo en el editor. Elimine todo lo que haya después de la línea de `package`, cambie los nombres de `option csharp_namespace`, `package` y `service` y quite el servicio de `SayHello` predeterminado, de modo que el código tenga este aspecto.

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> La plantilla no agrega la parte del espacio de nombres `Protos` de forma predeterminada, pero al agregarla es más fácil mantener las clases generadas por gRPC y sus propias clases separadas claramente en el código.

Si cambia el nombre del archivo de `greet.proto` en un entorno de desarrollo integrado (IDE) como Visual Studio, se actualiza automáticamente una referencia a este archivo en el archivo de `.csproj`. Pero en otro editor, como Visual Studio Code, esta referencia no se actualiza automáticamente, por lo que debe editar el archivo de proyecto manualmente.

En los destinos de compilación de gRPC, hay un elemento `Protobuf` elemento que le permite especificar qué archivos de `.proto` se deben compilar y qué forma de generación de código es necesaria (es decir, "servidor" o "cliente").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Cambiar el nombre de la clase GreeterService

La clase `GreeterService` se encuentra en la carpeta `Services` y hereda de `Greeter.GreeterBase`. Cambie el nombre a `PortfolioService` y cambie la clase base a `Portfolios.PortfoliosBase`. Elimine los métodos de `override`.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

Hay una referencia a la clase `GreeterService` en el método `Configure` de la clase `Startup`. Si usó la refactorización para cambiar el nombre de la clase, esta referencia debería haberse actualizado automáticamente. Sin embargo, si no lo ha hecho, debe editarlo manualmente.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

En la siguiente sección, agregaremos funcionalidad a este nuevo servicio.

>[!div class="step-by-step"]
>[Anterior](migrate-wcf-to-grpc.md)
>[Siguiente](migrate-request-reply.md)

---
title: Introducción a la herramienta svcutil de WCF
description: Información general sobre la herramienta dotnet-svcutil de WCF de Microsoft que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a la herramienta svcutil de WCF para proyectos de .NET Framework.
author: mlacouture
ms.date: 02/22/2019
ms.openlocfilehash: d204576f27227ce6e65d61471f19cdf3ec4df37a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714562"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a>Herramienta dotnet-svcutil de WCF para .NET Core

La herramienta **dotnet-svcutil** de Windows Communication Foundation (WCF) es una herramienta de la CLI de .NET Core que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera una clase de WCF que contiene métodos de proxy de cliente que acceden a las operaciones del servicio web.

Similar a la herramienta [**de utilidad de metadatos de ServiceModel (Svcutil.exe)** ](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para proyectos de .NET Framework, **dotnet-svcutil** es una herramienta de línea de comandos para generar una referencia de servicio web compatible con proyectos de .NET Core y .NET Standard.

La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de la CLI de .NET Core, está disponible en las distintas plataformas de Linux, Mac OS y Windows.

> [!IMPORTANT]
> Solo debe hacer referencia a servicios desde un origen de confianza. Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.

## <a name="prerequisites"></a>Requisitos previos

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

- [SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores
- Su editor de código favorito

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

- [SDK de .NET Core 1.0.4](https://dotnet.microsoft.com/download) o versiones posteriores
- Su editor de código favorito

---

## <a name="getting-started"></a>Introducción

En el ejemplo siguiente se le guía por los pasos necesarios para agregar una referencia de servicio web a un proyecto web de .NET Core e invocar el servicio. Creará una aplicación web de .NET Core denominada *HelloSvcutil* y agregará una referencia a un servicio web que implementa el siguiente contrato:

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

En este ejemplo, se da por hecho que el servicio web se hospedará en la siguiente dirección: `http://contoso.com/SayHello.svc`

Desde una ventana de comandos de Windows, Mac OS o Linux, siga estos pasos:

1. Cree un directorio denominado _HelloSvcutil_ para el proyecto y hágalo su directorio actual, como en el ejemplo siguiente:

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. Cree un nuevo proyecto web de C# en ese directorio mediante el comando [`dotnet new`](../tools/dotnet-new.md) del modo siguiente:

    ```dotnetcli
    dotnet new web
    ```

3. Instale el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como herramienta CLI:  <!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)
    Abra el archivo de proyecto `HelloSvcutil.csproj` en su editor, edite el elemento `Project` y agregue el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como referencia de la herramienta CLI, usando el siguiente código:

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    Restaure el paquete _dotnet-svcutil_ mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) de la siguiente manera:

    ```dotnetcli
    dotnet restore
    ```

    ---

4. Ejecute el comando _dotnet-svcutil_ para generar el archivo de referencia del servicio web de la siguiente manera:

    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

El archivo generado se guarda como _HelloSvcutil/ServiceReference1/Reference.cs_. La herramienta _dotnet_svcutil_ también agrega al proyecto los paquetes de WCF adecuados que necesita el código de proxy como referencias del paquete.

## <a name="using-the-service-reference"></a>Uso de la referencia de servicio

1. Restaure los paquetes de WCF mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) como sigue:

    ```dotnetcli
    dotnet restore
    ```

2. Busque el nombre de la clase de cliente y la operación que quiera usar. `Reference.cs` contendrá una clase que se hereda de `System.ServiceModel.ClientBase`, con métodos que pueden usarse para llamar a las operaciones del servicio. En este ejemplo, quiere llamar a la operación _Hello_ del servicio _SayHello_. `ServiceReference.SayHelloClient` es el nombre de la clase de cliente, y tiene un método llamado `HelloAsync` que se puede usar para llamar a la operación.

3. Abra el archivo `Startup.cs` en el editor y agregue una instrucción using al espacio de nombres de la referencia de servicio en la parte superior:

    ```csharp
    using ServiceReference;
    ```

4. Edite el método `Configure` para invocar el servicio web. Para ello, cree una instancia de la clase que se hereda de `ClientBase` y llame al método en el objeto de cliente:

    ```csharp
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            var client = new SayHelloClient();
            var response = await client.HelloAsync();
            await context.Response.WriteAsync(response);
        });
    }

    ```

5. Ejecute la aplicación con el comando [`dotnet run`](../tools/dotnet-run.md) como sigue:

    ```dotnetcli
    dotnet run
    ```

6. Vaya a la dirección URL indicada en la consola (por ejemplo, `http://localhost:5000`) en el explorador web.

Debería ver los siguientes resultados: "Hello dotnet-svcutil!"

Para obtener una descripción detallada de los parámetros de la herramienta `dotnet-svcutil`, invoque la herramienta pasando el parámetro de ayuda del siguiente modo:
# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[dotnet-svcutil 2.x](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[dotnet-svcutil 1.x](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a>Preguntas y comentarios

Si tiene preguntas o comentarios, [abra un problema en GitHub](https://github.com/dotnet/wcf/issues/new). También puede revisar las preguntas o problemas que ya se han planteado en el [repositorio de WCF en GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).

## <a name="release-notes"></a>Notas de la versión

- Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.

## <a name="information"></a>Información

- [Paquete NuGet svcutil dotnet](https://nuget.org/packages/dotnet-svcutil)

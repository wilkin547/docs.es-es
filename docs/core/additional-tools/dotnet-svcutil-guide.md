---
title: Introducción a la herramienta svcutil de WCF
description: Información general sobre la herramienta dotnet-svcutil de WCF de Microsoft que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a la herramienta svcutil de WCF para proyectos de .NET Framework.
author: mlacouture
ms.date: 08/20/2018
ms.custom: seodec18
ms.openlocfilehash: e42ec0d4072c56456c824a814f1b383ea70a9307
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237264"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a>Herramienta dotnet-svcutil de WCF para .NET Core

La herramienta **dotnet-svcutil** de Windows Communication Foundation (WCF) es una herramienta de la CLI de .NET Core que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera una clase de WCF que contiene métodos de proxy de cliente que acceden a las operaciones del servicio web.

Similar a la herramienta [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para proyectos de .NET Framework, **dotnet-svcutil** es una herramienta de línea de comandos para generar una referencia de servicio web compatible con proyectos de .NET Core y .NET Standard.

La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017. La herramienta **dotnet-svcutil**, como herramienta de la CLI de .NET Core, está disponible en las distintas plataformas de Linux, Mac OS y Windows.

> [!IMPORTANT]
> Solo debe hacer referencia a servicios desde un origen de confianza. Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.

## <a name="prerequisites"></a>Requisitos previos

* [SDK de .NET Core](https://dotnet.microsoft.com/download), versión 1.0.4 o posterior
* Su editor de código favorito

## <a name="getting-started"></a>Introducción

En el ejemplo siguiente se le guía por los pasos necesarios para agregar una referencia de servicio web a un proyecto de consola de .NET Core e invocar el servicio. Creará una aplicación de consola de .NET Core denominada _HelloSvcutil_ y agregará una referencia a un servicio web que implementa el contrato siguiente:

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

En este ejemplo, se supondrá que el servicio web se hospeda en la siguiente dirección: `http://contoso.com/SayHello.svc`

Desde una ventana de comandos de Windows, Mac OS o Linux, siga estos pasos:

1. Cree un directorio denominado _HelloSvcutil_ para el proyecto y hágalo su directorio actual, como en el ejemplo siguiente:

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. Cree un nuevo proyecto de consola de C# en ese directorio mediante el comando [`dotnet new`](../tools/dotnet-new.md) del modo siguiente:

```console
dotnet new console
```

3. Abra el archivo de proyecto `HelloSvcutil.csproj` en su editor, edite el elemento `Project` y agregue el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como referencia de la herramienta CLI, usando el siguiente código:

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. Restaure el paquete _dotnet-svcutil_ utilizando el comando [`dotnet restore`](../tools/dotnet-restore.md) de la siguiente manera:

```console
dotnet restore
```

5. Ejecute _dotnet_ con el comando _svcutil_ para generar el archivo de referencia de servicio web como se indica a continuación:

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
El archivo generado se guarda como _HelloSvcutil/ServiceReference1/Reference.cs_. La herramienta _dotnet_svcutil_ también agrega al proyecto los paquetes adecuados de WCF requeridos por el código de proxy como referencias del paquete.

6. Restaure los paquetes de WCF mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) como sigue:

```console
dotnet restore
```

7. Abra el archivo `Program.cs` en el editor, edite el método `Main()` y reemplace el código generado automáticamente por el código siguiente para invocar el servicio web:

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. Ejecute la aplicación con el comando [`dotnet run`](../tools/dotnet-run.md) como sigue:

```console
dotnet run
```
Debería ver los siguientes resultados: "Hello dotnet-svcutil!"

Para obtener una descripción detallada de los parámetros de la herramienta `dotnet-svcutil`, invoque la herramienta pasando el parámetro de ayuda del siguiente modo:

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>Pasos siguientes

### <a name="feedback--questions"></a>Preguntas y comentarios

Si tiene preguntas o comentarios, [abra un problema en GitHub](https://github.com/dotnet/wcf/issues/new). También puede revisar las preguntas o problemas que ya se han planteado en el [repositorio de WCF en GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).

### <a name="release-notes"></a>Notas de la versión

* Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.

### <a name="information"></a>Información

* [Paquete NuGet svcutil dotnet](https://nuget.org/packages/dotnet-svcutil)

---
title: Herramienta dotnet-svcutil de WCF de Microsoft
description: Información general sobre la herramienta dotnet-svcutil de WCF de Microsoft que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a la herramienta svcutil de WCF para proyectos de .NET Framework.
author: mlacouture
ms.author: jralexander
ms.date: 08/20/2018
ms.openlocfilehash: bb4d8e5f3997318b720535b0f1e07fc33d13338a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484126"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a><span data-ttu-id="53af4-103">Herramienta dotnet-svcutil de WCF de Microsoft</span><span class="sxs-lookup"><span data-stu-id="53af4-103">Microsoft WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="53af4-104">La herramienta **dotnet-svcutil** de Windows Communication Foundation (WCF) es una herramienta de la CLI de .NET Core que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera una clase de WCF que contiene métodos de proxy de cliente que acceden a las operaciones del servicio web.</span><span class="sxs-lookup"><span data-stu-id="53af4-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="53af4-105">Similar a la herramienta [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para proyectos de .NET Framework, **dotnet-svcutil** es una herramienta de línea de comandos para generar una referencia de servicio web compatible con proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="53af4-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="53af4-106">La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="53af4-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="53af4-107">La herramienta **dotnet-svcutil**, como herramienta de la CLI de .NET Core, está disponible en las distintas plataformas de Linux, Mac OS y Windows.</span><span class="sxs-lookup"><span data-stu-id="53af4-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53af4-108">Solo debe hacer referencia a servicios desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="53af4-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="53af4-109">Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.</span><span class="sxs-lookup"><span data-stu-id="53af4-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="53af4-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="53af4-110">Prerequisites</span></span>

* <span data-ttu-id="53af4-111">[SDK de .NET Core](https://www.microsoft.com/net/download), versión 1.0.4 o posterior</span><span class="sxs-lookup"><span data-stu-id="53af4-111">[.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 or later versions</span></span>
* <span data-ttu-id="53af4-112">Su editor de código favorito</span><span class="sxs-lookup"><span data-stu-id="53af4-112">Your favorite code editor</span></span>

## <a name="getting-started"></a><span data-ttu-id="53af4-113">Introducción</span><span class="sxs-lookup"><span data-stu-id="53af4-113">Getting started</span></span>

<span data-ttu-id="53af4-114">En el ejemplo siguiente se le guía por los pasos necesarios para agregar una referencia de servicio web a un proyecto de consola de .NET Core e invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="53af4-114">The following example walks you through the steps required to add a web service reference to a .NET Core console project and invoke the service.</span></span> <span data-ttu-id="53af4-115">Creará una aplicación de consola de .NET Core denominada _HelloSvcutil_ y agregará una referencia a un servicio web que implementa el contrato siguiente:</span><span class="sxs-lookup"><span data-stu-id="53af4-115">You will create a .NET Core console application named _HelloSvcutil_ and will add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="53af4-116">En este ejemplo, se supondrá que el servicio web se hospeda en la siguiente dirección: `http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="53af4-116">For this example, the web service will be assumed to be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="53af4-117">Desde una ventana de comandos de Windows, Mac OS o Linux, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="53af4-117">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="53af4-118">Cree un directorio denominado _HelloSvcutil_ para el proyecto y hágalo su directorio actual, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53af4-118">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. <span data-ttu-id="53af4-119">Cree un nuevo proyecto de consola de C# en ese directorio mediante el comando [`dotnet new`](../tools/dotnet-new.md) del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="53af4-119">Create a new C# console project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

```console
dotnet new console
```

3. <span data-ttu-id="53af4-120">Abra el archivo de proyecto `HelloSvcutil.csproj` en su editor, edite el elemento `Project` y agregue el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como referencia de la herramienta CLI, usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="53af4-120">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. <span data-ttu-id="53af4-121">Restaure el paquete _dotnet-svcutil_ utilizando el comando [`dotnet restore`](../tools/dotnet-restore.md) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="53af4-121">Restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

5. <span data-ttu-id="53af4-122">Ejecute _dotnet_ con el comando _svcutil_ para generar el archivo de referencia de servicio web como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="53af4-122">Run _dotnet_ with the _svcutil_ command to generate the web service reference file as follows:</span></span>

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
<span data-ttu-id="53af4-123">El archivo generado se guarda como _HelloSvcutil/ServiceReference1/Reference.cs_.</span><span class="sxs-lookup"><span data-stu-id="53af4-123">The generated file is saved as _HelloSvcutil/ServiceReference1/Reference.cs_.</span></span> <span data-ttu-id="53af4-124">La herramienta _dotnet_svcutil_ también agrega al proyecto los paquetes adecuados de WCF requeridos por el código de proxy como referencias del paquete.</span><span class="sxs-lookup"><span data-stu-id="53af4-124">The _dotnet_svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

6. <span data-ttu-id="53af4-125">Restaure los paquetes de WCF mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) como sigue:</span><span class="sxs-lookup"><span data-stu-id="53af4-125">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

7. <span data-ttu-id="53af4-126">Abra el archivo `Program.cs` en el editor, edite el método `Main()` y reemplace el código generado automáticamente por el código siguiente para invocar el servicio web:</span><span class="sxs-lookup"><span data-stu-id="53af4-126">Open the `Program.cs` file in your editor, edit the `Main()` method, and replace the auto-generated code with the following code to invoke the web service:</span></span>

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. <span data-ttu-id="53af4-127">Ejecute la aplicación con el comando [`dotnet run`](../tools/dotnet-run.md) como sigue:</span><span class="sxs-lookup"><span data-stu-id="53af4-127">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

```console
dotnet run
```
<span data-ttu-id="53af4-128">Debería ver el siguiente resultado: "Hello dotnet-svcutil!".</span><span class="sxs-lookup"><span data-stu-id="53af4-128">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="53af4-129">Para obtener una descripción detallada de los parámetros de la herramienta `dotnet-svcutil`, invoque la herramienta pasando el parámetro de ayuda del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="53af4-129">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

```console
dotnet svcutil --help
```

## <a name="next-steps"></a><span data-ttu-id="53af4-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="53af4-130">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="53af4-131">Preguntas y comentarios</span><span class="sxs-lookup"><span data-stu-id="53af4-131">Feedback & questions</span></span>

<span data-ttu-id="53af4-132">Si tiene preguntas o comentarios, [abra un problema en GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="53af4-132">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="53af4-133">También puede revisar las preguntas o problemas que ya se han planteado en el [repositorio de WCF en GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="53af4-133">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="53af4-134">Notas de la versión</span><span class="sxs-lookup"><span data-stu-id="53af4-134">Release notes</span></span>

* <span data-ttu-id="53af4-135">Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="53af4-135">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

### <a name="information"></a><span data-ttu-id="53af4-136">Información</span><span class="sxs-lookup"><span data-stu-id="53af4-136">Information</span></span>

* [<span data-ttu-id="53af4-137">Paquete NuGet svcutil dotnet</span><span class="sxs-lookup"><span data-stu-id="53af4-137">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)

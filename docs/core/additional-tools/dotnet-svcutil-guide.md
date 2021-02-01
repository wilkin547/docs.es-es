---
title: Introducción a la herramienta svcutil de WCF
description: Información general sobre la herramienta dotnet-svcutil de WCF de Microsoft que agrega funciones para proyectos de .NET Core y ASP.NET Core, similares a la herramienta svcutil de WCF para proyectos de .NET Framework.
author: honggit
ms.date: 02/22/2019
ms.openlocfilehash: 9468a881fe3850b53d48945340127ac2c2d4c6c8
ms.sourcegitcommit: 7e42488c2f8f63f6d499b5f8fb1dec5bac9ad254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957928"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a><span data-ttu-id="d39c5-103">Herramienta dotnet-svcutil de WCF para .NET Core</span><span class="sxs-lookup"><span data-stu-id="d39c5-103">WCF dotnet-svcutil tool for .NET Core</span></span>

<span data-ttu-id="d39c5-104">La herramienta **dotnet-svcutil** de Windows Communication Foundation (WCF) es una herramienta de .NET que recupera metadatos de un servicio web en una ubicación de red o de un archivo WSDL, y genera una clase de WCF que contiene métodos de proxy de cliente que acceden a las operaciones del servicio web.</span><span class="sxs-lookup"><span data-stu-id="d39c5-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="d39c5-105">Similar a la herramienta [**de utilidad de metadatos de ServiceModel (Svcutil.exe)**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para proyectos de .NET Framework, **dotnet-svcutil** es una herramienta de línea de comandos para generar una referencia de servicio web compatible con proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d39c5-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="d39c5-106">La herramienta **dotnet-svcutil** es una alternativa al proveedor de servicios conectados de Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) que se distribuyó por primera vez en la versión 15.5 de Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d39c5-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 version 15.5.</span></span> <span data-ttu-id="d39c5-107">La herramienta multiplataforma **dotnet-svcutil**, como herramienta de .NET, está disponible en Linux, macOS y Windows.</span><span class="sxs-lookup"><span data-stu-id="d39c5-107">The **dotnet-svcutil** tool as a .NET tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d39c5-108">Solo debe hacer referencia a servicios desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="d39c5-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="d39c5-109">Si agrega referencias desde un origen que no es de confianza podría poner en peligro la seguridad.</span><span class="sxs-lookup"><span data-stu-id="d39c5-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d39c5-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d39c5-110">Prerequisites</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2x"></a>[<span data-ttu-id="d39c5-111">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-111">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

- <span data-ttu-id="d39c5-112">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d39c5-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="d39c5-113">Su editor de código favorito</span><span class="sxs-lookup"><span data-stu-id="d39c5-113">Your favorite code editor</span></span>

# <a name="dotnet-svcutil-1x"></a>[<span data-ttu-id="d39c5-114">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-114">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

- <span data-ttu-id="d39c5-115">[SDK de .NET Core 1.0.4](https://dotnet.microsoft.com/download) o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d39c5-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="d39c5-116">Su editor de código favorito</span><span class="sxs-lookup"><span data-stu-id="d39c5-116">Your favorite code editor</span></span>

---

## <a name="getting-started"></a><span data-ttu-id="d39c5-117">Introducción</span><span class="sxs-lookup"><span data-stu-id="d39c5-117">Getting started</span></span>

<span data-ttu-id="d39c5-118">En el ejemplo siguiente se le guía por los pasos necesarios para agregar una referencia de servicio web a un proyecto web de .NET Core e invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="d39c5-118">The following example walks you through the steps required to add a web service reference to a .NET Core web project and invoke the service.</span></span> <span data-ttu-id="d39c5-119">Creará una aplicación web de .NET Core denominada *HelloSvcutil* y agregará una referencia a un servicio web que implementa el siguiente contrato:</span><span class="sxs-lookup"><span data-stu-id="d39c5-119">You'll create a .NET Core web application named *HelloSvcutil* and add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="d39c5-120">En este ejemplo, se da por hecho que el servicio web se hospedará en la siguiente dirección: `http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="d39c5-120">For this example, let's assume the web service will be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="d39c5-121">Desde una ventana de comandos de Windows, Mac OS o Linux, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d39c5-121">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="d39c5-122">Cree un directorio denominado _HelloSvcutil_ para el proyecto y hágalo su directorio actual, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d39c5-122">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. <span data-ttu-id="d39c5-123">Cree un nuevo proyecto web de C# en ese directorio mediante el comando [`dotnet new`](../tools/dotnet-new.md) del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d39c5-123">Create a new C# web project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

    ```dotnetcli
    dotnet new web
    ```

3. <span data-ttu-id="d39c5-124">Instale el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como herramienta CLI:  </span><span class="sxs-lookup"><span data-stu-id="d39c5-124">Install the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool:  </span></span><!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2x"></a>[<span data-ttu-id="d39c5-125">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-125">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1x"></a>[<span data-ttu-id="d39c5-126">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-126">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

    <span data-ttu-id="d39c5-127">Abra el archivo de proyecto `HelloSvcutil.csproj` en su editor, edite el elemento `Project` y agregue el [paquete NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) como referencia de la herramienta CLI, usando el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="d39c5-127">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    <span data-ttu-id="d39c5-128">Restaure el paquete _dotnet-svcutil_ mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d39c5-128">Then restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

    ---

4. <span data-ttu-id="d39c5-129">Ejecute el comando _dotnet-svcutil_ para generar el archivo de referencia del servicio web de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d39c5-129">Run the _dotnet-svcutil_ command to generate the web service reference file as follows:</span></span>

    # <a name="dotnet-svcutil-2x"></a>[<span data-ttu-id="d39c5-130">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-130">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1x"></a>[<span data-ttu-id="d39c5-131">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-131">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

<span data-ttu-id="d39c5-132">El archivo generado se guarda como _HelloSvcutil/ServiceReference1/Reference.cs_.</span><span class="sxs-lookup"><span data-stu-id="d39c5-132">The generated file is saved as _HelloSvcutil/ServiceReference/Reference.cs_.</span></span> <span data-ttu-id="d39c5-133">La herramienta _dotnet_svcutil_ también agrega al proyecto los paquetes de WCF adecuados que necesita el código de proxy como referencias del paquete.</span><span class="sxs-lookup"><span data-stu-id="d39c5-133">The _dotnet-svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

## <a name="using-the-service-reference"></a><span data-ttu-id="d39c5-134">Uso de la referencia de servicio</span><span class="sxs-lookup"><span data-stu-id="d39c5-134">Using the Service Reference</span></span>

1. <span data-ttu-id="d39c5-135">Restaure los paquetes de WCF mediante el comando [`dotnet restore`](../tools/dotnet-restore.md) como sigue:</span><span class="sxs-lookup"><span data-stu-id="d39c5-135">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

2. <span data-ttu-id="d39c5-136">Busque el nombre de la clase de cliente y la operación que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="d39c5-136">Find the name of the client class and operation you want to use.</span></span> <span data-ttu-id="d39c5-137">`Reference.cs` contendrá una clase que se hereda de `System.ServiceModel.ClientBase`, con métodos que pueden usarse para llamar a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="d39c5-137">`Reference.cs` will contain a class that inherits from `System.ServiceModel.ClientBase`, with methods that can be used to call operations on the service.</span></span> <span data-ttu-id="d39c5-138">En este ejemplo, quiere llamar a la operación _Hello_ del servicio _SayHello_.</span><span class="sxs-lookup"><span data-stu-id="d39c5-138">In this example, you want to call the _SayHello_ service's _Hello_ operation.</span></span> <span data-ttu-id="d39c5-139">`ServiceReference.SayHelloClient` es el nombre de la clase de cliente, y tiene un método llamado `HelloAsync` que se puede usar para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="d39c5-139">`ServiceReference.SayHelloClient` is the name of the client class, and has a method called `HelloAsync` that can be used to call the operation.</span></span>

3. <span data-ttu-id="d39c5-140">Abra el archivo `Startup.cs` en el editor y agregue una directiva `using` al espacio de nombres de la referencia de servicio en la parte superior:</span><span class="sxs-lookup"><span data-stu-id="d39c5-140">Open the `Startup.cs` file in your editor, and add a `using` directive for the service reference namespace at the top:</span></span>

    ```csharp
    using ServiceReference;
    ```

4. <span data-ttu-id="d39c5-141">Edite el método `Configure` para invocar el servicio web.</span><span class="sxs-lookup"><span data-stu-id="d39c5-141">Edit the `Configure` method to invoke the web service.</span></span> <span data-ttu-id="d39c5-142">Para ello, cree una instancia de la clase que se hereda de `ClientBase` y llame al método en el objeto de cliente:</span><span class="sxs-lookup"><span data-stu-id="d39c5-142">You do this by creating an instance of the class that inherits from `ClientBase` and calling the method on the client object:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
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

5. <span data-ttu-id="d39c5-143">Ejecute la aplicación con el comando [`dotnet run`](../tools/dotnet-run.md) como sigue:</span><span class="sxs-lookup"><span data-stu-id="d39c5-143">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

    ```dotnetcli
    dotnet run
    ```

6. <span data-ttu-id="d39c5-144">Vaya a la dirección URL indicada en la consola (por ejemplo, `http://localhost:5000`) en el explorador web.</span><span class="sxs-lookup"><span data-stu-id="d39c5-144">Navigate to the URL listed in the console (for example, `http://localhost:5000`) in your web browser.</span></span>

<span data-ttu-id="d39c5-145">Debería ver los siguientes resultados: "Hello dotnet-svcutil!"</span><span class="sxs-lookup"><span data-stu-id="d39c5-145">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="d39c5-146">Para obtener una descripción detallada de los parámetros de la herramienta `dotnet-svcutil`, invoque la herramienta pasando el parámetro de ayuda del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="d39c5-146">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

# <a name="dotnet-svcutil-2x"></a>[<span data-ttu-id="d39c5-147">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-147">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1x"></a>[<span data-ttu-id="d39c5-148">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="d39c5-148">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a><span data-ttu-id="d39c5-149">Preguntas y comentarios</span><span class="sxs-lookup"><span data-stu-id="d39c5-149">Feedback & questions</span></span>

<span data-ttu-id="d39c5-150">Si tiene preguntas o comentarios, [abra un problema en GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="d39c5-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="d39c5-151">También puede revisar las preguntas o problemas que ya se han planteado en el [repositorio de WCF en GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="d39c5-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

## <a name="release-notes"></a><span data-ttu-id="d39c5-152">Notas de la versión</span><span class="sxs-lookup"><span data-stu-id="d39c5-152">Release notes</span></span>

- <span data-ttu-id="d39c5-153">Eche un vistazo a las [notas de la versión](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) para obtener información actualizada sobre la versión, incluidos los problemas conocidos.</span><span class="sxs-lookup"><span data-stu-id="d39c5-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

## <a name="information"></a><span data-ttu-id="d39c5-154">Información</span><span class="sxs-lookup"><span data-stu-id="d39c5-154">Information</span></span>

- [<span data-ttu-id="d39c5-155">Paquete NuGet svcutil dotnet</span><span class="sxs-lookup"><span data-stu-id="d39c5-155">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)

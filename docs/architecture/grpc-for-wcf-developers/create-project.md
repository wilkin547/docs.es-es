---
title: Creación de un nuevo ASP.NET Core proyecto de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo crear un proyecto de gRPC con Visual Studio o desde la línea de comandos.
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967890"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="06591-103">Creación de un nuevo proyecto gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="06591-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="06591-104">.NET Core incluye una eficaz herramienta de la CLI, `dotnet`, que permite crear y administrar proyectos y soluciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="06591-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="06591-105">La herramienta está estrechamente integrada con Visual Studio, por lo que todo está disponible a través de la interfaz GUI familiar.</span><span class="sxs-lookup"><span data-stu-id="06591-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="06591-106">En este capítulo se muestran las dos maneras de crear un nuevo proyecto de gRPC ASP.NET Core: en primer lugar con Visual Studio, con el CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="06591-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="06591-107">Crear el proyecto mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06591-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06591-108">Para desarrollar una aplicación ASP.NET Core 3,0, necesita Visual Studio 2019,3 o posterior con la carga de trabajo de **desarrollo web y ASP.net** instalada.</span><span class="sxs-lookup"><span data-stu-id="06591-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="06591-109">Cree una solución vacía denominada **Traders** a partir de la plantilla de *solución en blanco* .</span><span class="sxs-lookup"><span data-stu-id="06591-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="06591-110">Agregue una carpeta de soluciones llamada `src`, haga clic con el botón derecho en la carpeta y elija **agregar** > **nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="06591-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="06591-111">Escriba `grpc` en el cuadro de búsqueda de plantillas y debería ver una plantilla de proyecto denominada `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="06591-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![Cuadro de diálogo Agregar nuevo proyecto que muestra la plantilla de proyecto de servicio gRPC](media/create-project/new-grpc-project.png)

<span data-ttu-id="06591-113">Haga clic en **siguiente** para continuar con el cuadro de diálogo **configurar proyecto** , asigne al proyecto el nombre `TraderSys.Portfolios`y agregue un subdirectorio `src` a la **Ubicación**.</span><span class="sxs-lookup"><span data-stu-id="06591-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Cuadro de diálogo Configurar proyecto](media/create-project/configure-project.png)

<span data-ttu-id="06591-115">Haga clic en **siguiente** para continuar en el cuadro de diálogo **nuevo proyecto de gRPC** .</span><span class="sxs-lookup"><span data-stu-id="06591-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![Cuadro de diálogo nuevo proyecto de gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="06591-117">En la actualidad, hay opciones limitadas para la creación del servicio.</span><span class="sxs-lookup"><span data-stu-id="06591-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="06591-118">Docker se introducirá más adelante en el libro, de modo que deje la casilla desactivada por ahora y simplemente haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="06591-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="06591-119">Se genera el primer ASP.NET Core 3,0 gRPC proyecto y se agrega a la solución.</span><span class="sxs-lookup"><span data-stu-id="06591-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="06591-120">Si no desea saber cómo trabajar con el `dotnet CLI`, vaya a la sección [limpieza del código de ejemplo](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="06591-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="06591-121">Cree el proyecto mediante el CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="06591-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="06591-122">En esta sección se describe la creación de soluciones y proyectos desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="06591-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="06591-123">Cree la solución como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="06591-123">Create the solution as shown below.</span></span> <span data-ttu-id="06591-124">La marca `-o` (o `--output`) especifica el directorio de salida, que se creará en el directorio actual si no existe.</span><span class="sxs-lookup"><span data-stu-id="06591-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="06591-125">La solución tendrá el mismo nombre que el directorio, es decir, `TraderSys.sln`. Puede proporcionar un nombre diferente mediante la marca `-n` (o `--name`).</span><span class="sxs-lookup"><span data-stu-id="06591-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="06591-126">ASP.NET Core 3,0 incluye una plantilla de CLI para gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="06591-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="06591-127">Cree el nuevo proyecto con esta plantilla y colóquelo en un subdirectorio de `src` como la Convención de ASP.NET Core proyectos.</span><span class="sxs-lookup"><span data-stu-id="06591-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="06591-128">El proyecto se denominará después del directorio (es decir, `TraderSys.Portfolios.csproj`) a menos que especifique otro nombre con la marca `-n`.</span><span class="sxs-lookup"><span data-stu-id="06591-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="06591-129">Por último, agregue el proyecto a la solución con el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="06591-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="06591-130">Dado que el directorio especificado solo contiene un único archivo de `.csproj`, puede empezar a especificar solo el directorio para guardar escribiendo.</span><span class="sxs-lookup"><span data-stu-id="06591-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="06591-131">Ahora puede abrir esta solución en Visual Studio 2019, Visual Studio Code o cualquier editor que prefiera.</span><span class="sxs-lookup"><span data-stu-id="06591-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="06591-132">Limpieza del código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="06591-132">Clean up the example code</span></span>

<span data-ttu-id="06591-133">Ahora ha creado un servicio de ejemplo con la plantilla gRPC, que se ha revisado anteriormente en el libro.</span><span class="sxs-lookup"><span data-stu-id="06591-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="06591-134">Esto no es útil en nuestro contexto de transacciones bursátiles, por lo que editaremos cosas para nuestro primer proyecto.</span><span class="sxs-lookup"><span data-stu-id="06591-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="06591-135">Cambiar el nombre y editar el archivo proto</span><span class="sxs-lookup"><span data-stu-id="06591-135">Rename and edit the proto file</span></span>

<span data-ttu-id="06591-136">Continúe y cambie el nombre del archivo de `Protos/greet.proto` a `Protos/portfolios.proto` y ábralo en el editor.</span><span class="sxs-lookup"><span data-stu-id="06591-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="06591-137">Elimine todo lo que haya después de la línea de `package`, cambie los nombres de `option csharp_namespace`, `package` y `service` y quite el servicio de `SayHello` predeterminado, de modo que el código tenga este aspecto.</span><span class="sxs-lookup"><span data-stu-id="06591-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="06591-138">La plantilla no agrega la parte del espacio de nombres `Protos` de forma predeterminada, pero al agregarla es más fácil mantener las clases generadas por gRPC y sus propias clases separadas claramente en el código.</span><span class="sxs-lookup"><span data-stu-id="06591-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="06591-139">Si cambia el nombre del archivo de `greet.proto` en un entorno de desarrollo integrado (IDE) como Visual Studio, se actualiza automáticamente una referencia a este archivo en el archivo de `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="06591-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="06591-140">Pero en otro editor, como Visual Studio Code, esta referencia no se actualiza automáticamente, por lo que debe editar el archivo de proyecto manualmente.</span><span class="sxs-lookup"><span data-stu-id="06591-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="06591-141">En los destinos de compilación de gRPC, hay un elemento `Protobuf` elemento que le permite especificar qué archivos de `.proto` se deben compilar y qué forma de generación de código es necesaria (es decir, "servidor" o "cliente").</span><span class="sxs-lookup"><span data-stu-id="06591-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="06591-142">Cambiar el nombre de la clase GreeterService</span><span class="sxs-lookup"><span data-stu-id="06591-142">Rename the GreeterService class</span></span>

<span data-ttu-id="06591-143">La clase `GreeterService` se encuentra en la carpeta `Services` y hereda de `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="06591-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="06591-144">Cambie el nombre a `PortfolioService` y cambie la clase base a `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="06591-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="06591-145">Elimine los métodos de `override`.</span><span class="sxs-lookup"><span data-stu-id="06591-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="06591-146">Hay una referencia a la clase `GreeterService` en el método `Configure` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="06591-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="06591-147">Si usó la refactorización para cambiar el nombre de la clase, esta referencia debería haberse actualizado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="06591-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="06591-148">Sin embargo, si no lo ha hecho, debe editarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="06591-148">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="06591-149">En la siguiente sección, agregaremos funcionalidad a este nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="06591-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="06591-150">[Anterior](migrate-wcf-to-grpc.md)
>[Siguiente](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="06591-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>

---
title: Creación de un nuevo ASP.NET Core proyecto de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo crear un proyecto de gRPC con Visual Studio o la línea de comandos.
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711448"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="865e3-103">Creación de un nuevo proyecto gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="865e3-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="865e3-104">La SDK de .NET Core incluye una eficaz herramienta de la CLI, `dotnet`, que permite crear y administrar proyectos y soluciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="865e3-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="865e3-105">El SDK está estrechamente integrado con Visual Studio, por lo que todo está también disponible a través de la conocida interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="865e3-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="865e3-106">En este capítulo se muestran las dos maneras de crear un nuevo proyecto de gRPC de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="865e3-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="865e3-107">Crear el proyecto mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="865e3-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="865e3-108">Para desarrollar cualquier aplicación ASP.NET Core 3,0, necesita Visual Studio 2019 16,3 o posterior, con la carga de trabajo de **desarrollo web y ASP.net** instalada.</span><span class="sxs-lookup"><span data-stu-id="865e3-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="865e3-109">Cree una solución vacía denominada **Traders** a partir de la plantilla de *solución en blanco* .</span><span class="sxs-lookup"><span data-stu-id="865e3-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="865e3-110">Agregue una carpeta de soluciones llamada `src`.</span><span class="sxs-lookup"><span data-stu-id="865e3-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="865e3-111">A continuación, haga clic con el botón derecho en la carpeta y elija **agregar** > **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="865e3-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="865e3-112">Escriba `grpc` en el cuadro de búsqueda de plantillas y debería ver una plantilla de proyecto denominada `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="865e3-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Captura de pantalla del cuadro de diálogo Agregar un nuevo proyecto](media/create-project/new-grpc-project.png)

<span data-ttu-id="865e3-114">Seleccione **siguiente** para continuar en el cuadro de diálogo **configurar el nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="865e3-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="865e3-115">Asigne al proyecto el nombre `TraderSys.Portfolios`y agregue un subdirectorio `src` a la **Ubicación**.</span><span class="sxs-lookup"><span data-stu-id="865e3-115">Name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Captura de pantalla del cuadro de diálogo Configurar el nuevo proyecto](media/create-project/configure-project.png)

<span data-ttu-id="865e3-117">Seleccione **siguiente** para continuar con el cuadro de diálogo **crear un nuevo servicio de gRPC** .</span><span class="sxs-lookup"><span data-stu-id="865e3-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Captura de pantalla del cuadro de diálogo crear un nuevo servicio gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="865e3-119">En la actualidad, tiene opciones limitadas para la creación del servicio.</span><span class="sxs-lookup"><span data-stu-id="865e3-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="865e3-120">Docker se introducirá más adelante, por lo que, por ahora, deje esa opción desactivada.</span><span class="sxs-lookup"><span data-stu-id="865e3-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="865e3-121">Simplemente seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="865e3-121">Just select **Create**.</span></span> <span data-ttu-id="865e3-122">Se genera el primer ASP.NET Core 3,0 gRPC proyecto y se agrega a la solución.</span><span class="sxs-lookup"><span data-stu-id="865e3-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="865e3-123">Si no desea saber cómo trabajar con el `dotnet CLI`, vaya a la sección [limpieza del código de ejemplo](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="865e3-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="865e3-124">Cree el proyecto mediante el CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="865e3-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="865e3-125">En esta sección se describe la creación de soluciones y proyectos desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="865e3-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="865e3-126">Cree la solución como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="865e3-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="865e3-127">La marca `-o` (o `--output`) especifica el directorio de salida, que se crea en el directorio actual si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="865e3-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="865e3-128">La solución tiene el mismo nombre que el directorio: `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="865e3-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="865e3-129">Puede proporcionar un nombre diferente mediante la marca `-n` (o `--name`).</span><span class="sxs-lookup"><span data-stu-id="865e3-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="865e3-130">ASP.NET Core 3,0 incluye una plantilla de CLI para gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="865e3-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="865e3-131">Cree el nuevo proyecto con esta plantilla y colóquelo en un subdirectorio de `src` como se usa para proyectos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="865e3-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="865e3-132">El nombre del proyecto se encuentra después del directorio (`TraderSys.Portfolios.csproj`), a menos que especifique otro nombre con la marca `-n`.</span><span class="sxs-lookup"><span data-stu-id="865e3-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="865e3-133">Por último, agregue el proyecto a la solución mediante el comando `dotnet sln`:</span><span class="sxs-lookup"><span data-stu-id="865e3-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="865e3-134">Dado que el directorio concreto solo contiene un único archivo de `.csproj`, puede especificar solo el directorio para guardar escribiendo.</span><span class="sxs-lookup"><span data-stu-id="865e3-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="865e3-135">Ahora puede abrir esta solución en Visual Studio 2019, Visual Studio Code o cualquier editor que prefiera.</span><span class="sxs-lookup"><span data-stu-id="865e3-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="865e3-136">Limpieza del código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="865e3-136">Clean up the example code</span></span>

<span data-ttu-id="865e3-137">Ahora ha creado un servicio de ejemplo con la plantilla gRPC, que se ha revisado anteriormente en el libro.</span><span class="sxs-lookup"><span data-stu-id="865e3-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="865e3-138">Esto no es útil en nuestro contexto de transacciones bursátiles, por lo que editaremos cosas para nuestro primer proyecto.</span><span class="sxs-lookup"><span data-stu-id="865e3-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="865e3-139">Cambiar el nombre y editar el archivo proto</span><span class="sxs-lookup"><span data-stu-id="865e3-139">Rename and edit the proto file</span></span>

<span data-ttu-id="865e3-140">Continúe y cambie el nombre del archivo de `Protos/greet.proto` a `Protos/portfolios.proto`y ábralo en el editor.</span><span class="sxs-lookup"><span data-stu-id="865e3-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="865e3-141">Elimine todo después de la línea de `package`.</span><span class="sxs-lookup"><span data-stu-id="865e3-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="865e3-142">A continuación, cambie los nombres de `option csharp_namespace`, `package` y `service` y quite el servicio de `SayHello` predeterminado.</span><span class="sxs-lookup"><span data-stu-id="865e3-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="865e3-143">El código tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="865e3-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="865e3-144">La plantilla no agrega la parte del espacio de nombres `Protos` de forma predeterminada, pero al agregarla es más fácil mantener las clases generadas por gRPC y sus propias clases separadas claramente en el código.</span><span class="sxs-lookup"><span data-stu-id="865e3-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="865e3-145">Si cambia el nombre del archivo de `greet.proto` en un entorno de desarrollo integrado (IDE) como Visual Studio, se actualiza automáticamente una referencia a este archivo en el archivo de `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="865e3-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="865e3-146">Pero en otro editor, como Visual Studio Code, esta referencia no se actualiza automáticamente, por lo que debe editar el archivo de proyecto manualmente.</span><span class="sxs-lookup"><span data-stu-id="865e3-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="865e3-147">En los destinos de compilación de gRPC, hay un elemento `Protobuf` elemento que le permite especificar qué archivos de `.proto` se deben compilar y qué forma de generación de código es necesaria (es decir, "servidor" o "cliente").</span><span class="sxs-lookup"><span data-stu-id="865e3-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="865e3-148">Cambiar el nombre de la clase `GreeterService`</span><span class="sxs-lookup"><span data-stu-id="865e3-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="865e3-149">La clase `GreeterService` se encuentra en la carpeta `Services` y hereda de `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="865e3-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="865e3-150">Cambie el nombre a `PortfolioService`y cambie la clase base a `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="865e3-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="865e3-151">Elimine los métodos de `override`.</span><span class="sxs-lookup"><span data-stu-id="865e3-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="865e3-152">Hay una referencia a la clase `GreeterService` en el método `Configure` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="865e3-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="865e3-153">Si usó la refactorización para cambiar el nombre de la clase, esta referencia debería haberse actualizado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="865e3-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="865e3-154">Sin embargo, si no lo ha hecho, debe editarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="865e3-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="865e3-155">En la siguiente sección, agregaremos funcionalidad a este nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="865e3-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="865e3-156">[Anterior](migrate-wcf-to-grpc.md)
>[Siguiente](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="865e3-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>

---
title: Creación de un nuevo ASP.NET Core proyecto de gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo crear un proyecto de gRPC con Visual Studio o la línea de comandos.
ms.date: 12/15/2020
ms.openlocfilehash: 960725a9507797f43b2c15283e384b0ad827c2b1
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938666"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="4f3d2-103">Creación de un nuevo proyecto gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4f3d2-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="4f3d2-104">El SDK de .NET incluye una eficaz herramienta de la CLI, `dotnet` , que permite crear y administrar proyectos y soluciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-104">The .NET SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="4f3d2-105">El SDK está estrechamente integrado con Visual Studio, por lo que todo está también disponible a través de la conocida interfaz gráfica de usuario.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="4f3d2-106">En este capítulo se muestran las dos maneras de crear un nuevo proyecto de gRPC de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="4f3d2-107">Crear el proyecto mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4f3d2-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f3d2-108">Para desarrollar cualquier aplicación ASP.NET Core 5,0, necesita la versión 16,3 de Visual Studio 2019 o posterior, con la carga de trabajo de **desarrollo web y ASP.net** instalada.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-108">To develop any ASP.NET Core 5.0 app, you need Visual Studio 2019 version 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="4f3d2-109">Cree una solución vacía denominada **Traders** a partir de la plantilla de *solución en blanco* .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="4f3d2-110">Agregue una carpeta de soluciones denominada `src` .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="4f3d2-111">A continuación, haga clic con el botón derecho en la carpeta y elija **Agregar**  >  **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="4f3d2-112">Escriba `grpc` en el cuadro de búsqueda de plantillas y debería ver una plantilla de proyecto denominada `gRPC Service` .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Captura de pantalla del cuadro de diálogo Agregar un nuevo proyecto](media/create-project/new-grpc-project.png)

<span data-ttu-id="4f3d2-114">Seleccione **siguiente** para continuar en el cuadro de diálogo **configurar el nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="4f3d2-115">Asigne un nombre al proyecto `TraderSys.Portfolios` y agregue un `src` subdirectorio a la **Ubicación**.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-115">Name the project `TraderSys.Portfolios` and add an `src` subdirectory to the **Location**.</span></span>

![Captura de pantalla del cuadro de diálogo Configurar el nuevo proyecto](media/create-project/configure-project.png)

<span data-ttu-id="4f3d2-117">Seleccione **siguiente** para continuar con el cuadro de diálogo **crear un nuevo servicio de gRPC** .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Captura de pantalla del cuadro de diálogo crear un nuevo servicio gRPC](media/create-project/create-new-grpc-service-v2.png)

<span data-ttu-id="4f3d2-119">En la actualidad, tiene opciones limitadas para la creación del servicio.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="4f3d2-120">Docker se introducirá más adelante, por lo que, por ahora, deje esa opción desactivada.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="4f3d2-121">Simplemente seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-121">Just select **Create**.</span></span> <span data-ttu-id="4f3d2-122">Se genera el primer ASP.NET Core 5,0 gRPC proyecto y se agrega a la solución.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-122">Your first ASP.NET Core 5.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="4f3d2-123">Si no desea saber cómo trabajar con el `dotnet CLI` , vaya a la sección [limpieza del código de ejemplo](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-cli"></a><span data-ttu-id="4f3d2-124">Creación del proyecto mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="4f3d2-124">Create the project by using the .NET CLI</span></span>

<span data-ttu-id="4f3d2-125">En esta sección se describe la creación de soluciones y proyectos desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="4f3d2-126">Cree la solución como se muestra en el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="4f3d2-127">La `-o` marca (o `--output` ) especifica el directorio de salida, que se crea en el directorio actual si aún no existe.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="4f3d2-128">La solución tiene el mismo nombre que el directorio: `TraderSys.sln` .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="4f3d2-129">Puede proporcionar un nombre diferente mediante la `-n` marca (o `--name` ).</span><span class="sxs-lookup"><span data-stu-id="4f3d2-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="4f3d2-130">ASP.NET Core 5,0 incluye una plantilla de CLI para gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-130">ASP.NET Core 5.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="4f3d2-131">Cree el nuevo proyecto con esta plantilla y colóquelo en un `src` subdirectorio, tal como se ha convencional para proyectos de ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="4f3d2-132">El nombre del proyecto se encuentra después del directorio ( `TraderSys.Portfolios.csproj` ), a menos que especifique otro nombre con la `-n` marca.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="4f3d2-133">Por último, agregue el proyecto a la solución mediante el `dotnet sln` comando:</span><span class="sxs-lookup"><span data-stu-id="4f3d2-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="4f3d2-134">Dado que el directorio concreto solo contiene un único `.csproj` archivo, puede especificar solo el directorio para guardar escribiendo.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="4f3d2-135">Ahora puede abrir esta solución en Visual Studio 2019, Visual Studio Code o cualquier editor que prefiera.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="4f3d2-136">Limpieza del código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f3d2-136">Clean up the example code</span></span>

<span data-ttu-id="4f3d2-137">Ahora ha creado un servicio de ejemplo con la plantilla gRPC, que se ha revisado anteriormente en el libro.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="4f3d2-138">Este código no es útil en nuestro contexto de transacciones bursátiles, por lo que editaremos cosas para nuestro primer proyecto.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-138">This code isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="4f3d2-139">Cambiar el nombre y editar el archivo proto</span><span class="sxs-lookup"><span data-stu-id="4f3d2-139">Rename and edit the proto file</span></span>

<span data-ttu-id="4f3d2-140">Continúe y cambie el nombre del `Protos/greet.proto` archivo a `Protos/portfolios.proto` y ábralo en el editor.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="4f3d2-141">Elimine todo el resto de la `package` línea.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="4f3d2-142">A continuación, cambie los `option csharp_namespace` `package` nombres, y `service` , y quite el `SayHello` servicio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="4f3d2-143">El código tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="4f3d2-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="4f3d2-144">La plantilla no agrega la `Protos` parte del espacio de nombres de forma predeterminada, pero la adición facilita la tarea de mantener las clases generadas por gRPC y sus propias clases separadas claramente en el código.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="4f3d2-145">Si cambia el nombre del `greet.proto` archivo en un entorno de desarrollo integrado (IDE) como Visual Studio, se actualiza automáticamente una referencia a este archivo en el `.csproj` archivo.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="4f3d2-146">Pero en otro editor, como Visual Studio Code, esta referencia no se actualiza automáticamente, por lo que debe editar el archivo de proyecto manualmente.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="4f3d2-147">En los destinos de compilación gRPC, hay un `Protobuf` elemento Item que le permite especificar qué `.proto` archivos se deben compilar y qué forma de generación de código es necesaria (es decir, "Server" o "Client").</span><span class="sxs-lookup"><span data-stu-id="4f3d2-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="4f3d2-148">Cambiar el nombre de la `GreeterService` clase</span><span class="sxs-lookup"><span data-stu-id="4f3d2-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="4f3d2-149">La `GreeterService` clase se encuentra en la `Services` carpeta y hereda de `Greeter.GreeterBase` .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="4f3d2-150">Cambie su nombre a `PortfolioService` y cambie la clase base a `Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="4f3d2-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="4f3d2-151">Elimine los `override` métodos.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="4f3d2-152">Hay una referencia a la `GreeterService` clase en el `Configure` método en la `Startup` clase.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="4f3d2-153">Si usó la refactorización para cambiar el nombre de la clase, esta referencia debería haberse actualizado automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="4f3d2-154">Sin embargo, si no lo ha hecho, debe editarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="4f3d2-155">En la siguiente sección, agregaremos funcionalidad a este nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="4f3d2-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4f3d2-156">[Anterior](migrate-wcf-to-grpc.md)
>[Siguiente](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="4f3d2-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>

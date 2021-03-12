---
title: Ejemplo de migración de eShop a ASP.NET Core
description: Un tutorial de migración de una aplicación de ASP.NET MVC existente a ASP.NET Core, mediante una aplicación de la tienda en línea de ejemplo como referencia.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 498eb3b11c44381ff6d261b37caed15a2698b166
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605261"
---
# <a name="example-migration-of-eshop-to-aspnet-core"></a><span data-ttu-id="9ef1e-103">Ejemplo de migración de eShop a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9ef1e-103">Example migration of eShop to ASP.NET Core</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9ef1e-104">En este capítulo, verá cómo migrar una aplicación .NET Framework a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-104">In this chapter, you'll see how to migrate a .NET Framework app to .NET Core.</span></span> <span data-ttu-id="9ef1e-105">En el capítulo se examina una aplicación de la tienda en línea de ejemplo escrita para ASP.NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-105">The chapter examines a sample online store app written for ASP.NET 5.0.</span></span> <span data-ttu-id="9ef1e-106">La aplicación usará muchos de los conceptos y herramientas descritos anteriormente en este libro.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-106">The app will use many of the concepts and tools described earlier in this book.</span></span> <span data-ttu-id="9ef1e-107">Encontrará la aplicación de punto de partida en el [repositorio de github de *eShopModernizing*](https://github.com/dotnet-architecture/eShopModernizing).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-107">You'll find the starting point app in the [*eShopModernizing* GitHub repository](https://github.com/dotnet-architecture/eShopModernizing).</span></span> <span data-ttu-id="9ef1e-108">Hay varias aplicaciones de punto de partida diferentes.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-108">There are several different starting point apps.</span></span> <span data-ttu-id="9ef1e-109">Este capítulo se centra en el *eShopLegacyMVCSolution*.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-109">This chapter focuses on the *eShopLegacyMVCSolution*.</span></span>

<span data-ttu-id="9ef1e-110">La versión inicial del proyecto se muestra en la figura 4-1.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-110">The initial version of the project is shown in Figure 4-1.</span></span> <span data-ttu-id="9ef1e-111">Es una aplicación ASP.NET MVC 5 bastante estándar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-111">It's a fairly standard ASP.NET MVC 5 app.</span></span>

![Figura 4-1](media/Figure4-1.png)

<span data-ttu-id="9ef1e-113">**Figura 4-1.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-113">**Figure 4-1.**</span></span> <span data-ttu-id="9ef1e-114">Estructura del proyecto de ejemplo *eShopModernizing* MVC.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-114">The *eShopModernizing* MVC sample project structure.</span></span>

<span data-ttu-id="9ef1e-115">En este capítulo se muestra cómo realizar muchos de los pasos de actualización a mano.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-115">This chapter demonstrates how to perform many of the upgrade steps by hand.</span></span> <span data-ttu-id="9ef1e-116">Como alternativa, puede usar la [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant) para realizar muchos de los pasos iniciales, como la conversión del archivo de proyecto, el cambio de la plataforma de destino y la actualización de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-116">Alternatively, you can use the [.NET Upgrade Assistant tool](https://aka.ms/dotnet-upgrade-assistant) to perform many of the initial steps, like converting the project file, changing the target framework, and updating NuGet packages.</span></span>

## <a name="run-apiport-to-identify-problematic-apis"></a><span data-ttu-id="9ef1e-117">Ejecución de *ApiPort* para identificar API problemáticas</span><span class="sxs-lookup"><span data-stu-id="9ef1e-117">Run *ApiPort* to identify problematic APIs</span></span>

<span data-ttu-id="9ef1e-118">El primer paso para preparar la migración es ejecutar la herramienta *ApiPort* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-118">The first step in preparing to migrate is to run the *ApiPort* tool.</span></span> <span data-ttu-id="9ef1e-119">La herramienta identifica cuántas API de .NET Framework llama la aplicación y cuántas de ellas tienen .NET Standard o equivalentes de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-119">The tool identifies how many .NET Framework APIs the app calls and how many of these have .NET Standard or .NET Core equivalents.</span></span> <span data-ttu-id="9ef1e-120">Céntrese principalmente en la lógica de su propia aplicación, no en las dependencias de terceros, y preste atención a las `System.Web` dependencias que se deben migrar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-120">Focus primarily on your own app's logic, not third-party dependencies, and pay attention to `System.Web` dependencies that will need to be ported.</span></span> <span data-ttu-id="9ef1e-121">La herramienta ApiPort se presentó en el último capítulo sobre cómo [comprender y actualizar las dependencias](understand-update-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-121">The ApiPort tool was introduced in the last chapter on [understanding and updating dependencies](understand-update-dependencies.md).</span></span>

<span data-ttu-id="9ef1e-122">Después de [instalar y configurar la herramienta *ApiPort*](../../standard/analyzers/portability-analyzer.md), ejecute el análisis desde dentro de Visual Studio, como se muestra en la figura 4-2.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-122">After [installing and configuring the *ApiPort* tool](../../standard/analyzers/portability-analyzer.md), run the analysis from within Visual Studio, as shown in Figure 4-2.</span></span>

![Figura 4-2](media/Figure4-2.png)

<span data-ttu-id="9ef1e-124">**Figura 4-2.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-124">**Figure 4-2.**</span></span> <span data-ttu-id="9ef1e-125">Analice la portabilidad de los ensamblados en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-125">Analyze assembly portability in Visual Studio.</span></span>

<span data-ttu-id="9ef1e-126">Elija el ensamblado del proyecto web en la carpeta *bin* del proyecto, como se muestra en la figura 4-3.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-126">Choose the web project's assembly from the project's *bin* folder, as shown in Figure 4-3.</span></span>

![Figura 4-3](media/Figure4-3.png)

<span data-ttu-id="9ef1e-128">**Figura 4-3.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-128">**Figure 4-3.**</span></span> <span data-ttu-id="9ef1e-129">Elija el ensamblado web del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-129">Choose the project's web assembly.</span></span>

<span data-ttu-id="9ef1e-130">Si la solución incluye varios proyectos, puede elegirlos todos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-130">If your solution includes several projects, you can choose all of them.</span></span> <span data-ttu-id="9ef1e-131">El ejemplo de *eShop* incluye solo un proyecto de MVC.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-131">The *eShop* sample includes just a single MVC project.</span></span>

<span data-ttu-id="9ef1e-132">Una vez generado el informe, abra el archivo y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-132">Once the report is generated, open the file and review the results.</span></span> <span data-ttu-id="9ef1e-133">El Resumen proporciona una vista de alto nivel del porcentaje de llamadas .NET Framework que la aplicación está realizando con versiones compatibles.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-133">The summary provides a high-level view of what percentage of .NET Framework calls your app is making have compatible versions.</span></span> <span data-ttu-id="9ef1e-134">En la figura 4-4 se muestra el resumen del proyecto de *eShop* MVC.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-134">Figure 4-4 shows the summary for the *eShop* MVC project.</span></span>

![Figura 4-4](media/Figure4-4.png)

<span data-ttu-id="9ef1e-136">**Figura 4-4.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-136">**Figure 4-4.**</span></span> <span data-ttu-id="9ef1e-137">Resumen de ApiPort.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-137">ApiPort summary.</span></span>

<span data-ttu-id="9ef1e-138">Para esta aplicación, el 80 por ciento de las llamadas .NET Framework son compatibles.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-138">For this app, about 80 percent of the .NET Framework calls are compatible.</span></span> <span data-ttu-id="9ef1e-139">el 20 por ciento de las llamadas deben solucionarse durante el proceso de portabilidad.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-139">20 percent of the calls need to be addressed during the porting process.</span></span> <span data-ttu-id="9ef1e-140">La visualización de los detalles revela que todas las llamadas incompatibles forman parte de `System.Web` , que es una incompatibilidad esperada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-140">Viewing the details reveals that all of the incompatible calls are part of `System.Web`, which is an expected incompatibility.</span></span> <span data-ttu-id="9ef1e-141">Las dependencias de las `System.Web` llamadas se dirigirán cuando se migren los controladores de la aplicación y las clases relacionadas en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-141">The dependencies on `System.Web` calls will be addressed when the app's controllers and related classes are migrated in a later step.</span></span> <span data-ttu-id="9ef1e-142">En la figura 4-5 se enumeran algunos de los tipos específicos que se encuentran en la herramienta:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-142">Figure 4-5 lists some of the specific types found by the tool:</span></span>

![Figura 4-5](media/Figure4-5.png)

<span data-ttu-id="9ef1e-144">**Figura 4-5.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-144">**Figure 4-5.**</span></span> <span data-ttu-id="9ef1e-145">*ApiPort* detalles de tipo incompatible.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-145">*ApiPort* incompatible type details.</span></span>

<span data-ttu-id="9ef1e-146">La mayoría de los tipos incompatibles hacen referencia a `Controller` y varios atributos relacionados que tienen equivalentes en ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-146">Most of the incompatible types refer to `Controller` and various related attributes that have equivalents in ASP.NET Core.</span></span>

## <a name="update-project-files-and-nuget-reference-syntax"></a><span data-ttu-id="9ef1e-147">Actualizar archivos de proyecto y sintaxis de referencia de NuGet</span><span class="sxs-lookup"><span data-stu-id="9ef1e-147">Update project files and NuGet reference syntax</span></span>

<span data-ttu-id="9ef1e-148">A continuación, migre de la estructura del archivo *. csproj* anterior a la estructura más reciente y más sencilla introducida con .net Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-148">Next, migrate from the older *.csproj* file structure to the newer, simpler structure introduced with .NET Core.</span></span> <span data-ttu-id="9ef1e-149">Al hacerlo, también migrará de mediante un archivo *packages.config* para que las referencias de NuGet usen `<PackageReference>` elementos del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-149">In doing so, you'll also migrate from using a *packages.config* file for NuGet references to using `<PackageReference>` elements in the project file.</span></span>

<span data-ttu-id="9ef1e-150">El archivo *eShopLegacyMVC. csproj* del proyecto original tiene 418 líneas de longitud.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-150">The original project's *eShopLegacyMVC.csproj* file is 418 lines long.</span></span> <span data-ttu-id="9ef1e-151">En la figura 4-6 se muestra un ejemplo del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-151">A sample of the project file is shown in Figure 4-6.</span></span> <span data-ttu-id="9ef1e-152">Para ofrecer una idea de su tamaño y complejidad generales, el lado derecho de la imagen contiene una vista en miniatura del archivo completo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-152">To offer a sense of its overall size and complexity, the right side of the image contains a miniature view of the entire file.</span></span>

![Figura 4-6](media/Figure4-6.png)

<span data-ttu-id="9ef1e-154">**Figura 4-6.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-154">**Figure 4-6.**</span></span> <span data-ttu-id="9ef1e-155">Estructura del archivo *eShopLegacyMVC. csproj* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-155">The *eShopLegacyMVC.csproj* file structure.</span></span>

<span data-ttu-id="9ef1e-156">Una forma habitual de crear un nuevo archivo de proyecto para un proyecto de ASP.net existente consiste en crear una nueva aplicación de ASP.net Core con `dotnet new` o **archivo**  >  **nuevo**  >  **proyecto** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-156">A common way to create a new project file for an existing ASP.NET project is to create a new ASP.NET Core app using `dotnet new` or **File** > **New** > **Project** in Visual Studio.</span></span> <span data-ttu-id="9ef1e-157">Después, los archivos se pueden copiar del proyecto anterior al nuevo para completar la migración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-157">Then files can be copied from the old project to the new one to complete the migration.</span></span>

<span data-ttu-id="9ef1e-158">Además del archivo de proyecto de C#, las dependencias de NuGet se almacenan en un archivo de *packages.config* de línea de 45 independiente, como se muestra en la figura 4-7.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-158">In addition to the C# project file, NuGet dependencies are stored in a separate 45-line *packages.config* file, as shown in Figure 4-7.</span></span>

![Figura 4-7](media/Figure4-7.png)

<span data-ttu-id="9ef1e-160">**Figura 4-7.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-160">**Figure 4-7.**</span></span> <span data-ttu-id="9ef1e-161">El archivo de *packages.config* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-161">The *packages.config* file.</span></span>

<span data-ttu-id="9ef1e-162">Después de actualizar al nuevo formato de archivo *. csproj* , puede migrar *packages.config* en proyectos de biblioteca de clases con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-162">After upgrading to the new *.csproj* file format, you can migrate *packages.config* in class library projects using Visual Studio.</span></span> <span data-ttu-id="9ef1e-163">No obstante, esta funcionalidad no funciona con proyectos de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-163">This functionality doesn't work with ASP.NET projects, however.</span></span> <span data-ttu-id="9ef1e-164">[Obtenga más información sobre cómo migrar *packages.config* a `<PackageReference>` en Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-164">[Learn more about migrating *packages.config* to `<PackageReference>` in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference).</span></span> <span data-ttu-id="9ef1e-165">Si tiene un gran número de proyectos que migrar, [esta herramienta de la comunidad puede servir de ayuda](https://github.com/MarkKharitonov/NuGetPCToPRMigrator).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-165">If you have a large number of projects to migrate, [this community tool may help](https://github.com/MarkKharitonov/NuGetPCToPRMigrator).</span></span>

## <a name="create-new-aspnet-core-project"></a><span data-ttu-id="9ef1e-166">Crear nuevo proyecto de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9ef1e-166">Create new ASP.NET Core project</span></span>

<span data-ttu-id="9ef1e-167">Agregue un nuevo proyecto de ASP.NET Core a la solución de la aplicación existente para facilitar el traslado de archivos, ya que la mayor parte del trabajo se puede realizar desde el **Explorador de soluciones** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-167">Add a new ASP.NET Core project to the existing app's solution to make moving files easier, as most of the work can be done from within Visual Studio's **Solution Explorer**.</span></span> <span data-ttu-id="9ef1e-168">En Visual Studio, haga clic con el botón derecho en la solución de la aplicación y elija **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-168">In Visual Studio, right-click on your app's solution and choose **Add New Project**.</span></span> <span data-ttu-id="9ef1e-169">Elija **ASP.net Core aplicación web** y asigne un nombre al nuevo proyecto como se muestra en la figura 4-8.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-169">Choose **ASP.NET Core web application**, and give the new project a name as shown in Figure 4-8.</span></span>

![Figura 4-8](media/Figure4-8.png)

<span data-ttu-id="9ef1e-171">**Figura 4-8.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-171">**Figure 4-8.**</span></span> <span data-ttu-id="9ef1e-172">Agregue una nueva ASP.NET Core aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-172">Add new ASP.NET Core web application.</span></span>

<span data-ttu-id="9ef1e-173">El siguiente cuadro de diálogo le pedirá que elija la plantilla que desea usar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-173">The next dialog will ask you to choose which template to use.</span></span> <span data-ttu-id="9ef1e-174">Seleccione la plantilla **Vacía**.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-174">Select the **Empty** template.</span></span> <span data-ttu-id="9ef1e-175">Asegúrese también de cambiar la lista desplegable de **.net Core** a **.NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-175">Be sure to also change the dropdown from **.NET Core** to **.NET Framework**.</span></span> <span data-ttu-id="9ef1e-176">Seleccione **ASP.NET Core 2,2**, como se muestra en la figura 4-9.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-176">Select **ASP.NET Core 2.2**, as shown in Figure 4-9.</span></span>

![Figura 4-9](media/Figure4-9.png)

<span data-ttu-id="9ef1e-178">**Figura 4-9.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-178">**Figure 4-9.**</span></span> <span data-ttu-id="9ef1e-179">Elija una plantilla de proyecto vacía que tenga como destino .NET Framework con ASP.NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-179">Choose an Empty project template targeting .NET Framework with ASP.NET Core 2.2.</span></span>

### <a name="migrating-nuget-packages"></a><span data-ttu-id="9ef1e-180">Migración de paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="9ef1e-180">Migrating NuGet Packages</span></span>

<span data-ttu-id="9ef1e-181">Dado que la herramienta de migración integrada para migrar *packages.config* a `<PackageReference>` no funciona en proyectos de ASP.net, puede usar una herramienta de la comunidad en su lugar o migrar a mano.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-181">Since the built-in migration tool for migrating *packages.config* to `<PackageReference>` doesn't work on ASP.NET projects, you can use a community tool instead, or migrate by hand.</span></span> <span data-ttu-id="9ef1e-182">Una [herramienta](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) de la comunidad que he usado usa un archivo XSL para transformar de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-182">A [community tool I've used](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) uses an XSL file to transform from one format to the other.</span></span> <span data-ttu-id="9ef1e-183">Para usarlo, copie primero el archivo de *packages.config* en la carpeta del proyecto ASP.net Core recién creada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-183">To use it, first copy the *packages.config* file to the newly created ASP.NET Core project folder.</span></span> <span data-ttu-id="9ef1e-184">Realice una copia de seguridad de los archivos, ya que este script quita el archivo *packages.config* de todas las carpetas en las que se ejecuta el script.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-184">Make a backup of your files, as this script removes the *packages.config* file from all folders under where you run the script.</span></span> <span data-ttu-id="9ef1e-185">Después, ejecute estos comandos desde la carpeta del proyecto (o para toda la solución si lo prefiere):</span><span class="sxs-lookup"><span data-stu-id="9ef1e-185">Then run these commands from the project folder (or for the entire solution if you prefer):</span></span>

```powershell
iwr https://git.io/vdKaV -OutFile Convert-ToPackageReference.ps1
iwr https://git.io/vdKar -OutFile  Convert-ToPackageReference.xsl
./Convert-ToPackageReference.ps1 | Out-Null
```

<span data-ttu-id="9ef1e-186">Los dos primeros comandos descargan archivos para que existan localmente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-186">The first two commands download files so that they exist locally.</span></span> <span data-ttu-id="9ef1e-187">La última línea ejecuta el script.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-187">The last line runs the script.</span></span> <span data-ttu-id="9ef1e-188">Después de ejecutarlo, intente compilar el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-188">After running it, try to build the new project.</span></span> <span data-ttu-id="9ef1e-189">Lo más probable es que reciba algunos errores.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-189">You'll most likely get some errors.</span></span> <span data-ttu-id="9ef1e-190">Para resolverlos, querrá eliminar algunas referencias (como la mayoría de los `Microsoft.AspNet` `System` paquetes y) y puede que tenga que quitar algunos `xmlns` atributos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-190">To resolve them, you'll want to eliminate some references (like most of the `Microsoft.AspNet` and `System` packages), and you may need to remove some `xmlns` attributes.</span></span>

<span data-ttu-id="9ef1e-191">En la mayoría de las aplicaciones de ASP.NET MVC, muchas dependencias del lado cliente como bootstrap y jQuery se han implementado mediante paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-191">In most ASP.NET MVC apps, many client-side dependencies like Bootstrap and jQuery were deployed using NuGet packages.</span></span> <span data-ttu-id="9ef1e-192">En ASP.NET Core, los paquetes NuGet solo se usan para la funcionalidad del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-192">In ASP.NET Core, NuGet packages are only used for server-side functionality.</span></span> <span data-ttu-id="9ef1e-193">Los archivos de cliente deben administrarse a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-193">Client files should be managed through other means.</span></span> <span data-ttu-id="9ef1e-194">Revise la lista de `<PackageReference>` elementos agregados y quite y tome nota de las bibliotecas de cliente, entre las que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-194">Review the list of `<PackageReference>` elements added and remove and make note of any that are for client libraries, including:</span></span>

- <span data-ttu-id="9ef1e-195">Bootstrap</span><span class="sxs-lookup"><span data-stu-id="9ef1e-195">Bootstrap</span></span>
- <span data-ttu-id="9ef1e-196">jQuery</span><span class="sxs-lookup"><span data-stu-id="9ef1e-196">jQuery</span></span>
- <span data-ttu-id="9ef1e-197">jQuery. Validation</span><span class="sxs-lookup"><span data-stu-id="9ef1e-197">jQuery.Validation</span></span>
- <span data-ttu-id="9ef1e-198">Modernizr</span><span class="sxs-lookup"><span data-stu-id="9ef1e-198">Modernizr</span></span>
- <span data-ttu-id="9ef1e-199">popper.js</span><span class="sxs-lookup"><span data-stu-id="9ef1e-199">popper.js</span></span>
- <span data-ttu-id="9ef1e-200">Respuesta</span><span class="sxs-lookup"><span data-stu-id="9ef1e-200">Respond</span></span>

<span data-ttu-id="9ef1e-201">Los archivos de cliente estáticos instalados por NuGet para estos paquetes se copiarán en la carpeta *wwwroot* del nuevo proyecto y se hospedarán desde allí.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-201">The static client files installed by NuGet for these packages will be copied over to the new project's *wwwroot* folder and hosted from there.</span></span> <span data-ttu-id="9ef1e-202">Merece la pena tener en cuenta si estos archivos siguen siendo necesarios para la aplicación y si tiene sentido continuar con su hospedaje o usar una red de entrega de contenido (CDN) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-202">It's worth considering whether these files are still needed by the app, and whether it makes sense to continue hosting them or to use a content delivery network (CDN) instead.</span></span> <span data-ttu-id="9ef1e-203">Estas versiones de la biblioteca se pueden administrar en tiempo de compilación mediante herramientas como [LibMan](/aspnet/core/client-side/libman/) o [NPM](https://www.npmjs.com/).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-203">These library versions can be managed at build time using tools like [LibMan](/aspnet/core/client-side/libman/) or [npm](https://www.npmjs.com/).</span></span> <span data-ttu-id="9ef1e-204">En la figura 4-10 se muestra el archivo *eShopPorted. csproj* completo después de migrar las referencias de paquete mediante la herramienta de conversión que se muestra y se quitan los paquetes innecesarios.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-204">Figure 4-10 shows the full *eShopPorted.csproj* file after migrating package references using the conversion tool shown and removing unnecessary packages.</span></span>

![Figura 4-10](media/Figure4-10.png)

<span data-ttu-id="9ef1e-206">**Figura 4-10.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-206">**Figure 4-10.**</span></span> <span data-ttu-id="9ef1e-207">Referencias de paquete en el archivo *eShopPorted. csproj* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-207">Package references in the *eShopPorted.csproj* file.</span></span>

<span data-ttu-id="9ef1e-208">Las referencias del paquete se pueden compactar más haciendo que el `<Version>1.0.0.0</Version>` elemento sea un `Version=1.0.0.0` atributo `<PackageReference>` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-208">The package references can be further compacted by making the `<Version>1.0.0.0</Version>` element a `Version=1.0.0.0` attribute on `<PackageReference>`.</span></span>

### <a name="migrate-static-files"></a><span data-ttu-id="9ef1e-209">Migrar archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="9ef1e-209">Migrate static files</span></span>

<span data-ttu-id="9ef1e-210">Los archivos estáticos que usa la aplicación, incluidos los scripts y los marcos de terceros, pero también las imágenes personalizadas y las hojas de estilo, se deben copiar del proyecto antiguo al nuevo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-210">Any static files the app uses, including third-party scripts and frameworks but also custom images and stylesheets, must be copied from the old project to the new one.</span></span> <span data-ttu-id="9ef1e-211">En las aplicaciones ASP.NET MVC, normalmente se a los archivos en función de su ubicación dentro de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-211">In ASP.NET MVC apps, files were typically accessed based on their location within the project folder.</span></span> <span data-ttu-id="9ef1e-212">En ASP.NET Core aplicaciones, se tendrá acceso a estos archivos estáticos en función de su ubicación dentro de la carpeta *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-212">In ASP.NET Core apps, these static files will be accessed based on their location within the *wwwroot* folder.</span></span> <span data-ttu-id="9ef1e-213">En el caso del proyecto de *eShop* , hay archivos estáticos en las siguientes carpetas:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-213">For the *eShop* project, there are static files in the following folders:</span></span>

* <span data-ttu-id="9ef1e-214">*Contenido*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-214">*Content*</span></span>
* <span data-ttu-id="9ef1e-215">*éstas*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-215">*fonts*</span></span>
* <span data-ttu-id="9ef1e-216">*Imágenes*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-216">*Images*</span></span>
* <span data-ttu-id="9ef1e-217">*Selecciones*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-217">*Pics*</span></span>
* <span data-ttu-id="9ef1e-218">*Scripts*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-218">*Scripts*</span></span>

<span data-ttu-id="9ef1e-219">La plantilla de proyecto **vacía** que se usó en el paso anterior no incluye esta carpeta de forma predeterminada o el middleware necesario para que funcione.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-219">The **Empty** project template used in the previous step doesn't include this folder by default, or the middleware needed for it to work.</span></span> <span data-ttu-id="9ef1e-220">Deberá agregarlos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-220">You'll need to add them.</span></span>

<span data-ttu-id="9ef1e-221">Agregue una carpeta *wwwroot* a la raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-221">Add a *wwwroot* folder to the root of the project.</span></span>

<span data-ttu-id="9ef1e-222">Agregue la versión 2.2.0 del `Microsoft.AspNetCore.StaticFiles` paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-222">Add version 2.2.0 of the `Microsoft.AspNetCore.StaticFiles` NuGet package.</span></span>

<span data-ttu-id="9ef1e-223">En *Startup.CS*, agregue una llamada a `app.UseStaticFiles()` en el `Configure` método:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-223">In *Startup.cs*, add a call to `app.UseStaticFiles()` in the `Configure` method:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseStaticFiles();

    // ...
}
```

<span data-ttu-id="9ef1e-224">Copie la carpeta de *contenido* de la aplicación ASP.NET MVC en la carpeta *wwwroot* del nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-224">Copy the *Content* folder from the ASP.NET MVC app to the new project's *wwwroot* folder.</span></span>

<span data-ttu-id="9ef1e-225">Ejecute la aplicación y vaya a la carpeta */Content/base.CSS* para comprobar que el archivo estático se atiende correctamente desde su ruta de acceso esperada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-225">Run the app and navigate to its */Content/base.css* folder to verify that the static file is served correctly from its expected path.</span></span> <span data-ttu-id="9ef1e-226">Siga copiando el resto de las carpetas que contienen archivos estáticos en el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-226">Continue copying the rest of the folders containing static files to the new project.</span></span> <span data-ttu-id="9ef1e-227">También querrá copiar el archivo *favicon. ico* de la raíz del proyecto en la carpeta *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-227">You'll also want to copy the *favicon.ico* file from the project's root to the *wwwroot* folder.</span></span> <span data-ttu-id="9ef1e-228">En la figura 4-11 se muestran los resultados tras copiar todos los archivos y sus carpetas.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-228">Figure 4-11 shows the results after these files and their folders have all been copied.</span></span>

![Figura 4-11](media/Figure4-11.png)

<span data-ttu-id="9ef1e-230">**Figura 4-11.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-230">**Figure 4-11.**</span></span> <span data-ttu-id="9ef1e-231">Carpetas estáticas copiadas en la carpeta *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-231">Static folders copied over to *wwwroot* folder.</span></span>

### <a name="migrate-c-files"></a><span data-ttu-id="9ef1e-232">Migración de archivos de C#</span><span class="sxs-lookup"><span data-stu-id="9ef1e-232">Migrate C# files</span></span>

<span data-ttu-id="9ef1e-233">A continuación, copie los archivos de C# usados por la aplicación, incluidas las carpetas estándar de MVC y su contenido, como *Controladores*, *modelos*, *ViewModel* y *servicios*.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-233">Next, copy over the C# files used by the app, including standard MVC folders and their contents like *Controllers*, *Models*, *ViewModel*, and *Services*.</span></span> <span data-ttu-id="9ef1e-234">Lo más probable es que se necesiten algunos cambios en estos archivos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-234">There will most likely be some changes needed in these files.</span></span> <span data-ttu-id="9ef1e-235">Es mejor copiar una carpeta (o subcarpeta) cada vez y compilar para ver qué errores deben solucionarse a medida que avanza.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-235">It's best to copy one folder (or subfolder) at a time and compile to see what errors need to be addressed as you go.</span></span>

<span data-ttu-id="9ef1e-236">En el ejemplo de *eShop* , la primera carpeta que se puede migrar es la carpeta *Models* , que incluye las entidades de C# y las clases de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-236">For the *eShop* sample, the first folder I choose to migrate is the *Models* folder, which includes C# entities and Entity Framework classes.</span></span> <span data-ttu-id="9ef1e-237">La mayoría de los demás usan las clases de esta carpeta, por lo que no funcionarán hasta que se hayan copiado estas clases.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-237">This folder's classes are used by most of the others, so they won't work until these classes have been copied.</span></span> <span data-ttu-id="9ef1e-238">Después de copiar la carpeta y la compilación, el compilador revelaba errores relacionados con el espacio de nombres que falta `System.Web.Hosting` , el acceso relacionado a `HostingEnvironment` y una referencia a `ConfigurationManager.AppSettings` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-238">After copying the folder and building, the compiler revealed errors related to missing namespace `System.Web.Hosting`, related access to `HostingEnvironment`, and a reference to `ConfigurationManager.AppSettings`.</span></span> <span data-ttu-id="9ef1e-239">La solución a estos problemas será pasar los datos de la ruta de acceso necesaria. por ahora, las líneas de interrupción están comentadas y `TODO:` se agrega un comentario a cada una de ellas para realizar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-239">The solution to these issues will be to pass in the necessary path data; for now the breaking lines are commented out and a `TODO:` comment is added to each one to track it.</span></span> <span data-ttu-id="9ef1e-240">Después de cambiar cinco líneas, el **lista de tareas** muestra cinco elementos y las compilaciones del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-240">After changing five lines, the **Task List** shows five items and the project builds.</span></span>

<span data-ttu-id="9ef1e-241">A continuación, se copia la carpeta *ViewModel* , con su clase.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-241">Next, the *ViewModel* folder, with its one class, is copied over.</span></span> <span data-ttu-id="9ef1e-242">Es fácil de crear y se compila de inmediato.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-242">It's an easy one, and builds immediately.</span></span>

<span data-ttu-id="9ef1e-243">Se copia la carpeta *servicios* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-243">The *Services* folder is copied over.</span></span> <span data-ttu-id="9ef1e-244">Las clases de esta carpeta dependen de Entity Framework clases de la carpeta *Models* , por lo que es necesario copiarlas después de esa carpeta.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-244">This folder's classes depend on Entity Framework classes from the *Models* folder, which is why it needed to be copied after that folder.</span></span> <span data-ttu-id="9ef1e-245">Afortunadamente, se compilan sin errores.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-245">Fortunately, it too builds without errors.</span></span>

<span data-ttu-id="9ef1e-246">Que deja la carpeta *Controllers* y sus dos `Controller` clases.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-246">That leaves the *Controllers* folder and its two `Controller` classes.</span></span> <span data-ttu-id="9ef1e-247">Después de copiar la carpeta en el nuevo proyecto y compilar, hay siete errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-247">After copying the folder to the new project and building, there are seven build errors.</span></span> <span data-ttu-id="9ef1e-248">Cuatro de ellos están relacionados con el `ViewBag` acceso y notifican un error de:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-248">Four of them are related to `ViewBag` access and report an error of:</span></span>

> `Missing compiler required member 'Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo.Create'`

<span data-ttu-id="9ef1e-249">Para resolver este error, agregue una referencia de paquete NuGet a C#:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-249">To resolve this error add a NuGet package reference to C#:</span></span>

```xml
<PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
```

<span data-ttu-id="9ef1e-250">Los tres errores restantes especifican los tipos que se definen en un ensamblado al que no se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-250">The remaining three errors specify types that are defined in an assembly that isn't referenced.</span></span> <span data-ttu-id="9ef1e-251">En concreto, estos tipos:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-251">Specifically these types:</span></span>

- `HttpServerUtilityBase`
- `RouteValueDictionary`
- `HttpRequestBase`

<span data-ttu-id="9ef1e-252">Echemos un vistazo a cada error de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-252">Let's look at each error one by one.</span></span> <span data-ttu-id="9ef1e-253">El primer error se produce al intentar hacer referencia a la `Server` propiedad de `Controller` , que ya no existe.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-253">The first error occurs while trying to reference the `Server` property of `Controller`, which no longer exists.</span></span> <span data-ttu-id="9ef1e-254">El objetivo de la operación es obtener la ruta de acceso a un archivo de imagen en la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-254">The goal of the operation is to get the path to an image file in the app:</span></span>

```csharp
if (item != null)
{
    var webRoot = Server.MapPath("~/Pics"); // compiler error on this line
    var path = Path.Combine(webRoot, item.PictureFileName);

    string imageFileExtension = Path.GetExtension(item.PictureFileName);
    string mimetype = GetImageMimeTypeFromImageFileExtension(imageFileExtension);

    var buffer = System.IO.File.ReadAllBytes(path);

    return File(buffer, mimetype);
}
```

<span data-ttu-id="9ef1e-255">Existen dos posibles soluciones para este problema.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-255">There are two possible solutions to this problem.</span></span> <span data-ttu-id="9ef1e-256">La primera es mantener la funcionalidad tal cual.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-256">The first is to keep the functionality as it is.</span></span> <span data-ttu-id="9ef1e-257">En este caso, en lugar de usar `Server.MapPath` , se debe usar una ruta de acceso fija que haga referencia a la ubicación de los archivos de imagen en *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-257">In this case, rather than using `Server.MapPath`, a fixed path referencing the image files' location in *wwwroot* should be used.</span></span> <span data-ttu-id="9ef1e-258">Como alternativa, puesto que el único propósito de este método de acción es devolver un archivo de imagen estático, las referencias a esta acción en los archivos de vista se pueden actualizar para hacer referencia a los archivos estáticos directamente, lo que mejora el rendimiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-258">Alternately, since the only purpose of this action method is to return a static image file, the references to this action in view files can be updated to reference the static files directly, which improves runtime performance.</span></span> <span data-ttu-id="9ef1e-259">Dado que no se realiza ningún procesamiento como parte de esta acción, no hay ninguna razón para no servir solo a los archivos directamente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-259">Since no processing is being done as part of this action, there's no reason not to just serve the files directly.</span></span> <span data-ttu-id="9ef1e-260">Si no se tenable actualizar todas las referencias a esta acción, se podría volver a escribir la acción para producir una redirección a la ubicación del archivo estático.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-260">If it's not tenable to update all references to this action, the action could be rewritten to produce a redirect to the static file's location.</span></span>

<span data-ttu-id="9ef1e-261">Los dos errores siguientes se producen en el mismo método privado en la misma línea de código:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-261">The next two errors both occur in the same private method in the same line of code:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

<span data-ttu-id="9ef1e-262">`this.Url`Y `this.Request` causan errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-262">Both `this.Url` and `this.Request` cause compiler errors.</span></span> <span data-ttu-id="9ef1e-263">En cuanto a cómo se usa este código, su finalidad es crear un vínculo a la `PicController` acción que representa los archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-263">Looking at how this code is used, its purpose is to build a link to the `PicController` action that renders image files.</span></span> <span data-ttu-id="9ef1e-264">Probablemente, la misma que se acaba de detectar podría reemplazarse por vínculos directos a los archivos estáticos ubicados en *wwwroot*.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-264">The same one we just discovered could probably be replaced with direct links to the static files located in *wwwroot*.</span></span> <span data-ttu-id="9ef1e-265">Por ahora, merece la pena comentar este código y agregar un `TODO:` Comentario para hacer referencia al método pics de otra manera.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-265">For now, it's worth commenting out this code and adding a `TODO:` comment to reference the pics another way.</span></span>

<span data-ttu-id="9ef1e-266">Merece la pena mencionar que la clase base `Controller` , usada por la `CatalogController` clase en la que aparece este código, sigue haciendo referencia a `System.Web.Mvc.Controller` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-266">It's worth noting that the base `Controller` class, used by the `CatalogController` class in which this code appears, is still referring to `System.Web.Mvc.Controller`.</span></span> <span data-ttu-id="9ef1e-267">Sin duda habrá más errores que corregir una vez que lo actualicemos para usar ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-267">There will undoubtedly be more errors to fix once we update this to use ASP.NET Core.</span></span> <span data-ttu-id="9ef1e-268">En primer lugar, quite la `using System.Web.Mvc;` línea de la lista de `using` instrucciones de `CatalogController` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-268">First, remove the `using System.Web.Mvc;` line from the list of `using` statements in `CatalogController`.</span></span> <span data-ttu-id="9ef1e-269">A continuación, agregue el paquete NuGet `Microsoft.AspNetCore.Mvc` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-269">Next, add the NuGet package `Microsoft.AspNetCore.Mvc`.</span></span> <span data-ttu-id="9ef1e-270">Por último, agregue una `using Microsoft.AspNetCore.Mvc;` instrucción y vuelva a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-270">Finally, add a `using Microsoft.AspNetCore.Mvc;` statement, and build the app again.</span></span>

<span data-ttu-id="9ef1e-271">Esta vez, hay 16 errores:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-271">This time, there are 16 errors:</span></span>

- <span data-ttu-id="9ef1e-272">`Include` no es un argumento de atributo con nombre válido (2)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-272">`Include` is not a valid named attribute argument (2)</span></span>
- <span data-ttu-id="9ef1e-273">`HttpStatusCodeResult` no encontrado (3)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-273">`HttpStatusCodeResult` not found (3)</span></span>
- <span data-ttu-id="9ef1e-274">`HttpNotFound` no existe (3)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-274">`HttpNotFound` does not exist (3)</span></span>
- <span data-ttu-id="9ef1e-275">`SelectList` no encontrado (8)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-275">`SelectList` not found (8)</span></span>

<span data-ttu-id="9ef1e-276">Una vez más, vamos a revisar estos errores uno a uno.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-276">Once more, let's review these errors one by one.</span></span> <span data-ttu-id="9ef1e-277">En primer lugar, `SelectList` se puede corregir agregando `using Microsoft.AspNetCore.Mvc.Rendering;` , lo que elimina la mitad de los errores.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-277">First, `SelectList` can be fixed by adding `using Microsoft.AspNetCore.Mvc.Rendering;`, which eliminates half of the errors.</span></span>

<span data-ttu-id="9ef1e-278">Todas las referencias a `return HttpNotFound();` deben reemplazarse por `return NotFound();` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-278">All references to `return HttpNotFound();` should be replaced with `return NotFound();`.</span></span>

<span data-ttu-id="9ef1e-279">Todas las referencias a `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` deben reemplazarse por `return BadRequest();` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-279">All references to `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` should be replaced with `return BadRequest();`.</span></span>

<span data-ttu-id="9ef1e-280">Esto solo deja el uso de `Include` con un `[Bind]` atributo en un par de métodos de acción que tienen el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-280">That just leaves the use of `Include` with a `[Bind]` attribute on a couple of action methods that look like this:</span></span>

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind(Include = "Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

<span data-ttu-id="9ef1e-281">El código anterior restringe el enlace de modelos a las propiedades enumeradas en la `Include` cadena.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-281">The preceding code restricts model binding to the properties listed in the `Include` string.</span></span> <span data-ttu-id="9ef1e-282">En ASP.NET Core MVC, el `[Bind]` atributo sigue existiendo, pero ya no necesita el `Include =` argumento.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-282">In ASP.NET Core MVC, the `[Bind]` attribute still exists, but no longer needs the `Include =` argument.</span></span> <span data-ttu-id="9ef1e-283">Pase la lista de propiedades directamente al `[Bind]` atributo:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-283">Pass the list of properties directly to the `[Bind]` attribute:</span></span>

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind("Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

<span data-ttu-id="9ef1e-284">Con estos cambios, el proyecto se compila una vez más.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-284">With these changes, the project compiles once more.</span></span> <span data-ttu-id="9ef1e-285">Por lo general, es mejor usar tipos de modelo independientes para las entradas del controlador, en lugar de usar el enlace de modelos directamente con el modelo de dominio o los tipos de modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-285">It's generally a better practice to use separate model types for controller inputs, rather than using model binding directly to your domain model or data model types.</span></span>

## <a name="migrate-views"></a><span data-ttu-id="9ef1e-286">Migrar vistas</span><span class="sxs-lookup"><span data-stu-id="9ef1e-286">Migrate views</span></span>

<span data-ttu-id="9ef1e-287">Las dos características más importantes ASP.NET Core MVC relacionadas con las vistas son [Razor pages](/aspnet/core/razor-pages/) y las [aplicaciones auxiliares de etiquetas](/aspnet/core/mvc/views/tag-helpers/built-in/).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-287">The two biggest ASP.NET Core MVC features related to views are [Razor Pages](/aspnet/core/razor-pages/) and [Tag Helpers](/aspnet/core/mvc/views/tag-helpers/built-in/).</span></span> <span data-ttu-id="9ef1e-288">Para la migración inicial, no usaremos ninguna de estas características.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-288">For the initial migration, we won't use either feature.</span></span> <span data-ttu-id="9ef1e-289">Sin embargo, debe tener en cuenta las características si sigue dando soporte a la aplicación una vez que se ha migrado.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-289">You should, however, keep the features in mind if you continue supporting the app once it's been migrated.</span></span> <span data-ttu-id="9ef1e-290">El siguiente paso consiste en copiar la carpeta *views* del proyecto original en la nueva.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-290">The next step is to copy the *Views* folder from the original project into the new one.</span></span> <span data-ttu-id="9ef1e-291">Después de compilar, hay nueve errores:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-291">After building, there are nine errors:</span></span>

- <span data-ttu-id="9ef1e-292">HttpContext no existe (2)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-292">HttpContext does not exist (2)</span></span>
- <span data-ttu-id="9ef1e-293">Los scripts no existen (5)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-293">Scripts does not exist (5)</span></span>
- <span data-ttu-id="9ef1e-294">No existe ningún estilo (1)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-294">Styles does not exist (1)</span></span>
- <span data-ttu-id="9ef1e-295">No se encontró HtmlString (1)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-295">HtmlString could not be found(1)</span></span>

<span data-ttu-id="9ef1e-296">La investigación de estos errores descubre que la mayoría de ellos se encuentran en el *_Layout. cshtml* principal, con varios relacionados con la representación de etiquetas de script y estilo, o que se muestran cuando el servidor que hospeda la aplicación se reinició por última vez.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-296">Investigating these errors finds that most of them are in the main *_Layout.cshtml*, with several related to rendering script and style tags, or displaying when the server hosting the app was last restarted.</span></span> <span data-ttu-id="9ef1e-297">La lista de código siguiente muestra las áreas problemáticas en el archivo *_Layout. cshtml* :</span><span class="sxs-lookup"><span data-stu-id="9ef1e-297">The following code listing shows problem areas in the *_Layout.cshtml* file:</span></span>

```razor
// other lines omitted; only errors shown
@Styles.Render("~/Content/css")
@Scripts.Render("~/bundles/modernizr")

@{ var sessionInfo = new HtmlString($"{HttpContext.Current.Session["MachineName"]}, {HttpContext.Current.Session["SessionStartTime"]}");}

@Scripts.Render("~/bundles/jquery")
@Scripts.Render("~/bundles/bootstrap")
```

<span data-ttu-id="9ef1e-298">Se puede quitar la referencia a Modernizr.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-298">The reference to Modernizr can be removed.</span></span> <span data-ttu-id="9ef1e-299">Las referencias a bootstrap y jQuery se pueden reemplazar por vínculos de red CDN a la versión adecuada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-299">The references to Bootstrap and jQuery can be replaced with CDN links to the appropriate version.</span></span>

<span data-ttu-id="9ef1e-300">Reemplazar `@Styles.Render` línea por:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-300">Replace `@Styles.Render` line with:</span></span>

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

<span data-ttu-id="9ef1e-301">Reemplace las dos últimas `Scripts.Render` líneas por:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-301">Replace the last two `Scripts.Render` lines with:</span></span>

```html
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```

<span data-ttu-id="9ef1e-302">Por último, después del bootstrap `<link>` , agregue `<link>` elementos adicionales para los estilos locales que use la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-302">Finally, after the Bootstrap `<link>`, add additional `<link>` elements for local styles your app uses.</span></span> <span data-ttu-id="9ef1e-303">En el caso de *eShop*, el resultado se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-303">For *eShop*, the result is shown here:</span></span>

```html
<link rel="stylesheet" href="~/Content/custom.css" />
<link rel="stylesheet" href="~/Content/base.css" />
<link rel="stylesheet" href="~/Content/Site.css" />
```

<span data-ttu-id="9ef1e-304">Para determinar el orden en el que `<link>` deben aparecer los elementos, mire el HTML representado de la aplicación original.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-304">To determine the order in which the `<link>` elements should appear, look at your original app's rendered HTML.</span></span> <span data-ttu-id="9ef1e-305">Como alternativa, revise *BundleConfig.CS*, que para el ejemplo de *eShop* incluye este código que indica la secuencia adecuada:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-305">Alternatively, review *BundleConfig.cs*, which for the *eShop* sample includes this code indicating the appropriate sequence:</span></span>

```csharp
bundles.Add(new StyleBundle("~/Content/css").Include(
          "~/Content/bootstrap.css",
          "~/Content/custom.css",
          "~/Content/base.css",
          "~/Content/site.css"));
```

<span data-ttu-id="9ef1e-306">Al volver a compilar, se revela un error más al cargar la validación de jQuery en las vistas *crear* y *Editar* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-306">Building again reveals one more error loading jQuery Validation on the *Create* and *Edit* views.</span></span> <span data-ttu-id="9ef1e-307">Reemplácelo por este script:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-307">Replace it with this script:</span></span>

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.17.0/jquery.validate.min.js" integrity="sha512-O/nUTF5mdFkhEoQHFn9N5wmgYyW323JO6v8kr6ltSRKriZyTr/8417taVWeabVS4iONGk2V444QD0P2cwhuTkg==" crossorigin="anonymous"></script>
```

<span data-ttu-id="9ef1e-308">Lo último que hay que corregir en las vistas es la referencia a `Session` para mostrar cuánto tiempo se ha estado ejecutando la aplicación y en qué máquina.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-308">The last thing to fix in the views is the reference to `Session` to display how long the app has been running, and on which machine.</span></span> <span data-ttu-id="9ef1e-309">Podemos recopilar estos datos en `Startup` como variables estáticas y mostrar las variables en la página de diseño.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-309">We can collect this data in `Startup` as static variables and display the variables on the layout page.</span></span> <span data-ttu-id="9ef1e-310">Agregue las siguientes propiedades a *Startup.CS*:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-310">Add the following properties to *Startup.cs*:</span></span>

```csharp
public static DateTime StartTime { get; } = DateTime.UtcNow;
public static string MachineName { get; } = Environment.MachineName;
```

<span data-ttu-id="9ef1e-311">A continuación, reemplace el contenido del pie de página en el diseño por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-311">Then replace the content of the footer in the layout with the following code:</span></span>

```razor
<section class="col-sm-6">
    <img class="esh-app-footer-text hidden-xs" src="~/images/main_footer_text.png" width="335" height="26" alt="footer text image" />
    <br />
<small>@eShopPorted.Startup.MachineName - @eShopPorted.Startup.StartTime.ToString() UTC</small>
</section>
```

<span data-ttu-id="9ef1e-312">Llegados a este punto, la aplicación se compilará correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-312">At this point, the app once more builds successfully.</span></span> <span data-ttu-id="9ef1e-313">Sin embargo, intentar ejecutarlo solo produce *Hola mundo.*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-313">However, trying to run it just yields *Hello World!*</span></span> <span data-ttu-id="9ef1e-314">Dado que la plantilla de ASP.NET Core **vacía** solo está configurada para mostrarla en respuesta a cualquier solicitud.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-314">because the **Empty** ASP.NET Core template is only configured to display that in response to any request.</span></span> <span data-ttu-id="9ef1e-315">En la siguiente sección, se completa la migración mediante la configuración de la aplicación para usar ASP.NET Core MVC, incluida la inserción de dependencias y la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-315">In the next section, I complete the migration by configuring the app to use ASP.NET Core MVC, including dependency injection and configuration.</span></span> <span data-ttu-id="9ef1e-316">Una vez que se haya implementado, la aplicación debe ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-316">Once that's in place, the app should run.</span></span> <span data-ttu-id="9ef1e-317">A continuación, será el momento de corregir las `TODO:` tareas que se crearon anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-317">Then it will be time to fix the `TODO:` tasks that were created earlier.</span></span>

## <a name="migrate-app-startup-components"></a><span data-ttu-id="9ef1e-318">Migrar componentes de inicio de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9ef1e-318">Migrate app startup components</span></span>

<span data-ttu-id="9ef1e-319">El último paso de migración consiste en realizar las tareas de inicio de la aplicación desde *global. asax* y las clases a las que llama, y migrarlas a sus ASP.net Core equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-319">The last migration step is to take the app startup tasks from *Global.asax*, and the classes it calls, and migrate these to their ASP.NET Core equivalents.</span></span> <span data-ttu-id="9ef1e-320">Estas tareas incluyen la configuración de MVC, la configuración de la inserción de dependencias y el trabajo con el nuevo sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-320">These tasks include configuration of MVC itself, setting up dependency injection, and working with the new configuration system.</span></span> <span data-ttu-id="9ef1e-321">En ASP.NET Core, estas tareas se administran en el archivo *Startup.CS* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-321">In ASP.NET Core, these tasks are handled in the *Startup.cs* file.</span></span>

### <a name="configure-mvc"></a><span data-ttu-id="9ef1e-322">Configurar MVC</span><span class="sxs-lookup"><span data-stu-id="9ef1e-322">Configure MVC</span></span>

<span data-ttu-id="9ef1e-323">La aplicación ASP.NET MVC original tiene el código siguiente en su `Application_Start` en *global. asax*, que se ejecuta cuando se inicia la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-323">The original ASP.NET MVC app has the following code in its `Application_Start` in *Global.asax*, which runs when the app starts up:</span></span>

```csharp
protected void Application_Start()
{
    container = RegisterContainer();
    AreaRegistration.RegisterAllAreas();
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
    RouteConfig.RegisterRoutes(RouteTable.Routes);
    BundleConfig.RegisterBundles(BundleTable.Bundles);
    ConfigDataBase();
}
```

<span data-ttu-id="9ef1e-324">Al examinar estas líneas de una en una, el `RegisterContainer` método configura la inserción de dependencias, que se migrará a continuación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-324">Looking at these lines one by one, the `RegisterContainer` method sets up dependency injection, which will be ported below.</span></span> <span data-ttu-id="9ef1e-325">Las tres líneas siguientes configuran distintas partes de MVC: áreas, filtros y rutas.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-325">The next three lines configure different parts of MVC: areas, filters, and routes.</span></span> <span data-ttu-id="9ef1e-326">Los paquetes se sustituyen por archivos estáticos en la aplicación migrada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-326">Bundles are replaced by static files in the ported app.</span></span> <span data-ttu-id="9ef1e-327">La última línea configura el acceso a los datos de la aplicación, que se mostrará en una sección posterior.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-327">The last line sets up data access for the app, which will be shown in a later section.</span></span>

<span data-ttu-id="9ef1e-328">Dado que esta aplicación no utiliza realmente áreas, no es necesario hacer nada para migrar la llamada de registro de área.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-328">Since this app isn't actually using areas, there's nothing that needs to be done to migrate the area registration call.</span></span> <span data-ttu-id="9ef1e-329">Si la aplicación necesita migrar áreas, los [documentos especifican cómo configurar áreas en ASP.net Core](/aspnet/core/mvc/controllers/areas).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-329">If your app does need to migrate areas, the [docs specify how to configure areas in ASP.NET Core](/aspnet/core/mvc/controllers/areas).</span></span>

<span data-ttu-id="9ef1e-330">La llamada para registrar filtros globales invoca una aplicación auxiliar en la `FilterConfig` clase de la carpeta de *App_Start* de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-330">The call to register global filters invokes a helper on the `FilterConfig` class in the app's *App_Start* folder:</span></span>

```csharp
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new HandleErrorAttribute());
}
```

<span data-ttu-id="9ef1e-331">El único atributo que se agrega a la aplicación es el filtro de MVC de ASP.NET, `HandleErrorAttribute` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-331">The only attribute added to the app is the ASP.NET MVC filter, `HandleErrorAttribute`.</span></span> <span data-ttu-id="9ef1e-332">Este filtro garantiza que cuando se produce una excepción como parte de una solicitud, se muestran una acción y vista predeterminadas, en lugar de los detalles de la excepción.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-332">This filter ensures that when an exception occurs as part of a request, a default action and view are displayed, rather than the exception details.</span></span> <span data-ttu-id="9ef1e-333">En ASP.NET Core, el middleware realiza esta misma funcionalidad `UseExceptionHandler` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-333">In ASP.NET Core, this same functionality is performed by the `UseExceptionHandler` middleware.</span></span> <span data-ttu-id="9ef1e-334">Los mensajes de error detallados no están habilitados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-334">The detailed error messages aren't enabled by default.</span></span> <span data-ttu-id="9ef1e-335">Deben configurarse con el `UseDeveloperExceptionPage` middleware.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-335">They must be configured using the `UseDeveloperExceptionPage` middleware.</span></span> <span data-ttu-id="9ef1e-336">Para configurar este comportamiento para que coincida con la aplicación original, se debe agregar el código siguiente al inicio del `Configure` método en *Startup.CS*:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-336">To configure this behavior to match the original app, the following code must be added to the start of the `Configure` method in *Startup.cs*:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
    }
    // ...
}
```

<span data-ttu-id="9ef1e-337">Esto se encarga del único filtro que usa la aplicación de eShop y, en este caso, se realizó mediante el middleware integrado.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-337">This takes care of the only filter used by the eShop app, and in this case it was done by using built-in middleware.</span></span> <span data-ttu-id="9ef1e-338">Si tiene filtros globales que se deben configurar en la aplicación, esto se hace cuando se agrega MVC en el `ConfigureServices` método, que se muestra más adelante en este capítulo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-338">If you have global filters that must be configured in your app, this is done when MVC is added in the `ConfigureServices` method, which is shown later in this chapter.</span></span>

<span data-ttu-id="9ef1e-339">La última parte de la lógica relacionada con MVC que se debe migrar son las rutas predeterminadas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-339">The last piece of MVC-related logic that needs to be migrated are the app's default routes.</span></span> <span data-ttu-id="9ef1e-340">La llamada a `RouteConfig.RegisterRoutes(RouteTable.Routes)` pasa la tabla de rutas MVC al `RegisterRoutes` método auxiliar, donde se ejecuta el código siguiente cuando se inicia la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-340">The call to `RouteConfig.RegisterRoutes(RouteTable.Routes)` passes the MVC route table to the `RegisterRoutes` helper method, where the following code is executed when the app starts up:</span></span>

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.MapMvcAttributeRoutes();
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

    routes.MapRoute(
        name: "Default",
        url: "{controller}/{action}/{id}",
        defaults: new { controller = "Catalog", action = "Index", id = UrlParameter.Optional }
    );
}
```

<span data-ttu-id="9ef1e-341">Tomando este código línea a línea, la primera línea configura la compatibilidad con las rutas de atributo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-341">Taking this code line-by-line, the first line sets up support for attribute routes.</span></span> <span data-ttu-id="9ef1e-342">Esto está integrado en ASP.NET Core, por lo que no es necesario configurarlo por separado.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-342">This is built into ASP.NET Core, so it's unnecessary to configure it separately.</span></span> <span data-ttu-id="9ef1e-343">Del mismo modo, los archivos *{Resource}. axd* no se usan con ASP.net Core, por lo que no es necesario pasar por alto dichas rutas.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-343">Likewise, *{resource}.axd* files aren't used with ASP.NET Core, so there's no need to ignore such routes.</span></span> <span data-ttu-id="9ef1e-344">El `MapRoute` método configura el predeterminado para MVC, que utiliza la `{controller}/{action}/{id}` plantilla de ruta típica.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-344">The `MapRoute` method configures the default for MVC, which uses the typical `{controller}/{action}/{id}` route template.</span></span> <span data-ttu-id="9ef1e-345">También especifica los valores predeterminados para esta plantilla, de modo que `CatalogController` es el controlador predeterminado que se usa y el `Index` método es la acción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-345">It also specifies the defaults for this template, such that the `CatalogController` is the default controller used and the `Index` method is the default action.</span></span> <span data-ttu-id="9ef1e-346">Las aplicaciones más grandes suelen incluir más llamadas a `MapRoute` para configurar rutas adicionales.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-346">Larger apps will frequently include more calls to `MapRoute` to set up additional routes.</span></span>

<span data-ttu-id="9ef1e-347">ASP.NET Core MVC admite [enrutamiento convencional y enrutamiento de atributos](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-347">ASP.NET Core MVC supports [conventional routing and attribute routing](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2).</span></span> <span data-ttu-id="9ef1e-348">El enrutamiento convencional es análogo al modo en que se configura la tabla de rutas en el `RegisterRoutes` método mencionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-348">Conventional routing is analogous to how the route table is configured in the `RegisterRoutes` method listed previously.</span></span> <span data-ttu-id="9ef1e-349">Para configurar el enrutamiento convencional con una ruta predeterminada como la usada en la aplicación de *eShop* , agregue el código siguiente a la parte inferior del `Configure` método en *Startup.CS*:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-349">To set up conventional routing with a default route like the one used in the *eShop* app, add the following code to the bottom of the `Configure` method in *Startup.cs*:</span></span>

```csharp
app.UseMvc(routes =>
{
   routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
});
```

> [!NOTE]
> <span data-ttu-id="9ef1e-350">Con ASP.NET Core 3,0 y versiones posteriores, se cambia para utilizar extremos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-350">With ASP.NET Core 3.0 and later, this is changed to use endpoints.</span></span> <span data-ttu-id="9ef1e-351">Para que el puerto inicial ASP.NET Core 2,2, se trata de la sintaxis adecuada para asignar rutas convencionales.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-351">For the initial port to ASP.NET Core 2.2, this is the proper syntax for mapping conventional routes.</span></span>

<span data-ttu-id="9ef1e-352">Una vez realizados estos cambios, el `Configure` método está casi terminado.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-352">With these changes in place, the `Configure` method is almost done.</span></span> <span data-ttu-id="9ef1e-353">El método de la plantilla original `app.Run` que imprime *Hola mundo.*</span><span class="sxs-lookup"><span data-stu-id="9ef1e-353">The original template's `app.Run` method that prints *Hello World!*</span></span> <span data-ttu-id="9ef1e-354">se debe eliminar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-354">should be deleted.</span></span> <span data-ttu-id="9ef1e-355">En este punto, el método es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-355">At this point, the method is as shown here:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }

    app.UseStaticFiles();

    app.UseMvc(routes =>
    {
        routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
    });
}
```

<span data-ttu-id="9ef1e-356">Ahora es el momento de configurar los servicios MVC, seguido del resto de la compatibilidad de la aplicación con la inserción de dependencias (DI).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-356">Now it's time to configure MVC services, followed by the rest of the app's support for dependency injection (DI).</span></span> <span data-ttu-id="9ef1e-357">Hasta ahora, el método del proyecto *eShopPorted* `ConfigureServices` permaneció vacío.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-357">So far, the *eShopPorted* project's `ConfigureServices` method has remained empty.</span></span> <span data-ttu-id="9ef1e-358">Ahora es el momento de empezar a rellenarlo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-358">Now it's time to start populating it.</span></span>

<span data-ttu-id="9ef1e-359">En primer lugar, para obtener ASP.NET Core MVC funcione correctamente, debe agregarse:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-359">First, to get ASP.NET Core MVC to work properly, it needs to be added:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
}
```

<span data-ttu-id="9ef1e-360">El código anterior es la configuración mínima necesaria para poder trabajar con las características de MVC.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-360">The preceding code is the minimal configuration required to get MVC features working.</span></span> <span data-ttu-id="9ef1e-361">Hay muchas características adicionales que se pueden configurar desde esta llamada, pero por ahora basta con compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-361">There are many additional features that can be configured from this call, but for now this will suffice to build the app.</span></span> <span data-ttu-id="9ef1e-362">Al ejecutarlo, se enruta correctamente la solicitud predeterminada, pero como todavía no se ha configurado DI, se produce un error durante la activación porque todavía no se ha `CatalogController` proporcionado ninguna implementación de tipo `ICatalogService` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-362">Running it now routes the default request properly, but since we've not yet configured DI, an error occurs while activating `CatalogController`, because no implementation of type `ICatalogService` has been provided yet.</span></span> <span data-ttu-id="9ef1e-363">Volveremos a configurar MVC más en un momento.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-363">We'll return to configure MVC further in a moment.</span></span> <span data-ttu-id="9ef1e-364">Por ahora, vamos a migrar la inserción de dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-364">For now, let's migrate the app's dependency injection.</span></span>

#### <a name="migrate-dependency-injection-configuration"></a><span data-ttu-id="9ef1e-365">Migrar la configuración de inserción de dependencias</span><span class="sxs-lookup"><span data-stu-id="9ef1e-365">Migrate dependency injection configuration</span></span>

<span data-ttu-id="9ef1e-366">El archivo *global. asax* de la aplicación original define el método siguiente, al que se llama cuando se inicia la aplicación:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-366">The original app's *Global.asax* file defines the following method, called when the app starts up:</span></span>

```csharp
protected IContainer RegisterContainer()
{
  var builder = new ContainerBuilder();

  builder.RegisterControllers(typeof(MvcApplication).Assembly);

  var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
  builder.RegisterModule(new ApplicationModule(mockData));

  var container = builder.Build();
  DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

  return container;
}
```

<span data-ttu-id="9ef1e-367">Este código configura un contenedor [Autofac](https://autofac.org/) , lee un valor de configuración para determinar si se deben usar datos reales o ficticios, y pasa esta configuración a un módulo Autofac (se encuentra en el directorio */modules* de la aplicación).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-367">This code configures an [Autofac](https://autofac.org/) container, reads a config setting to determine whether real or mock data should be used, and passes this setting into an Autofac module (found in the app's */Modules* directory).</span></span> <span data-ttu-id="9ef1e-368">Afortunadamente, Autofac es compatible con .NET Core, por lo que el módulo se puede migrar directamente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-368">Fortunately, Autofac supports .NET Core, so the module can be migrated directly.</span></span> <span data-ttu-id="9ef1e-369">Copie la carpeta en el nuevo proyecto y actualice el espacio de nombres de la clase y se debe compilar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-369">Copy the folder into the new project and updates the class's namespace and it should compile.</span></span>

<span data-ttu-id="9ef1e-370">ASP.NET Core tiene compatibilidad integrada para la inserción de dependencias, pero puede conectar un contenedor de terceros como Autofac fácilmente si es necesario.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-370">ASP.NET Core has built-in support for dependency injection, but you can wire up a third-party container such as Autofac easily if necessary.</span></span> <span data-ttu-id="9ef1e-371">En este caso, puesto que la aplicación ya está configurada para usar Autofac, la solución más sencilla consiste en mantener su uso.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-371">In this case, since the app is already configured to use Autofac, the simplest solution is to maintain its usage.</span></span> <span data-ttu-id="9ef1e-372">Para ello, `ConfigureServices` se debe modificar la firma del método para que devuelva un objeto `IServiceProvider` y la instancia del contenedor Autofac debe estar configurada y devuelta desde el método.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-372">To do so, the `ConfigureServices` method signature must be modified to return an `IServiceProvider`, and the Autofac container instance must be configured and returned from the method.</span></span>

<span data-ttu-id="9ef1e-373">**Nota:** En .NET Core 3,0 y versiones posteriores, el proceso de integración de un contenedor de DI de terceros ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-373">**Note:** In .NET Core 3.0 and later, the process for integrating a third-party DI container has changed.</span></span>

<span data-ttu-id="9ef1e-374">Parte de la configuración de Autofac requiere una llamada a `builder.Populate(services)` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-374">Part of configuring Autofac requires a call to `builder.Populate(services)`.</span></span> <span data-ttu-id="9ef1e-375">Esta extensión se encuentra en el `Autofac.Extensions.DependencyInjection` paquete NuGet, que debe instalarse antes de que se compile el código.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-375">This extension is found in the `Autofac.Extensions.DependencyInjection` NuGet package, which must be installed before the code will compile.</span></span>

<span data-ttu-id="9ef1e-376">Después de modificar `ConfigureServices` para configurar un contenedor de Autofac, el nuevo método es como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-376">After modifying `ConfigureServices` to configure an Autofac container, the new method is as shown here:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    bool useMockData = true; // TODO: read from config
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

<span data-ttu-id="9ef1e-377">Por ahora, el valor de `useMockData` se establece en `true` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-377">For now, the setting for `useMockData` is set to `true`.</span></span> <span data-ttu-id="9ef1e-378">Esta configuración se leerá de la configuración en un momento.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-378">This setting will be read from configuration in a moment.</span></span> <span data-ttu-id="9ef1e-379">En este punto, la aplicación se compila y debe cargarse correctamente cuando se ejecuta, como se muestra en la figura 4-12.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-379">At this point, the app compiles and should load successfully when run, as shown in Figure 4-12.</span></span>

![Figura 4-12](media/Figure4-12.png)

<span data-ttu-id="9ef1e-381">**Figura 4-12.**</span><span class="sxs-lookup"><span data-stu-id="9ef1e-381">**Figure 4-12.**</span></span> <span data-ttu-id="9ef1e-382">Aplicación de *eShop* trasladada que se ejecuta localmente con datos ficticios.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-382">Ported *eShop* app running locally with mock data.</span></span>

#### <a name="migrate-app-settings"></a><span data-ttu-id="9ef1e-383">Migrar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9ef1e-383">Migrate app settings</span></span>

<span data-ttu-id="9ef1e-384">ASP.NET Core usa un nuevo [sistema de configuración](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2), que de forma predeterminada aprovecha una *appsettings.jsen* el archivo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-384">ASP.NET Core uses a new [configuration system](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2), which by default leverages an *appsettings.json* file.</span></span> <span data-ttu-id="9ef1e-385">Mediante `CreateDefaultBuilder` el uso de en *Program.CS*, la configuración predeterminada ya está configurada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-385">By using `CreateDefaultBuilder` in *Program.cs*, the default configuration is already set up in the app.</span></span> <span data-ttu-id="9ef1e-386">Para tener acceso a la configuración, las clases solo deben solicitarla en su constructor.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-386">To access configuration, classes just need to request it in their constructor.</span></span> <span data-ttu-id="9ef1e-387">La `Startup` clase no es ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-387">The `Startup` class is no exception.</span></span> <span data-ttu-id="9ef1e-388">Para iniciar el acceso a la configuración en `Startup` y el resto de la aplicación, solicite una instancia de `IConfiguration` a partir de su constructor:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-388">To start accessing configuration in `Startup` and the rest of the app, request an instance of `IConfiguration` from its constructor:</span></span>

```csharp
public Startup(IConfiguration configuration)
{
    Configuration = configuration;
}

public IConfiguration Configuration { get; }
```

<span data-ttu-id="9ef1e-389">La aplicación original hacía referencia a su configuración mediante `ConfigurationManager.AppSettings` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-389">The original app referenced its settings using `ConfigurationManager.AppSettings`.</span></span> <span data-ttu-id="9ef1e-390">Una búsqueda rápida de todas las referencias de este término da como resultado el conjunto de valores que necesita la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-390">A quick search for all references of this term yields the set of settings the new app needs.</span></span> <span data-ttu-id="9ef1e-391">Solo hay dos:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-391">There are only two:</span></span>

- `UseMockData`
- `UseCustomizationData`

<span data-ttu-id="9ef1e-392">Si la aplicación tiene una configuración más compleja, especialmente si usa secciones de configuración personalizadas, es probable que quiera crear y enlazar objetos a diferentes partes de la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-392">If your app has more complex configuration, especially if it's using custom configuration sections, you'll probably want to create and bind objects to different parts of your app's configuration.</span></span> <span data-ttu-id="9ef1e-393">A continuación, se puede tener acceso a estos tipos mediante el [patrón de opciones](../../core/extensions/options.md).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-393">These types can then be accessed using the [options pattern](../../core/extensions/options.md).</span></span> <span data-ttu-id="9ef1e-394">Sin embargo, como se indica en el documento al que se hace referencia, este patrón no debe usarse en `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-394">However, as noted in the referenced doc, this pattern shouldn't be used in `ConfigureServices`.</span></span> <span data-ttu-id="9ef1e-395">En su lugar, la aplicación migrada hará referencia al `UseMockData` valor de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-395">Instead the ported app will reference the `UseMockData` configuration value directly.</span></span>

<span data-ttu-id="9ef1e-396">En primer lugar, modifique el archivo de la aplicación migrada `appsettings.json` y agregue los dos valores en la raíz:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-396">First, modify the ported app's `appsettings.json` file and add the two settings in the root:</span></span>

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "true",
  "UseCustomizationData" :  "true"
}
```

<span data-ttu-id="9ef1e-397">Ahora, modifique `ConfigureServices` para tener acceso a la `UseMockData` configuración de la `Configuration` propiedad (en la que previamente se establece el valor en `true` ):</span><span class="sxs-lookup"><span data-stu-id="9ef1e-397">Now, modify `ConfigureServices` to access the `UseMockData` setting from the `Configuration` property (where previously we set the value to `true`):</span></span>

```csharp
  bool useMockData = Configuration.GetValue<bool>("UseMockData");
```

<span data-ttu-id="9ef1e-398">En este momento, la configuración se extrae de la configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-398">At this point, the setting is pulled from configuration.</span></span> <span data-ttu-id="9ef1e-399">El otro valor, `UseCustomizationData` , lo utiliza la `CatalogDBInitializer` clase.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-399">The other setting, `UseCustomizationData`, is used by the `CatalogDBInitializer` class.</span></span> <span data-ttu-id="9ef1e-400">La primera vez que se portó esta clase, se marca el acceso a `ConfigurationManager.AppSettings["UseCustomizationData"]` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-400">When you first ported this class, you commented out the access to `ConfigurationManager.AppSettings["UseCustomizationData"]`.</span></span> <span data-ttu-id="9ef1e-401">Ahora es el momento de modificarlo para usar ASP.NET Core configuración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-401">Now it's time to modify it to use ASP.NET Core configuration.</span></span> <span data-ttu-id="9ef1e-402">Modifique el constructor de de la `CatalogDBInitializer` siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-402">Modify the constructor of `CatalogDBInitializer` as follows:</span></span>

```csharp
  // add using Microsoft.Extensions.Configuration
  public CatalogDBInitializer(CatalogItemHiLoGenerator indexGenerator,
      IConfiguration configuration)
  {
      this.indexGenerator = indexGenerator;
      useCustomizationData = configuration.GetValue<bool>("UseCustomizationData");
  }
```

<span data-ttu-id="9ef1e-403">Todo acceso a la configuración dentro de la aplicación Web debe modificarse de esta manera para usar el nuevo `IConfiguration` tipo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-403">All access to configuration within the web app should be modified in this manner to use the new `IConfiguration` type.</span></span> <span data-ttu-id="9ef1e-404">Las dependencias que requieren acceso a la configuración de .NET Framework pueden incluir estos valores en un archivo *app.config* agregado al proyecto Web.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-404">Dependencies that require access to .NET Framework configuration can include such settings in an *app.config* file added to the web project.</span></span> <span data-ttu-id="9ef1e-405">Los proyectos dependientes pueden trabajar con `ConfigurationManager` para obtener acceso a la configuración y no deben realizar cambios si ya utilizan este enfoque.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-405">The dependent projects can work with `ConfigurationManager` to access settings, and shouldn't require any changes if they already use this approach.</span></span> <span data-ttu-id="9ef1e-406">Sin embargo, como ASP.NET Core aplicaciones se ejecutan como su propio ejecutable, no hacen referencia a *web.config* sino *app.config*. Al migrar la configuración del archivo de *web.config* de la aplicación heredada a un nuevo archivo de *app.config* en la aplicación ASP.net Core, los componentes que usan `ConfigurationManager` para tener acceso a su configuración seguirán funcionando correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-406">However, since ASP.NET Core apps run as their own executable, they don't reference *web.config* but rather *app.config*. By migrating settings from the legacy app's *web.config* file to a new *app.config* file in the ASP.NET Core app, components that use `ConfigurationManager` to access their settings will continue to function properly.</span></span>

<span data-ttu-id="9ef1e-407">La migración de la aplicación está casi completa.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-407">The app's migration is nearly complete.</span></span> <span data-ttu-id="9ef1e-408">La única tarea restante es la configuración de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-408">The only remaining task is data access configuration.</span></span>
  
## <a name="data-access-considerations"></a><span data-ttu-id="9ef1e-409">Consideraciones sobre el acceso a datos</span><span class="sxs-lookup"><span data-stu-id="9ef1e-409">Data access considerations</span></span>

<span data-ttu-id="9ef1e-410">ASP.NET Core aplicaciones que se ejecutan en .NET Framework pueden seguir aprovechando Entity Framework (EF).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-410">ASP.NET Core apps running on .NET Framework can continue to leverage Entity Framework (EF).</span></span> <span data-ttu-id="9ef1e-411">Si realiza una migración incremental, el hecho de que la aplicación funcione con EF 6 antes de intentar migrar su acceso a datos para usar EF Core puede merecer la pena.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-411">If performing an incremental migration, getting the app working with EF 6 before trying to port its data access to use EF Core may be worthwhile.</span></span> <span data-ttu-id="9ef1e-412">De esta manera, cualquier problema con la migración de la aplicación puede identificarse y abordarse antes de que se haya iniciado otro bloque de trabajo de migración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-412">In this way, any problems with the app's migration can be identified and addressed before another block of migration effort is begun.</span></span>

<span data-ttu-id="9ef1e-413">Como sucede, la configuración de EF 6 en la migración de ejemplo de eShop no requiere ningún trabajo especial, ya que este trabajo se realizó en Autofac `ApplicationModule` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-413">As it happens, configuring EF 6 in the eShop sample migration doesn't require any special work, since this work was performed in the Autofac `ApplicationModule`.</span></span> <span data-ttu-id="9ef1e-414">El único problema es que actualmente la `CatalogDBContext` clase intenta leer su cadena de conexión de *web.config*. Para solucionar este paso, es necesario agregar los detalles de conexión para *appsettings.jsen*.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-414">The only problem is that currently the `CatalogDBContext` class tries to read its connection string from *web.config*. To address this, the connection details need to be added to *appsettings.json*.</span></span> <span data-ttu-id="9ef1e-415">A continuación, se debe pasar la cadena de conexión `CatalogDBContext` cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-415">Then the connection string must be passed into `CatalogDBContext` when it's created.</span></span>

<span data-ttu-id="9ef1e-416">Actualice el *appsettings.jsen* para incluir la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-416">Update the *appsettings.json* to include the connection string.</span></span> <span data-ttu-id="9ef1e-417">El archivo completo se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-417">The full file is listed here:</span></span>

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=eShopPorted;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "false",
  "UseCustomizationData": "true"
}
```

<span data-ttu-id="9ef1e-418">La cadena de conexión se debe pasar al constructor cuando `DbContext` se crea.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-418">The connection string must be passed into the constructor when the `DbContext` is created.</span></span> <span data-ttu-id="9ef1e-419">Dado que las instancias se crean mediante Autofac, el cambio debe realizarse en `ApplicationModule` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-419">Since the instances are created by Autofac, the change needs to be made in `ApplicationModule`.</span></span> <span data-ttu-id="9ef1e-420">Modifique el módulo para que tome en `connectionString` su constructor y asígnelo a un campo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-420">Modify the module to take in a `connectionString` in its constructor and assign it to a field.</span></span> <span data-ttu-id="9ef1e-421">A continuación, modifique el registro de `CatalogDBContext` para agregar la cadena de conexión como parámetro:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-421">Then modify the registration for `CatalogDBContext` to add connection string as a parameter:</span></span>

```csharp
builder.RegisterType<CatalogDBContext>()
  .WithParameter("connectionString", _connectionString)
  .InstancePerLifetimeScope();
```

<span data-ttu-id="9ef1e-422">El parámetro también debe agregarse a una nueva sobrecarga del constructor en `CatalogDBContext` sí mismo:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-422">The parameter must also be added to a new constructor overload in `CatalogDBContext` itself:</span></span>

```csharp
public CatalogDBContext(string connectionString) : base(connectionString)
{
}
```

<span data-ttu-id="9ef1e-423">Por último, `ConfigureServices` debe leer la cadena de conexión de `Config` y pasarla a `ApplicationModule` cuando cree una instancia de ella:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-423">Finally, `ConfigureServices` must read the connection string from `Config` and pass it into the `ApplicationModule` when it instantiates it:</span></span>

```csharp
bool useMockData = Configuration.GetValue<bool>("UseMockData");
string connectionString = Configuration.GetConnectionString("DefaultConnection");
builder.RegisterModule(new ApplicationModule(useMockData, connectionString));
```

<span data-ttu-id="9ef1e-424">Con este código en su lugar, la aplicación se ejecuta como antes, conectándose a una base de datos de SQL Server cuando `UseMockData` es `false` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-424">With this code in place, the app runs as it did before, connecting to a SQL Server database when `UseMockData` is `false`.</span></span>

<span data-ttu-id="9ef1e-425">La aplicación se puede implementar y ejecutar en producción en este momento, convertirla en ASP.NET Core pero seguir ejecutándose en .NET Framework y EF 6.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-425">The app can be deployed and run in production at this point, converted to ASP.NET Core but still running on .NET Framework and EF 6.</span></span> <span data-ttu-id="9ef1e-426">Si lo desea, se puede migrar la aplicación para que se ejecute en .NET Core y Entity Framework Core, lo que aportará más ventajas que se describen en los capítulos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-426">If desired, the app can be migrated to run on .NET Core and Entity Framework Core, which will bring additional advantages described in earlier chapters.</span></span> <span data-ttu-id="9ef1e-427">Específico de Entity Framework, [esta documentación compara EF Core y EF 6](/ef/efcore-and-ef6/) e incluye una cuadrícula que muestra la biblioteca que admite cada una de las docenas de características individuales.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-427">Specific to Entity Framework, [this documentation compares EF Core and EF 6](/ef/efcore-and-ef6/) and includes a grid showing which library supports each of dozens of individual features.</span></span>

### <a name="migrate-to-entity-framework-core"></a><span data-ttu-id="9ef1e-428">Migrar a Entity Framework Core</span><span class="sxs-lookup"><span data-stu-id="9ef1e-428">Migrate to Entity Framework Core</span></span>

<span data-ttu-id="9ef1e-429">Suponiendo que se haya tomado la decisión de migrar a EF Core, los pasos pueden ser bastante sencillos, especialmente si la aplicación original usaba un enfoque de modelo basado en código.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-429">Assuming a decision is made to migrate to EF Core, the steps can be fairly straightforward, especially if the original app used a code-based model approach.</span></span> <span data-ttu-id="9ef1e-430">Al [preparar el puerto de EF 6 a EF Core](/ef/efcore-and-ef6/porting/), revise la disponibilidad de las características en la versión de destino de EF Core que va a usar.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-430">When [preparing to port from EF 6 to EF Core](/ef/efcore-and-ef6/porting/), review the availability of features in the destination version of EF Core you'll be using.</span></span> <span data-ttu-id="9ef1e-431">Revise la documentación sobre la [migración desde y el modelo basado en EDMX](/ef/efcore-and-ef6/porting/port-edmx) en comparación con la [migración de un modelo basado en código](/ef/efcore-and-ef6/porting/port-code).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-431">Review the documentation on [porting from and EDMX-based model](/ef/efcore-and-ef6/porting/port-edmx) versus [porting from a code-based model](/ef/efcore-and-ef6/porting/port-code).</span></span>

<span data-ttu-id="9ef1e-432">Para actualizar a EF Core 2,2, los pasos básicos que conlleva son agregar los paquetes de NuGet adecuados y actualizar los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-432">To upgrade to EF Core 2.2, the basic steps involved are to add the appropriate NuGet package(s) and update namespaces.</span></span> <span data-ttu-id="9ef1e-433">A continuación, ajuste el modo en que se pasa la cadena de conexión al `DbContext` tipo y cómo se conecta para la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-433">Then adjust how the connection string is passed to the `DbContext` type and how they're wired up for dependency injection.</span></span>

<span data-ttu-id="9ef1e-434">EF Core se agrega como una referencia de paquete al proyecto:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-434">EF Core is added as a package reference to the project:</span></span>

```xml
<PackageReference Include="Microsoft.EntityFrameworkCore" Version="2.2.6" />
```

<span data-ttu-id="9ef1e-435">Se quita la referencia a EF 6:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-435">The reference to EF 6 is removed:</span></span>

```xml
<PackageReference Include="EntityFramework" Version="6.2.0" />
```

<span data-ttu-id="9ef1e-436">El compilador notificará los errores en `CatalogDBContext` y `CatalogDBInitializer` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-436">The compiler will report errors in `CatalogDBContext` and `CatalogDBInitializer`.</span></span> <span data-ttu-id="9ef1e-437">`CatalogDbContext` es necesario que los espacios de nombres antiguos se hayan quitado y se hayan reemplazado por `Microsoft.EntityFrameworkCore` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-437">`CatalogDbContext` needs to have the old namespaces removed and replaced with `Microsoft.EntityFrameworkCore`.</span></span> <span data-ttu-id="9ef1e-438">Se pueden quitar sus constructores.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-438">Its constructors can be removed.</span></span> <span data-ttu-id="9ef1e-439">`DbModelBuilder` debe reemplazarse por `ModelBuilder` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-439">`DbModelBuilder` should be replaced with `ModelBuilder`.</span></span> <span data-ttu-id="9ef1e-440">Los métodos auxiliares para configurar tipos se mueven a clases independientes que implementan `IEntityTypeConfiguration<T>` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-440">The helper methods for configuring types are moved to separate classes implementing `IEntityTypeConfiguration<T>`.</span></span> <span data-ttu-id="9ef1e-441">A continuación, el `CatalogDBContext` método de la clase `OnModelCreating` simplemente se convierte en:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-441">Then the `CatalogDBContext` class's `OnModelCreating` method simply becomes:</span></span>

```csharp
protected override void OnModelCreating(ModelBuilder builder)
{
    builder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());

    base.OnModelCreating(builder);
}
```

<span data-ttu-id="9ef1e-442">Otros cambios implicados incluyen:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-442">Other changes involved include:</span></span>

- <span data-ttu-id="9ef1e-443">`HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` reemplazado por `ValueGeneratedNever()`</span><span class="sxs-lookup"><span data-stu-id="9ef1e-443">`HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` replaced with `ValueGeneratedNever()`</span></span>
- <span data-ttu-id="9ef1e-444">`HasRequired<T>` reemplazado por `HasOne<T>`</span><span class="sxs-lookup"><span data-stu-id="9ef1e-444">`HasRequired<T>` replaced with `HasOne<T>`</span></span>
- <span data-ttu-id="9ef1e-445">`Microsoft.EntityFrameworkCore.Relational`Paquete instalado</span><span class="sxs-lookup"><span data-stu-id="9ef1e-445">Installed `Microsoft.EntityFrameworkCore.Relational` package</span></span>
- <span data-ttu-id="9ef1e-446">Agregar un constructor para `CatalogDBContext` tomarlo `DbContextOptions` y pasarlo al constructor base</span><span class="sxs-lookup"><span data-stu-id="9ef1e-446">Add a constructor to `CatalogDBContext` taking `DbContextOptions` and passing it to the base constructor</span></span>

<span data-ttu-id="9ef1e-447">Aquí se muestra una clase de configuración de ejemplo para `CatalogType` :</span><span class="sxs-lookup"><span data-stu-id="9ef1e-447">An example configuration class for `CatalogType` is shown here:</span></span>

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

namespace eShopPorted.Models.Config
{
    public class CatalogTypeConfig : IEntityTypeConfiguration<CatalogType>
    {
        public void Configure(EntityTypeBuilder<CatalogType> builder)
        {
            builder.ToTable(nameof(CatalogType));

            builder.HasKey(ci => ci.Id);

            builder.Property(ci => ci.Id)
               .IsRequired();

            builder.Property(cb => cb.Type)
                .IsRequired()
                .HasMaxLength(100);
        }
    }
}
```

<span data-ttu-id="9ef1e-448">`CatalogDBInitializer`Y su clase base, `CreateDatabaseIfNotExists<T>` , son incompatibles con EF Core.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-448">The `CatalogDBInitializer` and its base class, `CreateDatabaseIfNotExists<T>`, are incompatible with EF Core.</span></span> <span data-ttu-id="9ef1e-449">El propósito de esta clase es crear e inicializar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-449">The purpose of this class is to create and seed the database.</span></span> <span data-ttu-id="9ef1e-450">[El uso de EF Core creará y quitará la base `DbContext` de datos asociada para un](/ef/core/managing-schemas/ensure-created) mediante estos métodos:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-450">Using EF Core will [create and drop the associated database for a `DbContext`](/ef/core/managing-schemas/ensure-created) using these methods:</span></span>

```csharp
dbContext.Database.EnsureDeleted();
dbContext.Database.EnsureCreated();
```

<span data-ttu-id="9ef1e-451">La propagación de datos en EF Core se puede realizar con scripts manuales o como parte de la configuración del tipo.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-451">Seeding data in EF Core can be done with manual scripts, or as part of the type configuration.</span></span> <span data-ttu-id="9ef1e-452">Junto con otras propiedades de entidad, los datos de inicialización se pueden configurar en `IEntityTypeConfiguration` clases mediante `builder.HasData()` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-452">Along with other entity properties, seed data can be configured in `IEntityTypeConfiguration` classes by using `builder.HasData()`.</span></span> <span data-ttu-id="9ef1e-453">La aplicación original cargó datos de inicialización de archivos CSV en el directorio de *instalación* .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-453">The original app loaded seed data from CSV files in the *Setup* directory.</span></span> <span data-ttu-id="9ef1e-454">Dado que solo hay unos pocos elementos, estos registros de datos se pueden agregar como parte de la configuración de la entidad.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-454">Given that there are only a handful of items, these data records can instead be added as part of the entity configuration.</span></span> <span data-ttu-id="9ef1e-455">Este enfoque funciona bien para los datos de búsqueda en tablas que cambian con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-455">This approach works well for lookup data in tables that change infrequently.</span></span> <span data-ttu-id="9ef1e-456">Agregar lo siguiente al `CatalogTypeConfig` `Configure` método de garantiza que las filas asociadas están presentes cuando se crea la base de datos:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-456">Adding the following to `CatalogTypeConfig`'s `Configure` method ensures the associated rows are present when the database is created:</span></span>

```csharp
builder.HasData(
    new CatalogType { Id = 1, Type = "Mug" },
    new CatalogType { Id = 2, Type = "T-Shirt" },
    new CatalogType { Id = 3, Type = "Sheet" },
    new CatalogType { Id = 4, Type = "USB Memory Stick" }
);
```

<span data-ttu-id="9ef1e-457">La aplicación inicial incluye una `PreconfiguredData` clase, que incluye los datos de `CatalogBrand` y `CatalogType` , por lo que el uso de este método `HasData` reduce la llamada a:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-457">The initial app includes a `PreconfiguredData` class, which includes data for `CatalogBrand` and `CatalogType`, so using this method the `HasData` call reduces to:</span></span>

```csharp
builder.HasData(
    PreconfiguredData.GetPreconfiguredCatalogBrands()
);
```

<span data-ttu-id="9ef1e-458">Los `CatalogItem` datos también se pueden extraer de `PreconfiguredData` y, suponiendo que las imágenes asociadas se mantienen en el control de código fuente, es la última tabla necesaria para que la aplicación funcione.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-458">The `CatalogItem` data can also be pulled from `PreconfiguredData`, and assuming the associated images are kept in source control, that is the last table needed for the app to function.</span></span> <span data-ttu-id="9ef1e-459">La `CatalogDBInitializer` clase se puede quitar, junto con las referencias a ella.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-459">The `CatalogDBInitializer` class can be removed, along with any references to it.</span></span> <span data-ttu-id="9ef1e-460">`CatalogItemHiLoGenerator`También se quitan la clase y los archivos SQL del `Infrastructure` directorio, junto con las referencias a ellos (en `CatalogService` , `ApplicationModule` ).</span><span class="sxs-lookup"><span data-stu-id="9ef1e-460">The `CatalogItemHiLoGenerator` class and the SQL files in the `Infrastructure` directory are also removed, along with any references to them (in `CatalogService`, `ApplicationModule`).</span></span>

<span data-ttu-id="9ef1e-461">Con la eliminación de las clases de generador de claves especiales para `CatalogItem` , este código ahora se quita de `CatalogItemConfig` :</span><span class="sxs-lookup"><span data-stu-id="9ef1e-461">With the elimination of the special key generator classes for `CatalogItem`, this code now is removed from `CatalogItemConfig`:</span></span>

```csharp
builder.Property(ci => ci.Id)
    .ValueGeneratedNever()
    .IsRequired();
```

<span data-ttu-id="9ef1e-462">Con estas modificaciones, la aplicación ASP.NET Core se compila, pero aún no funciona con EF Core, que todavía se debe configurar para la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-462">With these modifications, the ASP.NET Core app builds, but it doesn't yet work with EF Core, which must still be configured for dependency injection.</span></span> <span data-ttu-id="9ef1e-463">Con EF Core, la manera más sencilla de configurarla es en `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="9ef1e-463">With EF Core, the simplest way to configure it is in `ConfigureServices`:</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    bool useMockData = Configuration.GetValue<bool>("UseMockData");
    if (!useMockData)
    {
        string connectionString = Configuration.GetConnectionString("DefaultConnection");

        services.AddDbContext<CatalogDBContext>(options =>
            options.UseSqlServer(connectionString)
        );
    }

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

<span data-ttu-id="9ef1e-464">La versión final de Autofac `ApplicationModule` solo configura un tipo, en función de si la aplicación está configurada para usar datos ficticios:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-464">The final version of Autofac's `ApplicationModule` only configures one type, depending on whether the app is configured to use mock data:</span></span>

```csharp
public class ApplicationModule : Module
{
    private bool _useMockData;

    public ApplicationModule(bool useMockData)
    {
        _useMockData = useMockData;
    }

    protected override void Load(ContainerBuilder builder)
    {
        if (_useMockData)
        {
            builder.RegisterType<CatalogServiceMock>()
                .As<ICatalogService>()
                .SingleInstance();
        }
        else
        {
            builder.RegisterType<CatalogService>()
                .As<ICatalogService>()
                .InstancePerLifetimeScope();
        }
    }
}
```

<span data-ttu-id="9ef1e-465">La aplicación migrada se ejecuta, pero no muestra ningún dato si está configurado para usar datos no ficticios.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-465">The ported app runs, but doesn't display any data if configured to use non-mock data.</span></span> <span data-ttu-id="9ef1e-466">Los datos de inicialización agregados mediante `HasData` solo se insertan cuando se aplican las migraciones.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-466">The seed data added through `HasData` is only inserted when migrations are applied.</span></span> <span data-ttu-id="9ef1e-467">La aplicación de origen no usó migraciones y, si la hubiera, no se migraría tal cual.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-467">The source app didn't use migrations, and if it had, they wouldn't migrate as-is.</span></span> <span data-ttu-id="9ef1e-468">El mejor enfoque es empezar con un nuevo script de migración.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-468">The best approach is to start with a new migration script.</span></span> <span data-ttu-id="9ef1e-469">Para ello, agregue una referencia de paquete para `Microsoft.EntityFrameworkCore.Design` y abra una ventana de terminal en la raíz del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-469">To do this, add a package reference for `Microsoft.EntityFrameworkCore.Design` and open a terminal window in the project root.</span></span> <span data-ttu-id="9ef1e-470">A continuación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-470">Then run:</span></span>

```dotnetcli
dotnet ef migrations add Initial
```

<span data-ttu-id="9ef1e-471">Quite la base de datos de *eShopPorted* existente si existe y, a continuación, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-471">Drop the existing *eShopPorted* database if it exists, then run:</span></span>

```dotnetcli
dotnet ef database update
```

<span data-ttu-id="9ef1e-472">Así se crea y se inicializa la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-472">This creates and seeds the database.</span></span> <span data-ttu-id="9ef1e-473">Ahora está listo para ejecutarse, con algunas pequeñas actualizaciones que quedan en dirección.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-473">It's now ready to run, with a few small updates left to address.</span></span>

## <a name="fix-all-todo-tasks"></a><span data-ttu-id="9ef1e-474">Corregir todas las tareas TODO</span><span class="sxs-lookup"><span data-stu-id="9ef1e-474">Fix all TODO tasks</span></span>

<span data-ttu-id="9ef1e-475">La ejecución de la aplicación migrada en este momento revela que no se muestra ninguna imagen en la página.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-475">Running the ported app at this point reveals that no pictures are shown on the page.</span></span> <span data-ttu-id="9ef1e-476">Esto se debe a que la `PictureUri` propiedad de `CatalogItem` nunca se establece.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-476">This is because the `PictureUri` property of `CatalogItem` is never set.</span></span> <span data-ttu-id="9ef1e-477">Al examinar la lista de `TODO` elementos que creamos con el **lista de tareas** de Visual Studio, el único que permanece en `CatalogController` , con una nota para "hacer referencia a PIC desde wwwroot".</span><span class="sxs-lookup"><span data-stu-id="9ef1e-477">Looking at the list of `TODO` items we created using Visual Studio's **Task List**, the only one that remains is in `CatalogController`, with a note to "Reference pic from wwwroot."</span></span> <span data-ttu-id="9ef1e-478">El código en cuestión es:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-478">The code in question is:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    //TODO: Reference pic from wwwroot
    //item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

<span data-ttu-id="9ef1e-479">La solución más sencilla consiste en hacer referencia a los archivos de imagen públicos en el directorio público de *wwwroot/pics* del sitio.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-479">The simplest fix is to reference the public image files in the site's public *wwwroot/Pics* directory.</span></span> <span data-ttu-id="9ef1e-480">Esta tarea se puede llevar a cabo reemplazando el método por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-480">This task can be accomplished by replacing the method with the following code:</span></span>

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = $"/Pics/{item.Id}.png";
}
```

<span data-ttu-id="9ef1e-481">Con este cambio, la ejecución de la aplicación revela que las imágenes funcionan como antes.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-481">With this change, running the app reveals the images work as before.</span></span>

## <a name="additional-mvc-customizations"></a><span data-ttu-id="9ef1e-482">Personalizaciones de MVC adicionales</span><span class="sxs-lookup"><span data-stu-id="9ef1e-482">Additional MVC customizations</span></span>

<span data-ttu-id="9ef1e-483">La aplicación *eShopLegacyMVC* es bastante simple, por lo que no hay mucho que configurar en términos de comportamiento predeterminado de MVC.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-483">The *eShopLegacyMVC* app is fairly simple, so there isn't much to configure in terms of default MVC behavior.</span></span> <span data-ttu-id="9ef1e-484">Sin embargo, si necesita configurar componentes de MVC adicionales, como CORS, filtros y restricciones de ruta, normalmente proporciona esta información en `Startup.ConfigureServices` , donde `UseMvc` se llama a.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-484">However, if you do need to configure additional MVC components, such as CORS, filters, and route constraints, you generally provide this information in `Startup.ConfigureServices`, where `UseMvc` is called.</span></span> <span data-ttu-id="9ef1e-485">Por ejemplo, en la lista de código siguiente se configura [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) y se configura un filtro de acción global:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-485">For example, the following code listing configures [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) and sets up a global action filter:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddCors(options =>
    {
        options.AddPolicy(MyAllowSpecificOrigins,
            builder =>
                builder.WithOrigins("http://example.com", "http://www.contoso.com")
                    .AllowAnyHeader()
                    .AllowAnyMethod());
    });

    services.AddMvc(options =>
    {
      options.Filters.Add(new SampleGlobalActionFilter());
    }).SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```

> [!Note]
> <span data-ttu-id="9ef1e-486">Para finalizar la configuración de CORS, también debe llamar a `app.UseCors()` en `Configure` .</span><span class="sxs-lookup"><span data-stu-id="9ef1e-486">To finish configuring CORS, you must also call `app.UseCors()` in `Configure`.</span></span>

<span data-ttu-id="9ef1e-487">Otros escenarios avanzados, como agregar [enlazadores de modelos personalizados](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), formateadores, etc., se explican en los documentos de ASP.net Core detallados. Por lo general, se pueden aplicar en un controlador o en una función individual, o globalmente con el mismo enfoque de opciones que se muestra en la lista de código anterior.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-487">Other advanced scenarios, like adding [custom model binders](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), formatters, and more are covered in the detailed ASP.NET Core docs. Generally these can be applied on an individual controller or action basis, or globally using the same options approach shown in the previous code listing.</span></span>

## <a name="other-dependencies"></a><span data-ttu-id="9ef1e-488">Otras dependencias</span><span class="sxs-lookup"><span data-stu-id="9ef1e-488">Other dependencies</span></span>

<span data-ttu-id="9ef1e-489">Las dependencias que usan características de .NET Framework que tenían una dependencia en el modelo de configuración heredado, como el tipo de cliente de WCF y el código de seguimiento, deben modificarse cuando se portan.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-489">Dependencies that use .NET Framework features that had a dependency on the legacy configuration model, such as the WCF client type and tracing code, must be modified when ported.</span></span> <span data-ttu-id="9ef1e-490">En lugar de que estos tipos extraigan su información de configuración directamente, deben configurarse en el código.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-490">Rather than having these types pull in their configuration information directly, they should be configured in code.</span></span> <span data-ttu-id="9ef1e-491">Por ejemplo, una conexión a un servicio WCF que se configuró en el *web.config* de la aplicación ASP.net que se va a usar `basicHttpBinding` podría configurarse mediante programación con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ef1e-491">For example, a connection to a WCF service that was configured in an ASP.NET app's *web.config* to use `basicHttpBinding` could instead be configured programmatically with the following code:</span></span>

```csharp
var binding = new BasicHttpBinding();
binding.MaxReceivedMessageSize = 2_000_000;

var endpointAddress = new EndpointAddress("http://localhost:9200/ExampleService");

var myClient = new MyServiceClient(binding, endpointAddress);
```

<span data-ttu-id="9ef1e-492">En lugar de basarse en los archivos de configuración para su configuración, los clientes de WCF y otros tipos de .NET Framework deben tener su configuración especificada en el código.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-492">Rather than relying on config files for its settings, WCF clients and other .NET Framework types should have their settings specified in code.</span></span> <span data-ttu-id="9ef1e-493">De esta manera, estos tipos pueden seguir funcionando en ASP.NET Core aplicaciones 2,2.</span><span class="sxs-lookup"><span data-stu-id="9ef1e-493">Configured in this manner, these types can continue to work in ASP.NET Core 2.2 apps.</span></span>

## <a name="references"></a><span data-ttu-id="9ef1e-494">Referencias</span><span class="sxs-lookup"><span data-stu-id="9ef1e-494">References</span></span>

- [<span data-ttu-id="9ef1e-495">repositorio de GitHub de eShopModernizing</span><span class="sxs-lookup"><span data-stu-id="9ef1e-495">eShopModernizing GitHub repository</span></span>](https://github.com/dotnet-architecture/eShopModernizing)
- [<span data-ttu-id="9ef1e-496">Herramienta del Asistente para actualización de .NET</span><span class="sxs-lookup"><span data-stu-id="9ef1e-496">.NET Upgrade Assistant tool</span></span>](https://aka.ms/dotnet-upgrade-assistant)
- [<span data-ttu-id="9ef1e-497">La API y ViewModels no deben hacer referencia a los modelos de dominio</span><span class="sxs-lookup"><span data-stu-id="9ef1e-497">Your API and ViewModels Should Not Reference Domain Models</span></span>](https://ardalis.com/your-api-and-view-models-should-not-reference-domain-models/)
- [<span data-ttu-id="9ef1e-498">Middleware de la página de excepciones para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="9ef1e-498">Developer Exception Page Middleware</span></span>](/aspnet/core/fundamentals/error-handling#developer-exception-page)
- [<span data-ttu-id="9ef1e-499">Profundice en EF Core HasData</span><span class="sxs-lookup"><span data-stu-id="9ef1e-499">Deep Dive into EF Core HasData</span></span>](/archive/msdn-magazine/2018/august/data-points-deep-dive-into-ef-core-hasdata-seeding)

>[!div class="step-by-step"]
><span data-ttu-id="9ef1e-500">[Anterior](more-migration-scenarios.md)
>[Siguiente](deployment-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="9ef1e-500">[Previous](more-migration-scenarios.md)
[Next](deployment-scenarios.md)</span></span>

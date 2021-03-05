---
title: Ejemplo de migración a .NET 5
description: Muestra cómo migrar una aplicación de ejemplo que tiene como destino .NET Framework a .NET 5.
ms.date: 01/19/2021
ms.openlocfilehash: 5b3743c68ee0426efffda6f999dffea788f493e9
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206547"
---
# <a name="example-of-migrating-to-net"></a><span data-ttu-id="50a33-103">Ejemplo de migración a .NET</span><span class="sxs-lookup"><span data-stu-id="50a33-103">Example of migrating to .NET</span></span>

<span data-ttu-id="50a33-104">En este capítulo, presentamos instrucciones prácticas que le ayudarán a realizar una migración de la aplicación existente desde .NET Framework a .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-104">In this chapter, we present practical guidelines to help you perform a migration of your existing application from .NET Framework to .NET.</span></span>

<span data-ttu-id="50a33-105">Presentamos un proceso bien estructurado que puede seguir y los aspectos más importantes que se deben tener en cuenta en cada paso.</span><span class="sxs-lookup"><span data-stu-id="50a33-105">We present a well-structured process you can follow and the most important things to consider on each step.</span></span>

<span data-ttu-id="50a33-106">A continuación, documentamos un proceso de migración paso a paso para una aplicación de escritorio de ejemplo, tanto de las versiones de WinForms como de WPF.</span><span class="sxs-lookup"><span data-stu-id="50a33-106">We then document a step-by-step migration process for a sample desktop application, both from WinForms and WPF versions.</span></span>

## <a name="migration-process-overview"></a><span data-ttu-id="50a33-107">Introducción al proceso de migración</span><span class="sxs-lookup"><span data-stu-id="50a33-107">Migration process overview</span></span>

<span data-ttu-id="50a33-108">El proceso de migración consta de cuatro pasos secuenciales:</span><span class="sxs-lookup"><span data-stu-id="50a33-108">The migration process consists of four sequential steps:</span></span>

1. <span data-ttu-id="50a33-109">**Preparación**: comprenda las dependencias que el proyecto tiene para tener una idea del avance.</span><span class="sxs-lookup"><span data-stu-id="50a33-109">**Preparation**: Understand the dependencies the project has to have an idea of what's ahead.</span></span> <span data-ttu-id="50a33-110">En este paso, se toma el proyecto actual en un estado que simplifica el punto de inicio de la migración.</span><span class="sxs-lookup"><span data-stu-id="50a33-110">In this step, you take the current project into a state that simplifies the startup point for the migration.</span></span>

2. <span data-ttu-id="50a33-111">**Migrar archivo de proyecto:** los proyectos de .net usan el nuevo formato de proyecto de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="50a33-111">**Migrate Project File:** .NET projects use the new SDK-style project format.</span></span> <span data-ttu-id="50a33-112">Cree un nuevo archivo de proyecto con este formato o actualice el que tenga para usar el estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="50a33-112">Create a new project file with this format or update the one you have to use the SDK style.</span></span>

3. <span data-ttu-id="50a33-113">**Corregir código y compilar:** Compile el código en .NET para resolver las diferencias de nivel de API entre .NET Framework y .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-113">**Fix code and build:** Build the code in .NET addressing API-level differences between .NET Framework and .NET.</span></span> <span data-ttu-id="50a33-114">Si es necesario, actualice los paquetes de terceros a los que admiten .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-114">If needed, update third-party packages to the ones that support .NET.</span></span>

4. <span data-ttu-id="50a33-115">**Ejecutar y probar:** Puede haber diferencias que no se muestren hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="50a33-115">**Run and test:** There might be differences that don't show up until run time.</span></span> <span data-ttu-id="50a33-116">Por lo tanto, no olvide ejecutar la aplicación y comprobar que todo funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="50a33-116">So, don't forget to run the application and test that everything works as expected.</span></span>

### <a name="preparation"></a><span data-ttu-id="50a33-117">Preparación</span><span class="sxs-lookup"><span data-stu-id="50a33-117">Preparation</span></span>

#### <a name="migrate-packagesconfig-file"></a><span data-ttu-id="50a33-118">Migrar archivo de packages.config</span><span class="sxs-lookup"><span data-stu-id="50a33-118">Migrate packages.config file</span></span>

<span data-ttu-id="50a33-119">En una aplicación .NET Framework, todas las referencias a paquetes externos se declaran en el archivo de *packages.config* .</span><span class="sxs-lookup"><span data-stu-id="50a33-119">In a .NET Framework application, all references to external packages are declared in the *packages.config* file.</span></span> <span data-ttu-id="50a33-120">En .NET, ya no es necesario usar el archivo de *packages.config* .</span><span class="sxs-lookup"><span data-stu-id="50a33-120">In .NET, there's no longer the need to use the *packages.config* file.</span></span> <span data-ttu-id="50a33-121">En su lugar, use la propiedad [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) en el archivo de proyecto para especificar los paquetes de NuGet para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50a33-121">Instead, use the [PackageReference](../../core/project-sdk/msbuild-props.md#packagereference) property inside the project file to specify the NuGet packages for your app.</span></span>

<span data-ttu-id="50a33-122">Por lo tanto, debe realizar la transición de un formato a otro.</span><span class="sxs-lookup"><span data-stu-id="50a33-122">So, you need to transition from one format to another.</span></span> <span data-ttu-id="50a33-123">Puede realizar la actualización manualmente, tomando las dependencias contenidas en el archivo de *packages.config* y migrarlas al archivo de proyecto con el `PackageReference` formato.</span><span class="sxs-lookup"><span data-stu-id="50a33-123">You can do the update manually, taking the dependencies contained in the *packages.config* file and migrating them to the project file with the `PackageReference` format.</span></span> <span data-ttu-id="50a33-124">O bien, puede dejar que Visual Studio haga el trabajo por usted: haga clic con el botón derecho en el archivo de *packages.config* y seleccione la opción **migrar packages.config a PackageReference** .</span><span class="sxs-lookup"><span data-stu-id="50a33-124">Or, you can let Visual Studio do the work for you: right-click on the *packages.config* file and select the **Migrate packages.config to PackageReference** option.</span></span>

#### <a name="verify-every-dependency-compatibility-in-net"></a><span data-ttu-id="50a33-125">Comprobar la compatibilidad de todas las dependencias en .NET</span><span class="sxs-lookup"><span data-stu-id="50a33-125">Verify every dependency compatibility in .NET</span></span>

<span data-ttu-id="50a33-126">Una vez que haya migrado las referencias de paquete, debe comprobar la compatibilidad de cada referencia.</span><span class="sxs-lookup"><span data-stu-id="50a33-126">Once you've migrated the package references, you must check each reference for compatibility.</span></span> <span data-ttu-id="50a33-127">Puede explorar las dependencias de cada paquete NuGet que está usando la aplicación en [Nuget.org](https://www.nuget.org/). Si el paquete tiene dependencias .NET Standard, se va a trabajar en .NET 5,0 porque .NET [es compatible con](../../standard/net-standard.md#net-implementation-support) todas las versiones de .net Standard.</span><span class="sxs-lookup"><span data-stu-id="50a33-127">You can explore the dependencies of each NuGet package your application is using on [nuget.org](https://www.nuget.org/). If the package has .NET Standard dependencies, then it's going to work on .NET 5.0 because .NET [supports](../../standard/net-standard.md#net-implementation-support) all versions of .NET Standard.</span></span> <span data-ttu-id="50a33-128">En la imagen siguiente se muestran las dependencias del `Castle.Windsor` paquete:</span><span class="sxs-lookup"><span data-stu-id="50a33-128">The following image shows the dependencies for the `Castle.Windsor` package:</span></span>

![Captura de pantalla de las dependencias de NuGet para el paquete de. Windsor](./media/example-migration-core/nuget-dependencies.png)

<span data-ttu-id="50a33-130">Para comprobar la compatibilidad del paquete, puede usar la herramienta <https://fuget.org> que ofrece información más detallada sobre las versiones y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="50a33-130">To check the package compatibility, you can use the tool <https://fuget.org> that offers a more detailed information about versions and dependencies.</span></span>

<span data-ttu-id="50a33-131">Es posible que el proyecto haga referencia a versiones anteriores de paquetes que no son compatibles con .NET, pero puede que encuentre versiones más recientes que las admitan.</span><span class="sxs-lookup"><span data-stu-id="50a33-131">Maybe the project is referencing older package versions that don't support .NET, but you might find newer versions that do support it.</span></span> <span data-ttu-id="50a33-132">Por lo tanto, la actualización de paquetes a versiones más recientes suele ser una buena recomendación.</span><span class="sxs-lookup"><span data-stu-id="50a33-132">So, updating packages to newer versions is generally a good recommendation.</span></span> <span data-ttu-id="50a33-133">Sin embargo, debe tener en cuenta que la actualización de la versión del paquete puede introducir algunos cambios importantes que le obligarían a actualizar el código.</span><span class="sxs-lookup"><span data-stu-id="50a33-133">However, you should consider that updating the package version can introduce some breaking changes that would force you to update your code.</span></span>

<span data-ttu-id="50a33-134">¿Qué ocurre si no encuentra una versión compatible?</span><span class="sxs-lookup"><span data-stu-id="50a33-134">What happens if you don't find a compatible version?</span></span> <span data-ttu-id="50a33-135">¿Qué ocurre si no desea actualizar la versión de un paquete debido a estos cambios importantes?</span><span class="sxs-lookup"><span data-stu-id="50a33-135">What if you just don't want to update the version of a package because of these breaking changes?</span></span> <span data-ttu-id="50a33-136">No se preocupe porque es posible depender de .NET Framework paquetes desde una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-136">Don't worry because it's possible to depend on .NET Framework packages from a .NET application.</span></span> <span data-ttu-id="50a33-137">No olvide probarla exhaustivamente porque puede provocar errores en tiempo de ejecución si el paquete externo llama a una API que no está disponible en .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-137">Don't forget to test it extensively because it can cause run-time errors if the external package calls an API that isn't available on .NET.</span></span> <span data-ttu-id="50a33-138">Esto resulta útil cuando se usa un paquete antiguo que no se va a actualizar y se puede redestinar simplemente para que funcione en .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-138">This is great for when you're using an old package that isn't going to be updated and you can just retarget to work on the .NET.</span></span>

#### <a name="check-for-api-compatibility"></a><span data-ttu-id="50a33-139">Comprobar la compatibilidad de API</span><span class="sxs-lookup"><span data-stu-id="50a33-139">Check for API compatibility</span></span>

<span data-ttu-id="50a33-140">Dado que la superficie de API en .NET Framework y .NET es similar pero no idéntica, debe comprobar qué API están disponibles en .NET y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="50a33-140">Since the API surface in .NET Framework and .NET is similar but not identical, you must check which APIs are available on .NET and which aren't.</span></span> <span data-ttu-id="50a33-141">Puede usar la herramienta analizador de portabilidad de .NET para Surface API que no está presente en .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-141">You can use the .NET Portability Analyzer tool to surface APIs used that aren't present on .NET.</span></span> <span data-ttu-id="50a33-142">Examina el nivel binario de la aplicación, extrae todas las API a las que se llama y, después, muestra las API que no están disponibles en la plataforma de destino (.NET 5,0 en este caso).</span><span class="sxs-lookup"><span data-stu-id="50a33-142">It looks at the binary level of your app, extracts all the APIs that are called, and then lists which APIs aren't available on your target framework (.NET 5.0 in this case).</span></span>

<span data-ttu-id="50a33-143">Puede encontrar más información sobre esta herramienta en:</span><span class="sxs-lookup"><span data-stu-id="50a33-143">You can find more information about this tool at:</span></span>

<https://docs.microsoft.com/dotnet/standard/analyzers/portability-analyzer>

<span data-ttu-id="50a33-144">Un aspecto interesante de esta herramienta es que solo muestra las diferencias de su propio código y no el código de los paquetes externos, que no se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="50a33-144">An interesting aspect of this tool is that it only surfaces the differences from your own code and not code from external packages, which you can't change.</span></span> <span data-ttu-id="50a33-145">Recuerde que debe haber actualizado la mayoría de estos paquetes para que funcionen con .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-145">Remember you should have updated most of these packages to make them work with .NET.</span></span>

### <a name="migrate-with-try-convert-tool"></a><span data-ttu-id="50a33-146">Migrar con la herramienta probar conversión</span><span class="sxs-lookup"><span data-stu-id="50a33-146">Migrate with Try Convert tool</span></span>

<span data-ttu-id="50a33-147">La herramienta [probar conversión](https://github.com/dotnet/try-convert/releases) es una excelente manera de migrar un proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-147">The [Try Convert](https://github.com/dotnet/try-convert/releases) tool is a great way to migrate a project.</span></span> <span data-ttu-id="50a33-148">Es una herramienta global que intenta actualizar el archivo de proyecto desde el estilo anterior al nuevo estilo del SDK y redestina los proyectos aplicables a .NET 5.</span><span class="sxs-lookup"><span data-stu-id="50a33-148">It's a global tool that attempts to upgrade your project file from the old style to the new SDK style, and retargets applicable projects to .NET 5.</span></span> <span data-ttu-id="50a33-149">Una vez instalado, puede ejecutar los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="50a33-149">Once installed, you can run the following commands:</span></span>

```dotnetcli
try-convert -p "<path to your project file>"
```

<span data-ttu-id="50a33-150">O:</span><span class="sxs-lookup"><span data-stu-id="50a33-150">Or:</span></span>

```dotnetcli
try-convert -w "<path to your solution>"
```

> [!NOTE]
> <span data-ttu-id="50a33-151">La herramienta try-Convert se ejecuta automáticamente como parte de la [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant).</span><span class="sxs-lookup"><span data-stu-id="50a33-151">The try-convert tool is run automatically as part of the [.NET Upgrade Assistant tool](https://aka.ms/dotnet-upgrade-assistant).</span></span> <span data-ttu-id="50a33-152">Considere la posibilidad de ejecutar el Asistente para actualización completa y no solo intente convertir.</span><span class="sxs-lookup"><span data-stu-id="50a33-152">Consider running the full Upgrade Assistant and not just Try Convert.</span></span>

<span data-ttu-id="50a33-153">Después de que la herramienta intente la conversión, vuelva a cargar los archivos en Visual Studio para ejecutarlos y probarlos.</span><span class="sxs-lookup"><span data-stu-id="50a33-153">After the tool attempts the conversion, reload your files in Visual Studio to run and test.</span></span> <span data-ttu-id="50a33-154">Existe la posibilidad de que el intento de convertir no pueda realizar la conversión debido a los detalles del proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-154">There's a possibility that Try Convert won't be able to perform the conversion due to the specifics of your project.</span></span> <span data-ttu-id="50a33-155">En ese caso, puede hacer referencia a los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="50a33-155">In that case, you can refer the below steps.</span></span>

#### <a name="migrate-manually"></a><span data-ttu-id="50a33-156">Migración manual</span><span class="sxs-lookup"><span data-stu-id="50a33-156">Migrate manually</span></span>

1. <span data-ttu-id="50a33-157">Crear el nuevo proyecto de .NET</span><span class="sxs-lookup"><span data-stu-id="50a33-157">Create the new .NET project</span></span>

<span data-ttu-id="50a33-158">En la mayoría de los casos, querrá actualizar el proyecto existente al nuevo formato .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-158">In most cases, you'll want to update your existing project to the new .NET format.</span></span> <span data-ttu-id="50a33-159">Sin embargo, también puede crear un nuevo proyecto manteniendo el anterior.</span><span class="sxs-lookup"><span data-stu-id="50a33-159">However, you can also create a new project while maintaining the old one.</span></span> <span data-ttu-id="50a33-160">La principal desventaja de actualizar el proyecto anterior es que pierde la compatibilidad con el diseñador, que puede ser importante para usted y su equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="50a33-160">The main drawback from updating the old project is that you lose designer support, which may be important to you and your development team.</span></span> <span data-ttu-id="50a33-161">Si desea seguir usando el diseñador, debe crear un nuevo proyecto de .NET en paralelo con el antiguo y compartir los recursos.</span><span class="sxs-lookup"><span data-stu-id="50a33-161">If you want to keep using the designer, you must create a new .NET project in parallel with the old one and share assets.</span></span> <span data-ttu-id="50a33-162">Si necesita modificar los elementos de la interfaz de usuario en el diseñador, puede cambiar al proyecto anterior para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="50a33-162">If you need to modify UI elements in the designer, you can switch to the old project to do that.</span></span> <span data-ttu-id="50a33-163">Y como los activos están vinculados, también se actualizarán en el proyecto de .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-163">And since assets are linked, they'll be updated in the .NET project as well.</span></span>

<span data-ttu-id="50a33-164">El [proyecto de estilo SDK](../../core/project-sdk/msbuild-props.md) para .net es mucho más sencillo que el formato de proyecto de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50a33-164">The [SDK-style project](../../core/project-sdk/msbuild-props.md) for .NET is a lot simpler than .NET Framework's project format.</span></span> <span data-ttu-id="50a33-165">Además de las entradas mencionadas anteriormente `PackageReference` , no tendrá que hacer mucho más.</span><span class="sxs-lookup"><span data-stu-id="50a33-165">Apart from the previously mentioned `PackageReference` entries, you won't need to do much more.</span></span> <span data-ttu-id="50a33-166">El nuevo formato de proyecto [incluye archivos con determinadas extensiones de forma predeterminada](../../core/project-sdk/overview.md#default-includes-and-excludes), `.cs` como `.xaml` archivos y, sin necesidad de incluirlos explícitamente en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-166">The new project format [includes files with certain extensions by default](../../core/project-sdk/overview.md#default-includes-and-excludes), such as `.cs` and `.xaml` files, without the need to explicitly include them in the project file.</span></span>

#### <a name="assemblyinfo-considerations"></a><span data-ttu-id="50a33-167">Consideraciones de AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="50a33-167">AssemblyInfo considerations</span></span>

<span data-ttu-id="50a33-168">Los atributos se generan automáticamente en los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-168">Attributes are autogenerated on .NET projects.</span></span> <span data-ttu-id="50a33-169">Si el proyecto contiene un archivo *AssemblyInfo.CS* , las definiciones se duplicarán, lo que provocará conflictos de compilación.</span><span class="sxs-lookup"><span data-stu-id="50a33-169">If the project contains an *AssemblyInfo.cs* file, the definitions will be duplicated, which will cause compilation conflicts.</span></span> <span data-ttu-id="50a33-170">Puede eliminar el archivo *AssemblyInfo.CS* anterior o deshabilitar la generación de perfiles agregando la siguiente entrada al archivo de proyecto .net:</span><span class="sxs-lookup"><span data-stu-id="50a33-170">You can delete the older *AssemblyInfo.cs* file or disable autogeneration by adding the following entry to the .NET project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

#### <a name="resources"></a><span data-ttu-id="50a33-171">Recursos</span><span class="sxs-lookup"><span data-stu-id="50a33-171">Resources</span></span>

<span data-ttu-id="50a33-172">Los recursos incrustados se incluyen automáticamente, pero no los recursos, por lo que debe migrar los recursos al nuevo archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-172">Embedded resources are included automatically but resources aren't, so you need to migrate the resources to the new project file.</span></span>

#### <a name="package-references"></a><span data-ttu-id="50a33-173">Referencias de paquete</span><span class="sxs-lookup"><span data-stu-id="50a33-173">Package references</span></span>

<span data-ttu-id="50a33-174">Con la opción **migrar packages.config a PackageReference** , puede trasladar fácilmente las referencias de paquetes externos al nuevo formato, como se mencionó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="50a33-174">With the **Migrate packages.config to PackageReference** option, you can easily move your external package references to the new format as previously mentioned.</span></span>

#### <a name="update-package-references"></a><span data-ttu-id="50a33-175">Actualización de las referencias del paquete</span><span class="sxs-lookup"><span data-stu-id="50a33-175">Update package references</span></span>

<span data-ttu-id="50a33-176">Actualice las versiones de los paquetes que ha encontrado como compatibles, tal como se muestra en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="50a33-176">Update the versions of the packages you've found to be compatible, as shown in the previous section.</span></span>

### <a name="fix-the-code-and-build"></a><span data-ttu-id="50a33-177">Corregir el código y compilar</span><span class="sxs-lookup"><span data-stu-id="50a33-177">Fix the code and build</span></span>

#### <a name="microsoftwindowscompatibility"></a><span data-ttu-id="50a33-178">Microsoft. Windows. Compatibility</span><span class="sxs-lookup"><span data-stu-id="50a33-178">Microsoft.Windows.Compatibility</span></span>

<span data-ttu-id="50a33-179">Si su aplicación depende de las API que no están disponibles en .NET, como registro, ACL o WCF, tiene que incluir una referencia al `Microsoft.Windows.Compatibility` paquete para agregar estas API específicas de Windows.</span><span class="sxs-lookup"><span data-stu-id="50a33-179">If your application depends on APIs that aren't available on .NET, such as Registry, ACLs, or WCF, you have to include a reference to the `Microsoft.Windows.Compatibility` package to add these Windows-specific APIs.</span></span> <span data-ttu-id="50a33-180">Funcionan en .NET, pero no se incluyen porque no son multiplataforma.</span><span class="sxs-lookup"><span data-stu-id="50a33-180">They work on .NET but aren't included as they aren't cross-platform.</span></span>

<span data-ttu-id="50a33-181">Hay una herramienta denominada API Analyzer ( <https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer> ) que le ayuda a identificar las API que no son compatibles con el código.</span><span class="sxs-lookup"><span data-stu-id="50a33-181">There's a tool called API Analyzer (<https://docs.microsoft.com/dotnet/standard/analyzers/api-analyzer>) that helps you identify APIs that aren't compatible with your code.</span></span>

#### <a name="use-if-directives"></a><span data-ttu-id="50a33-182">Usar \# directivas if</span><span class="sxs-lookup"><span data-stu-id="50a33-182">Use \#if directives</span></span>

<span data-ttu-id="50a33-183">Si necesita diferentes rutas de ejecución al establecer como destino .NET Framework y .NET, debe utilizar constantes de compilación.</span><span class="sxs-lookup"><span data-stu-id="50a33-183">If you need different execution paths when targeting .NET Framework and .NET, you should use compilation constants.</span></span> <span data-ttu-id="50a33-184">Agregue algunas \# directivas if al código para mantener la misma base de código para ambos destinos.</span><span class="sxs-lookup"><span data-stu-id="50a33-184">Add some \#if directives to your code to keep the same code base for both targets.</span></span>

#### <a name="technologies-not-available-on-net"></a><span data-ttu-id="50a33-185">Tecnologías no disponibles en .NET</span><span class="sxs-lookup"><span data-stu-id="50a33-185">Technologies not available on .NET</span></span>

<span data-ttu-id="50a33-186">Algunas tecnologías no están disponibles en .NET, como:</span><span class="sxs-lookup"><span data-stu-id="50a33-186">Some technologies aren't available on .NET, such as:</span></span>

* <span data-ttu-id="50a33-187">Dominios de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="50a33-187">AppDomains</span></span>
* <span data-ttu-id="50a33-188">Comunicación remota</span><span class="sxs-lookup"><span data-stu-id="50a33-188">Remoting</span></span>
* <span data-ttu-id="50a33-189">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="50a33-189">Code Access Security</span></span>
* <span data-ttu-id="50a33-190">Servidor WCF</span><span class="sxs-lookup"><span data-stu-id="50a33-190">WCF Server</span></span>
* <span data-ttu-id="50a33-191">Flujo de trabajo de Windows</span><span class="sxs-lookup"><span data-stu-id="50a33-191">Windows Workflow</span></span>

<span data-ttu-id="50a33-192">Esta es la razón por la que necesita buscar una sustitución para estas tecnologías si las usa en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50a33-192">That's why you need to find a replacement for these technologies if you're using them in your application.</span></span> <span data-ttu-id="50a33-193">Para obtener más información, consulte el artículo [.NET Framework Technologies no está disponible en .net Core y .net 5 +](../../core/porting/net-framework-tech-unavailable.md) .</span><span class="sxs-lookup"><span data-stu-id="50a33-193">For more information, see the [.NET Framework technologies unavailable on .NET Core and .NET 5+](../../core/porting/net-framework-tech-unavailable.md) article.</span></span>

#### <a name="regenerate-autogenerated-clients"></a><span data-ttu-id="50a33-194">Regenerar clientes generados automáticamente</span><span class="sxs-lookup"><span data-stu-id="50a33-194">Regenerate autogenerated clients</span></span>

<span data-ttu-id="50a33-195">Si la aplicación usa código generado automáticamente, como un cliente de WCF, es posible que tenga que volver a generar este código para tener como destino .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-195">If your application uses autogenerated code, such as a WCF client, you may need to regenerate this code to target .NET.</span></span> <span data-ttu-id="50a33-196">A veces, puede encontrar algunas referencias que faltan, ya que no se incluyen como parte del conjunto de ensamblados .NET predeterminado.</span><span class="sxs-lookup"><span data-stu-id="50a33-196">Sometimes, you can find some missing references since they may not be included as part of the default .NET assemblies set.</span></span> <span data-ttu-id="50a33-197">Con una herramienta como <https://apisof.net/> , puede encontrar fácilmente el ensamblado en el que reside la referencia que falta y agregarlo desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="50a33-197">Using a tool like <https://apisof.net/>, you can easily locate the assembly the missing reference lives in and add it from NuGet.</span></span>

#### <a name="rolling-back-package-versions"></a><span data-ttu-id="50a33-198">Revertir versiones de paquetes</span><span class="sxs-lookup"><span data-stu-id="50a33-198">Rolling back package versions</span></span>

<span data-ttu-id="50a33-199">Como norma general, ya hemos indicado que se actualizan mejor todas las versiones de paquete único para que sean compatibles con .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-199">As a general rule, we've previously stated that you better update every single package version to be compatible with .NET.</span></span> <span data-ttu-id="50a33-200">Sin embargo, puede encontrar que el destino de una versión actualizada y compatible de un ensamblado no se pague.</span><span class="sxs-lookup"><span data-stu-id="50a33-200">However, you can find that targeting an updated and compatible version of an assembly just doesn't pay off.</span></span> <span data-ttu-id="50a33-201">Si el costo del cambio no es aceptable, puede considerar la posibilidad de revertir versiones de paquetes manteniendo las que usa en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="50a33-201">If the cost of change isn't acceptable, you can consider rolling back package versions keeping the ones you use on .NET Framework.</span></span> <span data-ttu-id="50a33-202">Aunque es posible que no tengan como destino .NET, deben funcionar bien a menos que llamen a algunas API no admitidas.</span><span class="sxs-lookup"><span data-stu-id="50a33-202">Although they may not be targeting .NET, they should work well unless they call some unsupported APIs.</span></span>

### <a name="run-and-test"></a><span data-ttu-id="50a33-203">Ejecución y prueba</span><span class="sxs-lookup"><span data-stu-id="50a33-203">Run and test</span></span>

<span data-ttu-id="50a33-204">Una vez que la aplicación se compila sin errores, puede iniciar el último paso de la migración probando cada funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="50a33-204">Once you have your application building with no errors, you can start the last step of the migration by testing every functionality.</span></span>

<span data-ttu-id="50a33-205">En este paso final, puede encontrar varios problemas diferentes en función de la complejidad de la aplicación y de las dependencias y las API que esté usando.</span><span class="sxs-lookup"><span data-stu-id="50a33-205">In this final step, you can find several different issues depending on the complexity of your application and the dependencies and APIs you're using.</span></span>

<span data-ttu-id="50a33-206">Por ejemplo, si usa archivos de configuración (*app.config*), puede encontrar algunos errores en tiempo de ejecución, como las secciones de configuración que no están presentes.</span><span class="sxs-lookup"><span data-stu-id="50a33-206">For example, if you use configuration files (*app.config*), you may find some errors at run time like Configuration Sections not present.</span></span> <span data-ttu-id="50a33-207">El uso del `Microsoft.Extensions.Configuration` paquete NuGet debe corregir este error.</span><span class="sxs-lookup"><span data-stu-id="50a33-207">Using the `Microsoft.Extensions.Configuration` NuGet package should fix that error.</span></span>

<span data-ttu-id="50a33-208">Otro motivo de los errores es el uso de `BeginInvoke` los `EndInvoke` métodos y porque no se admiten en .net.</span><span class="sxs-lookup"><span data-stu-id="50a33-208">Another reason for errors is the use of the `BeginInvoke` and `EndInvoke` methods because they aren't supported on .NET.</span></span> <span data-ttu-id="50a33-209">No se admiten en .NET porque tienen una dependencia en la comunicación remota, que no existe en .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-209">They aren't supported on .NET because they have a dependency on Remoting, which doesn't exist on .NET.</span></span> <span data-ttu-id="50a33-210">Para solucionar este problema, intente usar la `await` palabra clave (si está disponible) o el <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="50a33-210">To solve this issue, try to use the `await` keyword (when available) or the <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="50a33-211">Puede usar analizadores de compatibilidad para permitirle identificar API y patrones de código en el código que pueden causar problemas en tiempo de ejecución con .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-211">You can use compatibility analyzers to let you identify APIs and code patterns in your code that can potentially cause problems at run time with .NET.</span></span> <span data-ttu-id="50a33-212">Vaya a <https://github.com/dotnet/platform-compat> y use el analizador de API de .net en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-212">Go to <https://github.com/dotnet/platform-compat> and use the .NET API analyzer on your project.</span></span>

## <a name="migrating-a-windows-forms-application"></a><span data-ttu-id="50a33-213">Migración de una aplicación Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50a33-213">Migrating a Windows Forms application</span></span>

<span data-ttu-id="50a33-214">Para exhibir un proceso de migración completo de una aplicación Windows Forms, hemos elegido migrar la aplicación de ejemplo de eShop disponible en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="50a33-214">To showcase a complete migration process of a Windows Forms application, we've chosen to migrate the eShop sample application available at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopLegacyNTier/src/eShopWinForms>.</span></span> <span data-ttu-id="50a33-215">Puede encontrar el resultado completo de la migración en <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms> .</span><span class="sxs-lookup"><span data-stu-id="50a33-215">You can find the complete result of the migration at <https://github.com/dotnet-architecture/eShopModernizing/tree/master/eShopModernizedNTier/src/eShopWinForms>.</span></span>

<span data-ttu-id="50a33-216">Esta aplicación muestra un catálogo de productos y permite al usuario navegar, filtrar y buscar productos.</span><span class="sxs-lookup"><span data-stu-id="50a33-216">This application shows a product catalog and allows the user to navigate, filter, and search for products.</span></span> <span data-ttu-id="50a33-217">Desde el punto de vista de la arquitectura, la aplicación se basa en un servicio WCF externo que sirve de fachada a una base de datos back-end.</span><span class="sxs-lookup"><span data-stu-id="50a33-217">From an architecture point of view, the app relies on an external WCF service that serves as a façade to a back-end database.</span></span>

<span data-ttu-id="50a33-218">Puede ver la ventana principal de la aplicación en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="50a33-218">You can see the main application window in the following picture:</span></span>

![Ventana principal de la aplicación](./media/example-migration-core/main-application-window.png)

<span data-ttu-id="50a33-220">Si abre el archivo de proyecto *. csproj* , puede ver algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="50a33-220">If you open the *.csproj* project file, you can see something like this:</span></span>

![Captura de pantalla del contenido del archivo csproj](./media/example-migration-core/csproj-file.png)

<span data-ttu-id="50a33-222">Como se mencionó anteriormente, el proyecto .NET tiene un estilo más compacto y debe migrar la estructura del proyecto al nuevo estilo del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-222">As previously mentioned, .NET project has a more compact style and you need to migrate the project structure to the new .NET SDK style.</span></span>

<span data-ttu-id="50a33-223">En el explorador de soluciones, haga clic con el botón derecho en el proyecto Windows Forms y seleccione **descargar el proyecto**  >  **Editar**.</span><span class="sxs-lookup"><span data-stu-id="50a33-223">In the Solution Explorer, right click on the Windows Forms project and select **Unload Project** > **Edit**.</span></span>

<span data-ttu-id="50a33-224">Ahora puede actualizar el archivo. csproj.</span><span class="sxs-lookup"><span data-stu-id="50a33-224">Now you can update the .csproj file.</span></span> <span data-ttu-id="50a33-225">Eliminará todo el contenido y lo reemplazará por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="50a33-225">You'll delete the entire content and replace it with the following code:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWindowsForms>true</UseWindowsForms>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="50a33-226">Guarde y vuelva a cargar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-226">Save and reload the project.</span></span> <span data-ttu-id="50a33-227">Ahora ha terminado de actualizar el archivo de proyecto y el proyecto tiene como destino .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-227">You're now done updating the project file and the project is targeting the .NET.</span></span>

<span data-ttu-id="50a33-228">Si compila el proyecto en este momento, encontrará algunos errores relacionados con la referencia de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="50a33-228">If you compile the project at this point, you'll find some errors related to the WCF client reference.</span></span> <span data-ttu-id="50a33-229">Dado que este código se genera automáticamente, debe volver a generarlo para tener como destino .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-229">Since this code is autogenerated, you must regenerate it to target .NET.</span></span>

![Captura de pantalla de errores de compilación en Visual Studio](./media/example-migration-core/winforms-compilation-errors.png)

<span data-ttu-id="50a33-231">Elimine el archivo *Reference.CS* y genere un nuevo cliente de servicio.</span><span class="sxs-lookup"><span data-stu-id="50a33-231">Delete the *Reference.cs* file and generate a new Service Client.</span></span>

<span data-ttu-id="50a33-232">Haga clic con el botón derecho en **servicios conectados** y seleccione la opción **Agregar servicio conectado** .</span><span class="sxs-lookup"><span data-stu-id="50a33-232">Right-click on **Connected Services** and select the **Add Connected Service** option.</span></span>

![Captura de pantalla del menú Servicios conectados con la opción Agregar servicio conectado seleccionada](./media/example-migration-core/add-connected-service.png)

<span data-ttu-id="50a33-234">Se abre la ventana Servicios conectados.</span><span class="sxs-lookup"><span data-stu-id="50a33-234">The Connected Services window opens.</span></span> <span data-ttu-id="50a33-235">Seleccione la opción **servicio Web WCF de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="50a33-235">Select the **Microsoft WCF Web Service** option.</span></span>

![Captura de pantalla de la ventana de Servicios conectados](./media/example-migration-core/connected-services-window.png)

<span data-ttu-id="50a33-237">Si tiene el servicio WCF en la misma solución que en este ejemplo, puede seleccionar la opción **Discover** en lugar de especificar una dirección URL de servicio.</span><span class="sxs-lookup"><span data-stu-id="50a33-237">If you have the WCF Service in the same solution as we have in this example, you can select the **Discover** option instead of specifying a service URL.</span></span>

![Captura de pantalla de la ventana Configurar referencia de servicio Web WCF](./media/example-migration-core/configure-wcf-reference.png)

<span data-ttu-id="50a33-239">Una vez que se encuentra el servicio, la herramienta refleja el contrato de API implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="50a33-239">Once the service is located, the tool reflects the API contract implemented by the service.</span></span> <span data-ttu-id="50a33-240">Cambie el nombre del espacio de nombres para que sea `eShopServiceReference` como se muestra en la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="50a33-240">Change the name of the namespace to be `eShopServiceReference` as shown in the following image:</span></span>

![Captura de pantalla del contrato de API y el espacio de nombres cambiado](./media/example-migration-core/api-contract-namespace.png)

<span data-ttu-id="50a33-242">Seleccione el botón **Finalizar** .</span><span class="sxs-lookup"><span data-stu-id="50a33-242">Select the **Finish** button.</span></span> <span data-ttu-id="50a33-243">Después de un tiempo, verá el código generado.</span><span class="sxs-lookup"><span data-stu-id="50a33-243">After a while, you'll see the generated code.</span></span>

<span data-ttu-id="50a33-244">Debería ver tres archivos generados automáticamente:</span><span class="sxs-lookup"><span data-stu-id="50a33-244">You should see three autogenerated files:</span></span>

1. <span data-ttu-id="50a33-245">*Introducción*: un vínculo a GitHub para proporcionar información sobre WCF.</span><span class="sxs-lookup"><span data-stu-id="50a33-245">*Getting Started*: a link to GitHub to provide some information on WCF.</span></span>
2. <span data-ttu-id="50a33-246">*ConnectedService.jsen*: parámetros de configuración para conectarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="50a33-246">*ConnectedService.json*: configuration parameters to connect to the service.</span></span>
3. <span data-ttu-id="50a33-247">*Reference.CS*: el código de cliente de WCF real.</span><span class="sxs-lookup"><span data-stu-id="50a33-247">*Reference.cs*: the actual WCF client code.</span></span>

![Captura de pantalla de la ventana de Explorador de soluciones con los tres archivos autogenerados](./media/example-migration-core/autogenerated-files.png)

<span data-ttu-id="50a33-249">Si vuelve a compilar, verá muchos errores procedentes de archivos *. CS* dentro de la carpeta *auxiliar* .</span><span class="sxs-lookup"><span data-stu-id="50a33-249">If you compile again, you'll see many errors coming from *.cs* files inside the *Helper* folder.</span></span> <span data-ttu-id="50a33-250">Esta carpeta estaba presente en la versión .NET Framework pero no en el antiguo *. csproj*.</span><span class="sxs-lookup"><span data-stu-id="50a33-250">This folder was present in the .NET Framework version but not included in the old *.csproj*.</span></span> <span data-ttu-id="50a33-251">Pero con el nuevo proyecto de estilo SDK, todos los archivos de código presentes bajo la ubicación del archivo de proyecto se incluyen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="50a33-251">But with the new SDK-style project, every code file present underneath the project file location is included by default.</span></span> <span data-ttu-id="50a33-252">Es decir, el nuevo proyecto de .NET Core intenta compilar los archivos dentro de la carpeta *auxiliar* .</span><span class="sxs-lookup"><span data-stu-id="50a33-252">That is, the new .NET Core project tries to compile the files inside the *Helper* folder.</span></span> <span data-ttu-id="50a33-253">Dado que esa carpeta no es necesaria, puede eliminarla de forma segura.</span><span class="sxs-lookup"><span data-stu-id="50a33-253">Since that folder isn't needed, you can safely delete it.</span></span>

<span data-ttu-id="50a33-254">Si compila el proyecto de nuevo y lo ejecuta, no verá las imágenes del producto.</span><span class="sxs-lookup"><span data-stu-id="50a33-254">If you compile the project again and execute it, you won't see the product images.</span></span> <span data-ttu-id="50a33-255">El problema es que ahora la ruta de acceso a los archivos ha cambiado ligeramente.</span><span class="sxs-lookup"><span data-stu-id="50a33-255">The problem is that now the path to the files has slightly changed.</span></span> <span data-ttu-id="50a33-256">Para corregir este problema, debe agregar otro nivel de profundidad en la ruta de acceso y actualizar en el archivo `CatalogView.cs` la línea:</span><span class="sxs-lookup"><span data-stu-id="50a33-256">To fix this issue, you need to add another level of depth in the path, updating in the file `CatalogView.cs` the line:</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="50a33-257">en</span><span class="sxs-lookup"><span data-stu-id="50a33-257">to</span></span>

```csharp
string image_name = Environment.CurrentDirectory + "\\..\\..\\..\\Assets\\Images\\Catalog\\" + catalogItems.Picturefilename;
```

<span data-ttu-id="50a33-258">Después de este cambio, puede comprobar que la aplicación se inicia y se ejecuta según lo previsto en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="50a33-258">After this change, you can check that the application launches and runs as expected on .NET Core.</span></span>

## <a name="migrating-a-wpf-application"></a><span data-ttu-id="50a33-259">Migración de una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="50a33-259">Migrating a WPF application</span></span>

<span data-ttu-id="50a33-260">Usaremos la `Shop.ClassicWPF` aplicación de ejemplo para realizar la migración.</span><span class="sxs-lookup"><span data-stu-id="50a33-260">We'll use the `Shop.ClassicWPF` sample application to perform the migration.</span></span> <span data-ttu-id="50a33-261">En la imagen siguiente se muestra una captura de pantalla de la aplicación antes de la migración:</span><span class="sxs-lookup"><span data-stu-id="50a33-261">The following image shows a screenshot of the app before migration:</span></span>

![Aplicación de ejemplo antes de la migración](./media/example-migration-core/app-before-migration.png)

<span data-ttu-id="50a33-263">Esta aplicación utiliza una base de datos de SQL Server Express local para almacenar la información del catálogo de productos.</span><span class="sxs-lookup"><span data-stu-id="50a33-263">This application uses a local SQL Server Express database to hold the product catalog information.</span></span> <span data-ttu-id="50a33-264">Se tiene acceso a esta base de datos directamente desde la aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="50a33-264">This database is accessed directly from the WPF application.</span></span>

<span data-ttu-id="50a33-265">En primer lugar, debe actualizar el archivo *. csproj* al nuevo estilo de SDK que usan las aplicaciones de .net Core.</span><span class="sxs-lookup"><span data-stu-id="50a33-265">First, you must update the *.csproj* file to the new SDK style used by .NET Core applications.</span></span> <span data-ttu-id="50a33-266">Siga los mismos pasos descritos en la Windows Forms migración: descargará el proyecto, abrirá el archivo *. csproj* , actualizará su contenido y volverá a cargar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="50a33-266">You'll follow the same steps described in the Windows Forms migration: you'll unload the project, open the *.csproj* file, update its contents, and reload the project.</span></span>

<span data-ttu-id="50a33-267">En este caso, elimine todo el contenido del archivo *. csproj* y reemplácelo por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="50a33-267">In this case, delete all the content of the *.csproj* file and replace it with the following code:</span></span>

```xml
 <Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWpf>true</UseWpf>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="50a33-268">Si vuelve a cargar el proyecto y lo compila, obtendrá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="50a33-268">If you reload the project and compile it, you'll get the following error:</span></span>

![Captura de pantalla de errores de compilación en Visual Studio](./media/example-migration-core/wpf-compilation-error.png)

<span data-ttu-id="50a33-270">Como ha eliminado todo el contenido de *. csproj* , ha perdido una especificación de referencia de proyecto presente en el proyecto anterior.</span><span class="sxs-lookup"><span data-stu-id="50a33-270">Since you've deleted all the *.csproj* contents, you've lost a project reference specification present in the old project.</span></span> <span data-ttu-id="50a33-271">Solo tiene que agregar esta línea al archivo *. csproj* para incluir la referencia de proyecto de nuevo:</span><span class="sxs-lookup"><span data-stu-id="50a33-271">You just need to add this line to the *.csproj* file to include the project reference back:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\\eShop.SqlProvider\\eShop.SqlProvider.csproj" />
<ItemGroup>
```

<span data-ttu-id="50a33-272">También puede dejar que Visual Studio le ayude haciendo clic con el botón derecho en el nodo **dependencias** y seleccionando **Agregar referencia de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="50a33-272">You can also let Visual Studio help you by right-clicking on the **Dependencies** node and selecting **Add Project Reference**.</span></span> <span data-ttu-id="50a33-273">Seleccione el proyecto de la solución y haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="50a33-273">Select the project from the solution and click **OK**:</span></span>

![Captura de pantalla del cuadro de diálogo Administrador de referencias con el proyecto eShop. SqlProvider seleccionado](./media/example-migration-core/reference-manager.png)

<span data-ttu-id="50a33-275">Una vez que se agrega la referencia de proyecto que falta, la aplicación se compila y se ejecuta según lo previsto en .NET.</span><span class="sxs-lookup"><span data-stu-id="50a33-275">Once you add the missing project reference, the application compiles and runs as expected on .NET.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="50a33-276">[Anterior](windows-migration.md)
>[Siguiente](deploy-modern-applications.md)</span><span class="sxs-lookup"><span data-stu-id="50a33-276">[Previous](windows-migration.md)
[Next](deploy-modern-applications.md)</span></span>

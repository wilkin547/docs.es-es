---
title: Ngen.exe (Generador de imágenes nativas)
description: Revise Ngen.exe, el Generador de imágenes nativas. Mejore el rendimiento de las aplicaciones administradas creando imágenes nativas e instalándolas en la caché local de imágenes nativas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
ms.openlocfilehash: a553be6877af5875692e5c0745b6b9ee766e143e
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259270"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="b641c-104">Ngen.exe (Generador de imágenes nativas)</span><span class="sxs-lookup"><span data-stu-id="b641c-104">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="b641c-105">El Generador de imágenes nativas (Ngen.exe) es una herramienta que mejora el rendimiento de las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="b641c-105">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="b641c-106">Ngen.exe crea imágenes nativas, que son archivos que contienen código máquina compilado específicamente para un procesador, e instala estas imágenes en la memoria caché de imágenes nativas del equipo local.</span><span class="sxs-lookup"><span data-stu-id="b641c-106">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="b641c-107">El runtime puede usar imágenes nativas de la memoria caché en lugar de usar el compilador Just-In-Time (JIT) para compilar el ensamblado original.</span><span class="sxs-lookup"><span data-stu-id="b641c-107">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-108">Ngen.exe compila las imágenes nativas de los ensamblados que tienen como destino solo .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b641c-108">Ngen.exe compiles native images for assemblies that target the .NET Framework only.</span></span> <span data-ttu-id="b641c-109">El generador de imágenes nativas equivalente para .NET Core es [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span><span class="sxs-lookup"><span data-stu-id="b641c-109">The equivalent native image generator for .NET Core is [CrossGen](https://github.com/dotnet/runtime/blob/master/docs/workflow/building/coreclr/crossgen.md).</span></span>

<span data-ttu-id="b641c-110">Cambios en Ngen.exe en .NET Framework 4:</span><span class="sxs-lookup"><span data-stu-id="b641c-110">Changes to Ngen.exe in the .NET Framework 4:</span></span>

- <span data-ttu-id="b641c-111">Ahora, Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="b641c-111">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="b641c-112">Las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="b641c-112">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="b641c-113">Cambios en Ngen.exe en la versión 2.0 de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b641c-113">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="b641c-114">Al instalar un ensamblado, también se instalan sus dependencias, lo que simplifica la sintaxis de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-114">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="b641c-115">Ahora, las imágenes nativas se pueden compartir en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-115">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="b641c-116">Una nueva acción, `update`, vuelve a crear las imágenes invalidadas.</span><span class="sxs-lookup"><span data-stu-id="b641c-116">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="b641c-117">Se pueden aplazar las acciones para que las ejecute un servicio que use el tiempo de inactividad del equipo para generar e instalar las imágenes.</span><span class="sxs-lookup"><span data-stu-id="b641c-117">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="b641c-118">Se han eliminado algunas de las causas que provocan la invalidación de imágenes.</span><span class="sxs-lookup"><span data-stu-id="b641c-118">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="b641c-119">En Windows 8, consulte [Tarea de imagen nativa](#native-image-task).</span><span class="sxs-lookup"><span data-stu-id="b641c-119">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="b641c-120">Para información adicional sobre el uso de Ngen.exe y el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-120">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-121">Puede encontrar información sobre la sintaxis de Ngen.exe para las versiones 1.0 y 1.1 de .NET Framework en [Sintaxis heredada del generador de imágenes nativas (Ngen.exe)](/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b641c-121">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="b641c-122">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b641c-122">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b641c-123">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="b641c-123">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>

<span data-ttu-id="b641c-124">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b641c-124">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="b641c-125">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b641c-125">Syntax</span></span>

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="b641c-126">Acciones</span><span class="sxs-lookup"><span data-stu-id="b641c-126">Actions</span></span>

<span data-ttu-id="b641c-127">En la tabla siguiente se muestra la sintaxis de cada acción (`action`).</span><span class="sxs-lookup"><span data-stu-id="b641c-127">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="b641c-128">Para ver descripciones de los distintos elementos de una `action`, consulte las tablas [Argumentos](#ArgumentTable), [Niveles de prioridad](#PriorityTable), [Escenarios](#ScenarioTable) y [Configuración](#ConfigTable).</span><span class="sxs-lookup"><span data-stu-id="b641c-128">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="b641c-129">En la tabla [Opciones](#OptionTable) se describe el parámetro `options` y los modificadores de ayuda.</span><span class="sxs-lookup"><span data-stu-id="b641c-129">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="b641c-130">Acción</span><span class="sxs-lookup"><span data-stu-id="b641c-130">Action</span></span>|<span data-ttu-id="b641c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-131">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="b641c-132">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="b641c-132">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="b641c-133">Genera imágenes nativas para un ensamblado y sus dependencias e instala las imágenes en la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-133">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="b641c-134">Si se especifica `/queue`, la acción se pone en la cola del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-134">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="b641c-135">La prioridad predeterminada es 3.</span><span class="sxs-lookup"><span data-stu-id="b641c-135">The default priority is 3.</span></span> <span data-ttu-id="b641c-136">Consulte la tabla [Niveles de prioridad](#PriorityTable).</span><span class="sxs-lookup"><span data-stu-id="b641c-136">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="b641c-137">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="b641c-137">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="b641c-138">Elimina las imágenes nativas de un ensamblado y sus dependencias de la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-138">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="b641c-139">Para desinstalar una imagen y sus dependencias, use los mismos argumentos de la línea de comandos que usó para instalar la imagen.</span><span class="sxs-lookup"><span data-stu-id="b641c-139">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="b641c-140">**Nota:**  A partir de .NET Framework 4:, ya no se admite la acción `uninstall` \*.</span><span class="sxs-lookup"><span data-stu-id="b641c-140">**Note:**  Starting with the .NET Framework 4, the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="b641c-141">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="b641c-141">`update` [`/queue`]</span></span>|<span data-ttu-id="b641c-142">Actualiza las imágenes nativas que han dejado de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="b641c-142">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="b641c-143">Si se especifica `/queue`, las actualizaciones se ponen en la cola del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-143">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="b641c-144">Las actualizaciones siempre se programan con una prioridad de 3, por lo que se ejecutan cuando el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-144">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="b641c-145">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="b641c-145">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="b641c-146">Muestra el estado de las imágenes nativas para un ensamblado y sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="b641c-146">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="b641c-147">Si no se proporciona ningún argumento, se muestra todo el contenido de la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-147">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="b641c-148">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="b641c-148">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="b641c-149">o bien</span><span class="sxs-lookup"><span data-stu-id="b641c-149">-or-</span></span><br /><br /> <span data-ttu-id="b641c-150">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="b641c-150">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="b641c-151">Ejecuta los trabajos de compilación en cola.</span><span class="sxs-lookup"><span data-stu-id="b641c-151">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="b641c-152">Si se especifica una prioridad, se ejecutan los trabajos de compilación con una prioridad mayor o igual a la especificada.</span><span class="sxs-lookup"><span data-stu-id="b641c-152">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="b641c-153">Si no se especifica ninguna prioridad, se ejecutan todos los trabajos de compilación en cola.</span><span class="sxs-lookup"><span data-stu-id="b641c-153">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="b641c-154">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="b641c-154">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="b641c-155">Pausa el servicio de imágenes nativas, permite la reanudación del servicio en pausa o consulta el estado del servicio.</span><span class="sxs-lookup"><span data-stu-id="b641c-155">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="b641c-156">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b641c-156">Arguments</span></span>

|<span data-ttu-id="b641c-157">Argumento</span><span class="sxs-lookup"><span data-stu-id="b641c-157">Argument</span></span>|<span data-ttu-id="b641c-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-158">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="b641c-159">El nombre para mostrar completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-159">The full display name of the assembly.</span></span> <span data-ttu-id="b641c-160">Por ejemplo: `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span><span class="sxs-lookup"><span data-stu-id="b641c-160">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="b641c-161">**Nota:**  Puede proporcionar un nombre de ensamblado parcial, como `myAssembly`, para las acciones `display` y `uninstall`.</span><span class="sxs-lookup"><span data-stu-id="b641c-161">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="b641c-162">Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-162">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="b641c-163">La ruta de acceso explícita del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-163">The explicit path of the assembly.</span></span> <span data-ttu-id="b641c-164">Se puede especificar una ruta de acceso completa o relativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-164">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="b641c-165">Si se especifica un nombre de archivo sin una ruta de acceso, el ensamblado deberá estar ubicado en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b641c-165">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="b641c-166">Solo se puede especificar un ensamblado por cada línea de comandos de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-166">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="b641c-167">Niveles de prioridad</span><span class="sxs-lookup"><span data-stu-id="b641c-167">Priority Levels</span></span>

|<span data-ttu-id="b641c-168">Prioridad</span><span class="sxs-lookup"><span data-stu-id="b641c-168">Priority</span></span>|<span data-ttu-id="b641c-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-169">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="b641c-170">Las imágenes nativas se generan e instalan de forma inmediata, sin esperar al tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="b641c-170">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="b641c-171">Las imágenes nativas se generan e instalan sin esperar al tiempo de inactividad, pero después de que se hayan completado todas las acciones de prioridad 1 (y sus dependencias).</span><span class="sxs-lookup"><span data-stu-id="b641c-171">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="b641c-172">Las imágenes nativas se instalan cuando el servicio de imágenes nativas detecta que el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-172">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="b641c-173">Consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-173">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="b641c-174">Escenarios</span><span class="sxs-lookup"><span data-stu-id="b641c-174">Scenarios</span></span>

|<span data-ttu-id="b641c-175">Escenario</span><span class="sxs-lookup"><span data-stu-id="b641c-175">Scenario</span></span>|<span data-ttu-id="b641c-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-176">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="b641c-177">Genera imágenes nativas que pueden usarse con un depurador.</span><span class="sxs-lookup"><span data-stu-id="b641c-177">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="b641c-178">Genera imágenes nativas que pueden usarse con un generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b641c-178">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="b641c-179">Genera el número mínimo de imágenes nativas requerido por las opciones de escenario especificadas.</span><span class="sxs-lookup"><span data-stu-id="b641c-179">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="b641c-180">Configuración</span><span class="sxs-lookup"><span data-stu-id="b641c-180">Config</span></span>

|<span data-ttu-id="b641c-181">Configuración</span><span class="sxs-lookup"><span data-stu-id="b641c-181">Configuration</span></span>|<span data-ttu-id="b641c-182">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-182">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="b641c-183">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="b641c-183">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="b641c-184">Usa la configuración del ensamblado ejecutable especificado.</span><span class="sxs-lookup"><span data-stu-id="b641c-184">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="b641c-185">Ngen.exe tiene que tomar las mismas decisiones que el cargador al enlazarse a las dependencias.</span><span class="sxs-lookup"><span data-stu-id="b641c-185">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="b641c-186">Cuando se carga un componente compartido en tiempo de ejecución usando el método <xref:System.Reflection.Assembly.Load%2A>, el archivo de configuración de la aplicación determina las dependencias que se cargan para el componente compartido como, por ejemplo, la versión que se carga de una dependencia.</span><span class="sxs-lookup"><span data-stu-id="b641c-186">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="b641c-187">El modificador `/ExeConfig` proporciona a Ngen.exe orientación sobre las dependencias que se cargarán en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b641c-187">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="b641c-188">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="b641c-188">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="b641c-189">Al buscar dependencias, usa el directorio especificado como base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-189">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="b641c-190">Opciones</span><span class="sxs-lookup"><span data-stu-id="b641c-190">Options</span></span>

|<span data-ttu-id="b641c-191">Opción</span><span class="sxs-lookup"><span data-stu-id="b641c-191">Option</span></span>|<span data-ttu-id="b641c-192">Descripción</span><span class="sxs-lookup"><span data-stu-id="b641c-192">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="b641c-193">Suprime la presentación de la pancarta de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b641c-193">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="b641c-194">Suprime la presentación de mensajes de operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="b641c-194">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="b641c-195">Muestra información detallada para la depuración.</span><span class="sxs-lookup"><span data-stu-id="b641c-195">Display detailed information for debugging.</span></span> <span data-ttu-id="b641c-196">**Nota:**  Debido a las limitaciones de los sistemas operativos, esta opción no muestra tanta información adicional en Windows 98 y Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="b641c-196">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="b641c-197">`/help`, `/?`</span><span class="sxs-lookup"><span data-stu-id="b641c-197">`/help`, `/?`</span></span>|<span data-ttu-id="b641c-198">Muestra las opciones y la sintaxis de los comandos de la versión actual.</span><span class="sxs-lookup"><span data-stu-id="b641c-198">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b641c-199">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b641c-199">Remarks</span></span>

<span data-ttu-id="b641c-200">Para ejecutar Ngen.exe, es necesario disponer de privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b641c-200">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="b641c-201">No ejecute Ngen.exe en ensamblados que no son de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="b641c-201">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="b641c-202">A partir de .NET Framework 4, Ngen.exe compila los ensamblados con plena confianza y ya no se evalúa la directiva de seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="b641c-202">Starting with the .NET Framework 4, Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="b641c-203">A partir de .NET Framework 4, las imágenes nativas que se generan con Ngen.exe ya no se pueden cargar en las aplicaciones que se están ejecutando con confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="b641c-203">Starting with the .NET Framework 4, the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="b641c-204">En su lugar, se invoca el compilador Just-In-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="b641c-204">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="b641c-205">Ngen.exe genera imágenes nativas para el ensamblado que el argumento `assemblyname` especifica para la acción `install` y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="b641c-205">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="b641c-206">Las dependencias se determinan a partir de las referencias del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-206">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="b641c-207">El único escenario en el que es necesario instalar una dependencia por separado es aquel donde la aplicación carga la dependencia usando la reflexión, por ejemplo, llamando al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b641c-207">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b641c-208">No use el método <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> con imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-208">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="b641c-209">Una imagen cargada con este método no la podrán usar otros ensamblados en el contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b641c-209">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="b641c-210">Ngen.exe mantiene un recuento de las dependencias.</span><span class="sxs-lookup"><span data-stu-id="b641c-210">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="b641c-211">Por ejemplo, suponga que `MyAssembly.exe` y `YourAssembly.exe` están instalados en la memoria caché de imágenes nativas y que ambos tienen referencias a `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="b641c-211">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="b641c-212">Si se desinstala `MyAssembly.exe`, no se desinstala `OurDependency.dll`.</span><span class="sxs-lookup"><span data-stu-id="b641c-212">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="b641c-213">Solo se quita cuando también se desinstala `YourAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="b641c-213">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="b641c-214">Si va a generar una imagen nativa para un ensamblado en la caché global de ensamblados, especifique su nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="b641c-214">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="b641c-215">Vea <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b641c-215">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b641c-216">Las imágenes nativas generadas por Ngen.exe se pueden compartir en los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-216">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="b641c-217">Esto significa que Ngen.exe puede usarse en escenarios de aplicación que requieren el uso compartido de los ensamblados entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-217">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="b641c-218">Para especificar una neutralidad de dominios:</span><span class="sxs-lookup"><span data-stu-id="b641c-218">To specify domain neutrality:</span></span>

- <span data-ttu-id="b641c-219">Aplique el atributo <xref:System.LoaderOptimizationAttribute> a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-219">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="b641c-220">Establezca la propiedad <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> al crear la información de instalación de un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-220">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="b641c-221">Use siempre código con dominio neutro al cargar el mismo ensamblado en varios dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-221">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="b641c-222">Si una imagen nativa se carga en un dominio de aplicación no compartido después de haberse cargado en un dominio compartido, no se podrá usar.</span><span class="sxs-lookup"><span data-stu-id="b641c-222">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-223">No se puede descargar código con dominio neutro y el rendimiento puede resultar algo más lento, especialmente al obtener acceso a miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="b641c-223">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="b641c-224">En esta sección Comentarios:</span><span class="sxs-lookup"><span data-stu-id="b641c-224">In this Remarks section:</span></span>

- [<span data-ttu-id="b641c-225">Generación de imágenes para distintos escenarios</span><span class="sxs-lookup"><span data-stu-id="b641c-225">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="b641c-226">Determinación de cuándo se deben usar imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-226">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="b641c-227">Uso de memoria mejorado</span><span class="sxs-lookup"><span data-stu-id="b641c-227">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="b641c-228">Inicio de aplicación más rápido</span><span class="sxs-lookup"><span data-stu-id="b641c-228">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="b641c-229">Resumen de las consideraciones de uso</span><span class="sxs-lookup"><span data-stu-id="b641c-229">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="b641c-230">Importancia de las direcciones base de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="b641c-230">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="b641c-231">Enlace fuerte</span><span class="sxs-lookup"><span data-stu-id="b641c-231">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="b641c-232">Especificación de una sugerencia de enlace para una dependencia</span><span class="sxs-lookup"><span data-stu-id="b641c-232">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="b641c-233">Especificación de una sugerencia de enlace predeterminado para un ensamblado</span><span class="sxs-lookup"><span data-stu-id="b641c-233">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="b641c-234">Procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="b641c-234">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="b641c-235">Imágenes nativas y compilación JIT</span><span class="sxs-lookup"><span data-stu-id="b641c-235">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="b641c-236">Imágenes no válidas</span><span class="sxs-lookup"><span data-stu-id="b641c-236">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="b641c-237">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b641c-237">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="b641c-238">Visor de registro de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="b641c-238">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="b641c-239">Asistente para la depuración administrada JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="b641c-239">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="b641c-240">Exclusión de la generación de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-240">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="b641c-241">Generación de imágenes para distintos escenarios</span><span class="sxs-lookup"><span data-stu-id="b641c-241">Generating images for     different scenarios</span></span>

<span data-ttu-id="b641c-242">Una vez generada la imagen nativa de un ensamblado, el runtime intenta localizar y usar automáticamente la imagen nativa cada vez que se ejecuta el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-242">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="b641c-243">Se pueden generar varias imágenes, en función de los escenarios de uso.</span><span class="sxs-lookup"><span data-stu-id="b641c-243">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="b641c-244">Por ejemplo, si ejecuta un ensamblado en un escenario de depuración o de generación de perfiles, el runtime buscará una imagen nativa generada con las opciones `/Debug` o `/Profile`.</span><span class="sxs-lookup"><span data-stu-id="b641c-244">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="b641c-245">Si no encuentra una imagen nativa coincidente, el runtime usa la compilación JIT estándar.</span><span class="sxs-lookup"><span data-stu-id="b641c-245">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="b641c-246">La única forma de depurar imágenes nativas es mediante la creación de una imagen nativa con la opción `/Debug`.</span><span class="sxs-lookup"><span data-stu-id="b641c-246">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="b641c-247">La acción `uninstall` también reconoce los escenarios, por lo que se pueden desinstalar todos los escenarios o solo los escenarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b641c-247">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="b641c-248">Determinación de cuándo se deben usar imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-248">Determining when to Use native images</span></span>

<span data-ttu-id="b641c-249">Las imágenes nativas pueden ofrecer mejoras de rendimiento en dos áreas: uso de memoria mejorado y tiempo de inicio reducido.</span><span class="sxs-lookup"><span data-stu-id="b641c-249">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-250">El rendimiento de las imágenes nativas depende de una serie de factores que dificultan el análisis, como los patrones de acceso a código y a datos, el número de llamadas realizadas a través de los límites de los módulos y el número de dependencias que ya se han cargado en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b641c-250">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="b641c-251">La única forma de determinar si las imágenes nativas benefician a la aplicación es mediante la realización de mediciones del rendimiento meticulosas en los escenarios de implementación clave.</span><span class="sxs-lookup"><span data-stu-id="b641c-251">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="b641c-252">Uso de memoria mejorado</span><span class="sxs-lookup"><span data-stu-id="b641c-252">Improved memory use</span></span>

<span data-ttu-id="b641c-253">Las imágenes nativas pueden mejorar significativamente el uso de memoria cuando el código se comparte entre los procesos.</span><span class="sxs-lookup"><span data-stu-id="b641c-253">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="b641c-254">Las imágenes nativas son archivos PE de Windows, de modo que una única copia de un archivo .dll pueden compartirla varios procesos; en cambio, el código nativo generado por el compilador JIT se almacena en la memoria privada y no se puede compartir.</span><span class="sxs-lookup"><span data-stu-id="b641c-254">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="b641c-255">Las aplicaciones que se ejecutan en Terminal Services también pueden beneficiarse de las páginas de código compartido.</span><span class="sxs-lookup"><span data-stu-id="b641c-255">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="b641c-256">Además, al no cargar el compilador JIT, se reserva una cantidad de memoria fija para cada instancia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-256">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="b641c-257">Inicio de aplicación más rápido</span><span class="sxs-lookup"><span data-stu-id="b641c-257">Faster application startup</span></span>

<span data-ttu-id="b641c-258">Precompilar los ensamblados con Ngen.exe puede reducir el tiempo de inicio de algunas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b641c-258">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="b641c-259">En general, pueden obtenerse mejoras cuando las aplicaciones comparten ensamblados de componentes porque, una vez iniciada la primera aplicación, los componentes compartidos ya estarán cargados para las siguientes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b641c-259">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="b641c-260">Un inicio en frío, en el que todos los ensamblados de una aplicación deben cargarse desde el disco duro, no se beneficia tanto de las imágenes nativas porque predomina el tiempo de acceso al disco duro.</span><span class="sxs-lookup"><span data-stu-id="b641c-260">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="b641c-261">El enlace fuerte puede afectar al tiempo de inicio, ya que todas las imágenes con enlaces fuertes al ensamblado de aplicación principal deben cargarse al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b641c-261">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-262">Antes de .NET Framework 3.5 Service Pack 1, debía poner componentes con nombre seguro en la caché global de ensamblados porque el cargador efectúa una validación adicional de los ensamblados con nombre seguro que no se encuentran en la caché global de ensamblados, lo que anula cualquier mejora del tiempo de inicio obtenida gracias al uso de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-262">Before the .NET Framework 3.5 Service Pack 1, you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="b641c-263">Las optimizaciones introducidas en .NET Framework 3.5 SP1 quitaron la validación adicional.</span><span class="sxs-lookup"><span data-stu-id="b641c-263">Optimizations that were introduced in the .NET Framework 3.5 SP1 removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="b641c-264">Resumen de las consideraciones de uso</span><span class="sxs-lookup"><span data-stu-id="b641c-264">Summary of usage considerations</span></span>

<span data-ttu-id="b641c-265">Las siguientes consideraciones generales y consideraciones sobre la aplicación pueden ayudarle a decidir si merece la pena asumir el esfuerzo de evaluar las imágenes nativas de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="b641c-265">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="b641c-266">Las imágenes nativas se cargan más rápido que MSIL, ya que eliminan la necesidad de ejecutar muchas actividades en el inicio, como la compilación JIT y la comprobación de la seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="b641c-266">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="b641c-267">Las imágenes nativas requieren un espacio de trabajo inicial más pequeño, ya que el compilador JIT no es necesario.</span><span class="sxs-lookup"><span data-stu-id="b641c-267">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="b641c-268">Las imágenes nativas permiten un uso compartido del código entre los procesos.</span><span class="sxs-lookup"><span data-stu-id="b641c-268">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="b641c-269">Las imágenes nativas requieren más espacio en el disco duro que los ensamblados MSIL y pueden tardar bastante tiempo en generarse.</span><span class="sxs-lookup"><span data-stu-id="b641c-269">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="b641c-270">Las imágenes nativas necesitan mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="b641c-270">Native images must be maintained.</span></span>

  - <span data-ttu-id="b641c-271">Cuando se realiza el mantenimiento del ensamblado original o de una de sus dependencias, es necesario volver a generar las imágenes.</span><span class="sxs-lookup"><span data-stu-id="b641c-271">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="b641c-272">Un solo ensamblado puede necesitar varias imágenes nativas para su uso en aplicaciones o escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="b641c-272">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="b641c-273">Por ejemplo, la información de configuración de dos aplicaciones podría producir distintas decisiones de enlace para el mismo ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="b641c-273">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="b641c-274">La generación de imágenes nativas solo la puede llevar a cabo un administrador; es decir, deberá realizarse desde una cuenta de Windows del grupo de administradores.</span><span class="sxs-lookup"><span data-stu-id="b641c-274">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="b641c-275">Además de estas consideraciones generales, hay que tener en cuenta la naturaleza de la aplicación a la hora de determinar si las imágenes nativas pueden suponer una mejora en el rendimiento:</span><span class="sxs-lookup"><span data-stu-id="b641c-275">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="b641c-276">Si la aplicación se ejecuta en un entorno que usa muchos componentes compartidos, las imágenes nativas permiten un uso compartido de los componentes por parte de varios procesos.</span><span class="sxs-lookup"><span data-stu-id="b641c-276">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="b641c-277">Si la aplicación usa varios dominios de aplicación, las imágenes nativas permiten un uso compartido de las páginas de códigos entre los distintos dominios.</span><span class="sxs-lookup"><span data-stu-id="b641c-277">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b641c-278">En las versiones 1.0 y 1.1 de .NET Framework, los dominios de aplicación no pueden compartir las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-278">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="b641c-279">Este no es el caso en la versión 2.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b641c-279">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="b641c-280">Si la aplicación va a ejecutarse en Terminal Server, las imágenes nativas permiten un uso compartido de las páginas de código.</span><span class="sxs-lookup"><span data-stu-id="b641c-280">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="b641c-281">En general, las aplicaciones de gran tamaño se benefician de la compilación de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-281">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="b641c-282">En cambio, las aplicaciones pequeñas no suelen beneficiarse.</span><span class="sxs-lookup"><span data-stu-id="b641c-282">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="b641c-283">En las aplicaciones de ejecución prolongada, la compilación JIT en tiempo de ejecución ofrece un rendimiento ligeramente superior al de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-283">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="b641c-284">(El enlace fuerte puede mitigar hasta cierto punto esta diferencia de rendimiento).</span><span class="sxs-lookup"><span data-stu-id="b641c-284">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="b641c-285">Importancia de las direcciones base de los ensamblados</span><span class="sxs-lookup"><span data-stu-id="b641c-285">Importance of assembly base addresses</span></span>

<span data-ttu-id="b641c-286">Dado que las imágenes nativas son archivos PE de Windows, están sujetas a las mismas cuestiones de cambio de ubicación que otros archivos ejecutables.</span><span class="sxs-lookup"><span data-stu-id="b641c-286">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="b641c-287">La repercusión que las reubicaciones tienen en el rendimiento es aún mayor si se usan enlaces fuertes.</span><span class="sxs-lookup"><span data-stu-id="b641c-287">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="b641c-288">Para establecer la dirección base de una imagen nativa, use la opción adecuada del compilador para establecer la dirección base del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-288">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="b641c-289">Ngen.exe usa esta dirección base para la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-289">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-290">Las imágenes nativas son de mayor tamaño que los ensamblados administrados a partir de los que se crean.</span><span class="sxs-lookup"><span data-stu-id="b641c-290">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="b641c-291">Las direcciones base deben calcularse para permitir estos tamaños mayores.</span><span class="sxs-lookup"><span data-stu-id="b641c-291">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="b641c-292">Para ver la dirección base preferida de una imagen nativa, puede usar una herramienta como dumpbin.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-292">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="b641c-293">Enlace fuerte</span><span class="sxs-lookup"><span data-stu-id="b641c-293">Hard binding</span></span>

<span data-ttu-id="b641c-294">El enlace fuerte aumenta el rendimiento y reduce el tamaño del espacio de trabajo de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-294">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="b641c-295">El inconveniente del enlace fuerte es que todas las imágenes con enlaces fuertes a un ensamblado deben cargarse al cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-295">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="b641c-296">Esto puede aumentar significativamente el tiempo de inicio de una aplicación de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="b641c-296">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="b641c-297">El enlace fuerte es adecuado para las dependencias que se cargan en todos los escenarios de la aplicación en los que el rendimiento es un factor crítico.</span><span class="sxs-lookup"><span data-stu-id="b641c-297">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="b641c-298">Al igual que con cualquier otro aspecto del uso de imágenes nativas, la realización de mediciones del rendimiento meticulosas constituye la única forma de determinar si el enlace fuerte mejora el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-298">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="b641c-299">Los atributos <xref:System.Runtime.CompilerServices.DependencyAttribute> y <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> permiten suministrar sugerencias de enlace fuerte a Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-299">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-300">Estos atributos son sugerencias para Ngen.exe, no comandos.</span><span class="sxs-lookup"><span data-stu-id="b641c-300">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="b641c-301">El uso de estos atributos no garantiza el enlace fuerte.</span><span class="sxs-lookup"><span data-stu-id="b641c-301">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="b641c-302">El significado de estos atributos puede cambiar en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="b641c-302">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="b641c-303">Especificación de una sugerencia de enlace para una dependencia</span><span class="sxs-lookup"><span data-stu-id="b641c-303">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="b641c-304">Aplique <xref:System.Runtime.CompilerServices.DependencyAttribute> a un ensamblado para indicar la probabilidad de que se cargue una dependencia especificada.</span><span class="sxs-lookup"><span data-stu-id="b641c-304">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="b641c-305"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indica que el enlace fuerte es adecuado, <xref:System.Runtime.CompilerServices.LoadHint.Default> indica que debe usarse el valor predeterminado de la dependencia y <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indica que el enlace fuerte no es adecuado.</span><span class="sxs-lookup"><span data-stu-id="b641c-305"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="b641c-306">En el siguiente código se muestran los atributos de un ensamblado que tiene dos dependencias.</span><span class="sxs-lookup"><span data-stu-id="b641c-306">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="b641c-307">La primera dependencia (Assembly1) es una candidata adecuada para el enlace fuerte, pero la segunda (Assembly2) no lo es.</span><span class="sxs-lookup"><span data-stu-id="b641c-307">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="b641c-308">El nombre de ensamblado no incluye la extensión de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-308">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="b641c-309">Pueden usarse nombres para mostrar.</span><span class="sxs-lookup"><span data-stu-id="b641c-309">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="b641c-310">Especificación de una sugerencia de enlace predeterminado para un ensamblado</span><span class="sxs-lookup"><span data-stu-id="b641c-310">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="b641c-311">Las sugerencias de enlace predeterminado solo son necesarias para los ensamblados que cualquier aplicación con una dependencia sobre los mismos vaya a usar inmediatamente y con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b641c-311">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="b641c-312">Aplique el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> con <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> a dichos ensamblados para especificar que debe usarse un enlace fuerte.</span><span class="sxs-lookup"><span data-stu-id="b641c-312">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-313">No hay ningún motivo para aplicar el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> a los ensamblados .dll que no pertenezcan a esta categoría, porque el hecho de aplicar el atributo con cualquier valor distinto de <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> produce el mismo efecto que no aplicar el atributo.</span><span class="sxs-lookup"><span data-stu-id="b641c-313">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="b641c-314">Microsoft usa el atributo <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> para especificar que el enlace fuerte es el valor predeterminado para un pequeño número de ensamblados de .NET Framework, como mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="b641c-314">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="b641c-315">Procesamiento diferido</span><span class="sxs-lookup"><span data-stu-id="b641c-315">Deferred processing</span></span>

<span data-ttu-id="b641c-316">La generación de imágenes nativas para una aplicación de gran tamaño puede llevar bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="b641c-316">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="b641c-317">Del mismo modo, los cambios realizados en un componente compartido o en la configuración del equipo pueden requerir la actualización de muchas imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-317">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="b641c-318">Las acciones `install` y `update` disponen de una opción `/queue` que pone en cola la operación para su ejecución diferida por parte del servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-318">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="b641c-319">Además, Ngen.exe dispone de las acciones `queue` y `executeQueuedItems`, que proporcionan algo de control sobre el servicio.</span><span class="sxs-lookup"><span data-stu-id="b641c-319">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="b641c-320">Para más información, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-320">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="b641c-321">Imágenes nativas y compilación JIT</span><span class="sxs-lookup"><span data-stu-id="b641c-321">Native images and JIT compilation</span></span>

<span data-ttu-id="b641c-322">Si Ngen.exe encuentra en un ensamblado métodos que no puede generar, los excluye de la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-322">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="b641c-323">Cuando el runtime ejecuta el ensamblado, usa la compilación JIT para los métodos que no se han incluido en la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-323">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="b641c-324">Además, si se ha actualizado el ensamblado o la imagen se ha invalidado por cualquier motivo, no se usan imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-324">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="b641c-325">Imágenes no válidas</span><span class="sxs-lookup"><span data-stu-id="b641c-325">Invalid images</span></span>

<span data-ttu-id="b641c-326">Cuando se usa Ngen.exe para crear una imagen nativa de un ensamblado, el resultado depende de las opciones especificadas en la línea de comandos y de determinadas opciones de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="b641c-326">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="b641c-327">Entre estas opciones de configuración, se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b641c-327">These settings include the following:</span></span>

- <span data-ttu-id="b641c-328">La versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b641c-328">The version of the .NET Framework.</span></span>

- <span data-ttu-id="b641c-329">La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="b641c-329">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="b641c-330">La identidad exacta del ensamblado (la recompilación cambia la identidad).</span><span class="sxs-lookup"><span data-stu-id="b641c-330">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="b641c-331">La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado (la recompilación cambia la identidad).</span><span class="sxs-lookup"><span data-stu-id="b641c-331">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="b641c-332">Factores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b641c-332">Security factors.</span></span>

<span data-ttu-id="b641c-333">Ngen.exe registra esta información cuando genera una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-333">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="b641c-334">Al ejecutar un ensamblado, el runtime busca la imagen nativa generada con las opciones y los valores de configuración que coinciden con el entorno actual del equipo.</span><span class="sxs-lookup"><span data-stu-id="b641c-334">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="b641c-335">El runtime usa la compilación JIT del ensamblado si no encuentra una imagen nativa coincidente.</span><span class="sxs-lookup"><span data-stu-id="b641c-335">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="b641c-336">Si se realizan los siguientes cambios en la configuración y el entorno de un equipo, las imágenes nativas dejarán de ser válidas:</span><span class="sxs-lookup"><span data-stu-id="b641c-336">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="b641c-337">La versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b641c-337">The version of the .NET Framework.</span></span>

     <span data-ttu-id="b641c-338">Si se aplica una actualización a .NET Framework, todas las imágenes nativas que se hayan creado mediante Ngen.exe dejarán de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="b641c-338">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="b641c-339">Por esta razón, todas las actualizaciones de .NET Framework ejecutan el comando `Ngen Update`, para garantizar que se vuelven a generar todas las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-339">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="b641c-340">.NET Framework crea nuevas imágenes nativas de forma automática para las bibliotecas de .NET Framework que instala.</span><span class="sxs-lookup"><span data-stu-id="b641c-340">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="b641c-341">La versión del sistema operativo, si se cambia de la familia Windows 9x a la familia Windows NT.</span><span class="sxs-lookup"><span data-stu-id="b641c-341">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="b641c-342">Por ejemplo, si la versión del sistema operativo que se ejecuta en un equipo cambia de Windows 98 a Windows XP, todas las imágenes nativas almacenadas en la memoria caché de imágenes nativas dejan de ser válidas.</span><span class="sxs-lookup"><span data-stu-id="b641c-342">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="b641c-343">Sin embargo, si el sistema operativo cambia de Windows 2000 a Windows XP, las imágenes siguen siendo válidas.</span><span class="sxs-lookup"><span data-stu-id="b641c-343">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="b641c-344">La identidad exacta del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-344">The exact identity of the assembly.</span></span>

     <span data-ttu-id="b641c-345">Si vuelve a compilar un ensamblado, su imagen nativa correspondiente deja de ser válida.</span><span class="sxs-lookup"><span data-stu-id="b641c-345">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="b641c-346">La identidad exacta de todos los ensamblados a los que hace referencia el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-346">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="b641c-347">Si actualiza un ensamblado administrado, todas las imágenes nativas que, directa o indirectamente, dependen de ese ensamblado dejan de ser válidas y deben volver a generarse.</span><span class="sxs-lookup"><span data-stu-id="b641c-347">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="b641c-348">Esto se aplica tanto a las referencias ordinarias como a las dependencias con enlaces fuertes.</span><span class="sxs-lookup"><span data-stu-id="b641c-348">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="b641c-349">Cuando se aplica una actualización de software, el programa de instalación debe ejecutar un comando `Ngen Update` para garantizar que se vuelven a generar todas las imágenes nativas dependientes.</span><span class="sxs-lookup"><span data-stu-id="b641c-349">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="b641c-350">Factores de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b641c-350">Security factors.</span></span>

     <span data-ttu-id="b641c-351">Si se modifica la directiva de seguridad del equipo para restringir los permisos previamente concedidos a un ensamblado, la imagen nativa compilada con anterioridad para dicho ensamblado puede dejar de ser válida.</span><span class="sxs-lookup"><span data-stu-id="b641c-351">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="b641c-352">Para información detallada sobre cómo Common Language Runtime administra la seguridad de acceso del código y sobre cómo usar los permisos, consulte [Seguridad de acceso del código](../misc/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="b641c-352">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="b641c-353">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b641c-353">Troubleshooting</span></span>

<span data-ttu-id="b641c-354">Los temas de solución de problemas siguientes permiten ver cuáles son las imágenes nativas que la aplicación usa y cuáles no puede usar, determinar cuándo el compilador JIT comienza a compilar un método y muestra cómo excluir la compilación de imágenes nativas de métodos específicos.</span><span class="sxs-lookup"><span data-stu-id="b641c-354">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="b641c-355">Visor de registro de enlaces de ensamblados</span><span class="sxs-lookup"><span data-stu-id="b641c-355">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="b641c-356">Para confirmar que la aplicación está usando imágenes nativas, puede usar [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](fuslogvw-exe-assembly-binding-log-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b641c-356">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="b641c-357">Seleccione **Imágenes nativas** en el cuadro **Categorías de registro** de la ventana del visor de registro de enlaces.</span><span class="sxs-lookup"><span data-stu-id="b641c-357">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="b641c-358">Fuslogvw.exe proporciona información sobre el motivo por el que se ha rechazado una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-358">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="b641c-359">Asistente para la depuración administrada JITCompilationStart</span><span class="sxs-lookup"><span data-stu-id="b641c-359">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="b641c-360">Puede usar el Asistente para la depuración administrada (MDA) [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) para determinar el momento en el que el compilador JIT empieza a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="b641c-360">You can use the [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="b641c-361">Exclusión de la generación de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-361">Opting out of native image generation</span></span>

<span data-ttu-id="b641c-362">En algunos casos, NGen.exe puede tener problemas para generar una imagen nativa para un método específico, o bien es posible que prefiera que el método se compile en JIT en lugar de compilarlo en una imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-362">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="b641c-363">En este caso, puede usar el atributo `System.Runtime.BypassNGenAttribute` para evitar que NGen.exe genere una imagen nativa para un método concreto.</span><span class="sxs-lookup"><span data-stu-id="b641c-363">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="b641c-364">El atributo se debe aplicar individualmente a cada método cuyo código no desea que se incluya en la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="b641c-364">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="b641c-365">NGen.exe reconoce el atributo y no genera código en la imagen nativa para el método correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b641c-365">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="b641c-366">Pero tenga en cuenta que `BypassNGenAttribute` no está definido como tipo en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b641c-366">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="b641c-367">Para usar el atributo en el código, primero debe definirlo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b641c-367">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="b641c-368">Luego puede aplicar el atributo a cada método.</span><span class="sxs-lookup"><span data-stu-id="b641c-368">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="b641c-369">En el ejemplo siguiente se indica al Generador de imágenes nativas que no debe generar una imagen nativa para el método `ExampleClass.ToJITCompile`.</span><span class="sxs-lookup"><span data-stu-id="b641c-369">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="b641c-370">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b641c-370">Examples</span></span>

<span data-ttu-id="b641c-371">El siguiente comando genera una imagen nativa para `ClientApp.exe`, que se encuentra en el directorio actual, e instala la imagen en la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-371">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="b641c-372">Si existe un archivo de configuración para el ensamblado, Ngen.exe usará dicho archivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-372">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="b641c-373">Además, se generarán imágenes nativas para cualquier archivo .dll al que haga referencia `ClientApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="b641c-373">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```console
ngen install ClientApp.exe
```

<span data-ttu-id="b641c-374">Una imagen instalada con Ngen.exe también recibe el nombre de raíz.</span><span class="sxs-lookup"><span data-stu-id="b641c-374">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="b641c-375">Una raíz puede ser una aplicación o un componente compartido.</span><span class="sxs-lookup"><span data-stu-id="b641c-375">A root can be an application or a shared component.</span></span>

<span data-ttu-id="b641c-376">El siguiente comando genera una imagen nativa para `MyAssembly.exe` con la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="b641c-376">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```console
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="b641c-377">A la hora de buscar los ensamblados y sus dependencias, Ngen.exe usa la misma lógica de búsqueda que Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b641c-377">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="b641c-378">De forma predeterminada, el directorio que contiene `ClientApp.exe` se usa como directorio base de la aplicación y todas las búsquedas de ensamblados comienzan en este directorio.</span><span class="sxs-lookup"><span data-stu-id="b641c-378">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="b641c-379">Se puede reemplazar este comportamiento mediante la opción `/AppBase`.</span><span class="sxs-lookup"><span data-stu-id="b641c-379">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-380">Se trata de un cambio de comportamiento de Ngen.exe en las versiones 1.0 y 1.1 de .NET Framework, donde la base de la aplicación está establecida en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b641c-380">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="b641c-381">Un ensamblado puede disponer de una dependencia sin referencia alguna; por ejemplo, si carga un archivo .dll mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b641c-381">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b641c-382">Se puede crear una imagen nativa de este archivo .dll usando la información de configuración del ensamblado de aplicación, con la opción `/ExeConfig`.</span><span class="sxs-lookup"><span data-stu-id="b641c-382">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="b641c-383">El siguiente comando genera una imagen nativa de `MyLib.dll,` usando la información de configuración de `MyApp.exe`.</span><span class="sxs-lookup"><span data-stu-id="b641c-383">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="b641c-384">Los ensamblados instalados de esta manera no se quitan cuando se quita la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b641c-384">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="b641c-385">Para desinstalar una dependencia, use las mismas opciones de línea de comandos que se usaron para su instalación.</span><span class="sxs-lookup"><span data-stu-id="b641c-385">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="b641c-386">El siguiente comando desinstala el archivo `MyLib.dll` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b641c-386">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="b641c-387">Para crear una imagen nativa de un ensamblado en la caché global de ensamblados, use el nombre para mostrar del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-387">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="b641c-388">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b641c-388">For example:</span></span>

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="b641c-389">NGen.exe generará un conjunto independiente de imágenes para cada escenario que se instale.</span><span class="sxs-lookup"><span data-stu-id="b641c-389">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="b641c-390">Por ejemplo, el siguiente comando instala un conjunto completo de imágenes nativas para el funcionamiento normal, otro conjunto completo para la depuración, y un tercer conjunto para la creación de perfiles:</span><span class="sxs-lookup"><span data-stu-id="b641c-390">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="b641c-391">Mostrar la memoria caché de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-391">Displaying the Native Image Cache</span></span>

<span data-ttu-id="b641c-392">Una vez instaladas en la memoria caché las imágenes nativas, se pueden mostrar mediante Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-392">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="b641c-393">El siguiente comando muestra todas las imágenes nativas que contiene la memoria caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-393">The following command displays all native images in the native image cache.</span></span>

```console
ngen display
```

<span data-ttu-id="b641c-394">La acción `display` muestra primero todos los ensamblados raíz, seguidos de una lista de todas las imágenes nativas del equipo.</span><span class="sxs-lookup"><span data-stu-id="b641c-394">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="b641c-395">Use el nombre simple de un ensamblado para mostrar únicamente información de dicho ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b641c-395">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="b641c-396">El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas que coinciden con el nombre parcial `MyAssembly`, sus dependencias y todas las raíces que tienen una dependencia en `MyAssembly`:</span><span class="sxs-lookup"><span data-stu-id="b641c-396">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```console
ngen display MyAssembly
```

<span data-ttu-id="b641c-397">Conocer las raíces que dependen de un ensamblado de componente compartido resulta de gran utilidad para valorar el impacto de una acción `update` una vez actualizado el componente compartido.</span><span class="sxs-lookup"><span data-stu-id="b641c-397">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="b641c-398">Si especifica la extensión de archivo de un ensamblado, deberá especificar la ruta de acceso o ejecutar Ngen.exe desde el directorio que contiene el ensamblado:</span><span class="sxs-lookup"><span data-stu-id="b641c-398">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```console
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="b641c-399">El siguiente comando muestra todas las imágenes nativas de la memoria caché de imágenes nativas con el nombre `MyAssembly` y la versión 1.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="b641c-399">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="b641c-400">Actualizar imágenes</span><span class="sxs-lookup"><span data-stu-id="b641c-400">Updating Images</span></span>

<span data-ttu-id="b641c-401">Normalmente, las imágenes se actualizan tras la actualización de un componente compartido.</span><span class="sxs-lookup"><span data-stu-id="b641c-401">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="b641c-402">Para actualizar todas las imágenes nativas que hayan cambiado o cuyas dependencias hayan cambiado, use la acción `update` sin ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="b641c-402">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```console
ngen update
```

<span data-ttu-id="b641c-403">Actualizar todas las imágenes puede ser un proceso largo.</span><span class="sxs-lookup"><span data-stu-id="b641c-403">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="b641c-404">La opción `/queue` pone en cola las actualizaciones para que las ejecute el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-404">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="b641c-405">Para más información sobre la opción `/queue` y las prioridades de instalación, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-405">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```console
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="b641c-406">Desinstalar imágenes</span><span class="sxs-lookup"><span data-stu-id="b641c-406">Uninstalling Images</span></span>

<span data-ttu-id="b641c-407">Ngen.exe mantiene una lista de dependencias; de este modo, los componentes compartidos se quitan únicamente cuando se han quitado todos los ensamblados que dependen de ellos.</span><span class="sxs-lookup"><span data-stu-id="b641c-407">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="b641c-408">Además, si un componente compartido se ha instalado como raíz, no se quita.</span><span class="sxs-lookup"><span data-stu-id="b641c-408">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="b641c-409">El siguiente comando desinstala todos los escenarios de la raíz `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="b641c-409">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp
```

<span data-ttu-id="b641c-410">Se puede usar la acción `uninstall` para quitar escenarios concretos.</span><span class="sxs-lookup"><span data-stu-id="b641c-410">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="b641c-411">El siguiente comando desinstala todos los escenarios de depuración de `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="b641c-411">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="b641c-412">Cuando se desinstalan escenarios `/debug` no se desinstalan los escenarios que incluyen tanto `/profile` como `/debug.`</span><span class="sxs-lookup"><span data-stu-id="b641c-412">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="b641c-413">El siguiente comando desinstala todos los escenarios de una versión concreta de `ClientApp.exe`:</span><span class="sxs-lookup"><span data-stu-id="b641c-413">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="b641c-414">Los siguientes comandos desinstalan todos los escenarios de `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` o simplemente el escenario de depuración de dicho ensamblado:</span><span class="sxs-lookup"><span data-stu-id="b641c-414">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="b641c-415">Al igual que ocurre con la acción `install`, cuando se suministra una extensión, es necesario ejecutar Ngen.exe desde el directorio que contiene el ensamblado o especificar una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="b641c-415">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="b641c-416">Para ver ejemplos relacionados con el servicio de imágenes nativas, consulte [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-416">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="b641c-417">Tarea de imagen nativa</span><span class="sxs-lookup"><span data-stu-id="b641c-417">Native Image Task</span></span>

<span data-ttu-id="b641c-418">La tarea de imagen nativa es una tarea de Windows que genera y mantiene imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-418">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="b641c-419">La tarea de imagen nativa genera y recupera automáticamente imágenes nativas para los escenarios admitidos.</span><span class="sxs-lookup"><span data-stu-id="b641c-419">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="b641c-420">También permite que los instaladores usen [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md) para aplazar la creación y la actualización de las imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-420">It also enables installers to use [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="b641c-421">La tarea de imagen nativa se registra una vez por cada arquitectura de CPU admitida en un equipo, para permitir la compilación de las aplicaciones que tienen como destino cada arquitectura:</span><span class="sxs-lookup"><span data-stu-id="b641c-421">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="b641c-422">Nombre de la tarea</span><span class="sxs-lookup"><span data-stu-id="b641c-422">Task name</span></span>|<span data-ttu-id="b641c-423">Equipo de 32 bits</span><span class="sxs-lookup"><span data-stu-id="b641c-423">32-bit computer</span></span>|<span data-ttu-id="b641c-424">Equipo de 64 bits</span><span class="sxs-lookup"><span data-stu-id="b641c-424">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="b641c-425">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="b641c-425">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="b641c-426">Sí</span><span class="sxs-lookup"><span data-stu-id="b641c-426">Yes</span></span>|<span data-ttu-id="b641c-427">Sí</span><span class="sxs-lookup"><span data-stu-id="b641c-427">Yes</span></span>|
|<span data-ttu-id="b641c-428">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="b641c-428">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="b641c-429">No</span><span class="sxs-lookup"><span data-stu-id="b641c-429">No</span></span>|<span data-ttu-id="b641c-430">Sí</span><span class="sxs-lookup"><span data-stu-id="b641c-430">Yes</span></span>|

<span data-ttu-id="b641c-431">La tarea de imagen nativa está disponible en .NET Framework 4.5 y las versiones posteriores, con Windows 8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="b641c-431">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="b641c-432">En las versiones anteriores de Windows, .NET Framework usa el [Servicio de imágenes nativas](#native-image-service).</span><span class="sxs-lookup"><span data-stu-id="b641c-432">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="b641c-433">Duración de la tarea</span><span class="sxs-lookup"><span data-stu-id="b641c-433">Task Lifetime</span></span>

<span data-ttu-id="b641c-434">En general, el Programador de tareas de Windows inicia la tarea de imagen nativa cada noche, cuando el equipo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-434">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="b641c-435">La tarea busca los trabajos aplazados puestos en cola por los instaladores de aplicaciones, las solicitudes aplazadas de actualización de imágenes nativas y las creaciones automáticas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="b641c-435">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="b641c-436">La tarea completa los elementos de trabajo pendientes y, después, se apaga.</span><span class="sxs-lookup"><span data-stu-id="b641c-436">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="b641c-437">Si el equipo deja de estar inactivo mientras se ejecuta la tarea, esta se detendrá.</span><span class="sxs-lookup"><span data-stu-id="b641c-437">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="b641c-438">También puede iniciar la tarea de imagen nativa manualmente con la interfaz de usuario del Programador de tareas o con llamadas manuales a NGen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-438">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="b641c-439">Si la tarea se inicia con alguno de estos métodos, seguirá ejecutándose cuando el equipo ya no esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-439">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="b641c-440">Las imágenes creadas manualmente con NGen.exe tienen mayor prioridad, para que el comportamiento de los instaladores de aplicaciones sea predecible.</span><span class="sxs-lookup"><span data-stu-id="b641c-440">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="b641c-441">Servicio de imágenes nativas</span><span class="sxs-lookup"><span data-stu-id="b641c-441">Native Image Service</span></span>

<span data-ttu-id="b641c-442">El servicio de imágenes nativas es un servicio de Windows que genera y mantiene imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-442">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="b641c-443">El servicio de imágenes nativas permite al desarrollador aplazar la instalación y la actualización de imágenes nativas hasta los períodos en los que el equipo está inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-443">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="b641c-444">Normalmente, quien inicia el servicio de imágenes nativas es el programa de instalación (el instalador) de una aplicación o una actualización.</span><span class="sxs-lookup"><span data-stu-id="b641c-444">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="b641c-445">En el caso de las acciones de prioridad 3, el servicio se ejecuta durante el tiempo de inactividad del equipo.</span><span class="sxs-lookup"><span data-stu-id="b641c-445">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="b641c-446">El servicio guarda su estado y es capaz de continuar a lo largo de varios reinicios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b641c-446">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="b641c-447">Se pueden poner en cola varias compilaciones de imágenes.</span><span class="sxs-lookup"><span data-stu-id="b641c-447">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="b641c-448">El servicio también interactúa con el comando Ngen.exe manual.</span><span class="sxs-lookup"><span data-stu-id="b641c-448">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="b641c-449">Los comandos manuales tienen prioridad sobre la actividad en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b641c-449">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="b641c-450">En Windows Vista, el nombre del servicio de imágenes nativas que se muestra es "Microsoft.NET Framework NGEN v2.0.50727_X86" o "Microsoft.NET Framework NGEN v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="b641c-450">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="b641c-451">En todas las versiones anteriores de Microsoft Windows, el nombre es "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X86" o "Servicio de optimización de tiempo de ejecución de .NET v2.0.50727_X64".</span><span class="sxs-lookup"><span data-stu-id="b641c-451">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="b641c-452">Iniciar operaciones aplazadas</span><span class="sxs-lookup"><span data-stu-id="b641c-452">Launching Deferred Operations</span></span>

<span data-ttu-id="b641c-453">Antes de comenzar una instalación o una actualización, se recomienda pausar el servicio.</span><span class="sxs-lookup"><span data-stu-id="b641c-453">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="b641c-454">Así, el servicio no se ejecutará mientras el instalador copia archivos o coloca ensamblados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b641c-454">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="b641c-455">La siguiente línea de comandos de Ngen.exe pausa el servicio:</span><span class="sxs-lookup"><span data-stu-id="b641c-455">The following Ngen.exe command line pauses the service:</span></span>

```console
ngen queue pause
```

<span data-ttu-id="b641c-456">Después de poner en cola todas las operaciones aplazadas, el siguiente comando permite reanudar el servicio:</span><span class="sxs-lookup"><span data-stu-id="b641c-456">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```console
ngen queue continue
```

<span data-ttu-id="b641c-457">Para aplazar la generación de imágenes nativas al instalar una nueva aplicación o al actualizar un componente compartido, utilice la opción `/queue` con las acciones `install` o `update`.</span><span class="sxs-lookup"><span data-stu-id="b641c-457">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="b641c-458">Las siguientes líneas de comandos de Ngen.exe instalan una imagen nativa de un componente compartido y realizan una actualización de todas las raíces a las que puede que afectaran:</span><span class="sxs-lookup"><span data-stu-id="b641c-458">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```console
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="b641c-459">La acción `update` vuelve a generar todas las imágenes nativas invalidadas, no solo las que utilizan `MyComponent`.</span><span class="sxs-lookup"><span data-stu-id="b641c-459">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="b641c-460">Si la aplicación está formada por muchas raíces, puede controlar la prioridad de las acciones aplazadas.</span><span class="sxs-lookup"><span data-stu-id="b641c-460">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="b641c-461">Los siguientes comandos ponen en cola la instalación de tres raíces.</span><span class="sxs-lookup"><span data-stu-id="b641c-461">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="b641c-462">`Assembly1` se instala en primer lugar, sin esperar al tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="b641c-462">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="b641c-463">`Assembly2` también se instala sin esperar al tiempo de inactividad, pero una vez que finalizan todas las acciones de prioridad 1.</span><span class="sxs-lookup"><span data-stu-id="b641c-463">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="b641c-464">`Assembly3` se instala cuando el servicio detecta que el equipo se encuentra inactivo.</span><span class="sxs-lookup"><span data-stu-id="b641c-464">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="b641c-465">Puede forzar la ejecución sincrónica de las acciones en cola con la acción `executeQueuedItems`.</span><span class="sxs-lookup"><span data-stu-id="b641c-465">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="b641c-466">Si especifica la prioridad (opcional), esta acción afecta solo a las acciones en cola que tienen una prioridad igual o menor.</span><span class="sxs-lookup"><span data-stu-id="b641c-466">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="b641c-467">La prioridad predeterminada es 3, por lo que el siguiente comando de Ngen.exe procesa todas las acciones en cola inmediatamente y no vuelve hasta que finalizan:</span><span class="sxs-lookup"><span data-stu-id="b641c-467">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```console
ngen executeQueuedItems
```

<span data-ttu-id="b641c-468">Los comandos sincrónicos son ejecutados por Ngen.exe y no utilizan el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-468">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="b641c-469">Puede ejecutar acciones con Ngen.exe mientras se está ejecutando el servicio de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="b641c-469">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="b641c-470">Apagado del servicio</span><span class="sxs-lookup"><span data-stu-id="b641c-470">Service Shutdown</span></span>

<span data-ttu-id="b641c-471">El servicio, después de iniciarse con la ejecución de un comando de Ngen.exe que incluye la opción `/queue`, se ejecuta en segundo plano hasta que se completan todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="b641c-471">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="b641c-472">El servicio guarda su estado para poder continuar a lo largo de varios reinicios si es necesario.</span><span class="sxs-lookup"><span data-stu-id="b641c-472">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="b641c-473">Cuando el servicio detecta que no hay más acciones en cola, restablece su estado para no reiniciarse la próxima vez que se arranque el equipo y, luego, se apaga.</span><span class="sxs-lookup"><span data-stu-id="b641c-473">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="b641c-474">Interacción del servicio con los clientes</span><span class="sxs-lookup"><span data-stu-id="b641c-474">Service Interaction with Clients</span></span>

<span data-ttu-id="b641c-475">En la versión 2.0 de .NET Framework, la única interacción con el servicio de imágenes nativas es a través de la herramienta de línea de comandos Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="b641c-475">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="b641c-476">Utilice la herramienta de línea de comandos en los scripts de instalación para poner en cola las acciones del servicio de imágenes nativas e interactuar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b641c-476">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="b641c-477">Vea también</span><span class="sxs-lookup"><span data-stu-id="b641c-477">See also</span></span>

- [<span data-ttu-id="b641c-478">Herramientas</span><span class="sxs-lookup"><span data-stu-id="b641c-478">Tools</span></span>](index.md)
- [<span data-ttu-id="b641c-479">Proceso de ejecución administrada</span><span class="sxs-lookup"><span data-stu-id="b641c-479">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="b641c-480">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="b641c-480">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="b641c-481">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="b641c-481">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)

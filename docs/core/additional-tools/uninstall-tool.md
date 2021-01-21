---
title: Herramienta de desinstalación
description: Información general de la herramienta de desinstalación de .NET Core, una herramienta guiada que permite limpiar de forma controlada los SDK y los entornos en tiempo de ejecución de .NET Core.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: ed43b4ec8437ae0ccaf5f1234758dda9f16bd51e
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235357"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="c5e13-103">Herramienta de desinstalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c5e13-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="c5e13-104">La [herramienta de desinstalación de .NET Core](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos en tiempo de ejecución de .NET Core de un sistema.</span><span class="sxs-lookup"><span data-stu-id="c5e13-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="c5e13-105">Hay una colección de opciones disponible para especificar las versiones que desea desinstalar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="c5e13-106">La herramienta es compatible con Windows y macOS.</span><span class="sxs-lookup"><span data-stu-id="c5e13-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="c5e13-107">Linux no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="c5e13-107">Linux is currently not supported.</span></span>

<span data-ttu-id="c5e13-108">En Windows, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución que se instalaron mediante uno de los siguientes instaladores:</span><span class="sxs-lookup"><span data-stu-id="c5e13-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="c5e13-109">El instalador del SDK y del entorno en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="c5e13-110">El instalador de Visual Studio en versiones anteriores a Visual Studio 2019, versión 16.3.</span><span class="sxs-lookup"><span data-stu-id="c5e13-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="c5e13-111">En macOS, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución ubicados en la carpeta */usr/local/share/dotnet*.</span><span class="sxs-lookup"><span data-stu-id="c5e13-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="c5e13-112">Debido a estas limitaciones, es posible que la herramienta no pueda desinstalar todos los SDK y los entornos en tiempo de ejecución de .NET Core de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c5e13-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="c5e13-113">Puede usar el comando `dotnet --info` para buscar todos los SDK y los entornos en tiempo de ejecución de .NET Core instalados, incluidos los entornos en tiempo de ejecución y SDK que esta herramienta no puede quitar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="c5e13-114">El comando `dotnet-core-uninstall list` muestra qué SDK se pueden desinstalar con la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span> <span data-ttu-id="c5e13-115">La versión 1.2 y posteriores pueden desinstalar SDK y entornos de ejecución con la versión 5.0 o anteriores, mientras que las versiones anteriores de la herramienta pueden desinstalar la versión 3.1 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-115">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="c5e13-116">Instalación de la herramienta</span><span class="sxs-lookup"><span data-stu-id="c5e13-116">Install the tool</span></span>

<span data-ttu-id="c5e13-117">Puede descargar la herramienta de desinstalación de .NET Core desde [la página de versiones de la herramienta](https://aka.ms/dotnet-core-uninstall-tool) y encontrar el código fuente en el repositorio [dotnet/cli-lab](https://github.com/dotnet/cli-lab) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="c5e13-117">You can download the .NET Core Uninstall Tool from [the tool's releases page](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="c5e13-118">La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-118">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="c5e13-119">Por lo tanto, debe instalarse en un directorio protegido contra escritura, como *C:\Archivos de programa* en Windows o */usr/local/bin* en macOS.</span><span class="sxs-lookup"><span data-stu-id="c5e13-119">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="c5e13-120">Consulte también [Acceso con privilegios elevados para comandos de dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="c5e13-120">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="c5e13-121">Para obtener más información, vea las [instrucciones de instalación detalladas](https://aka.ms/dotnet-core-uninstall-tool).</span><span class="sxs-lookup"><span data-stu-id="c5e13-121">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="c5e13-122">Ejecución de la herramienta</span><span class="sxs-lookup"><span data-stu-id="c5e13-122">Run the tool</span></span>

<span data-ttu-id="c5e13-123">En los pasos siguientes se muestra el enfoque recomendado para ejecutar la herramienta de desinstalación:</span><span class="sxs-lookup"><span data-stu-id="c5e13-123">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="c5e13-124">Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados</span><span class="sxs-lookup"><span data-stu-id="c5e13-124">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="c5e13-125">Paso 2: Realizar un simulacro</span><span class="sxs-lookup"><span data-stu-id="c5e13-125">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="c5e13-126">Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c5e13-126">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="c5e13-127">Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)</span><span class="sxs-lookup"><span data-stu-id="c5e13-127">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="c5e13-128">Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados</span><span class="sxs-lookup"><span data-stu-id="c5e13-128">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="c5e13-129">El comando `dotnet-core-uninstall list` enumera los SDK y los entornos en tiempo de ejecución de .NET Core instalados que se pueden quitar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-129">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="c5e13-130">Visual Studio puede necesitar algunos SDK y entornos en tiempo de ejecución, que se muestran con una nota de por qué no se recomienda desinstalarlos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-130">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="c5e13-131">En la mayoría de los casos, la salida del comando `dotnet-core-uninstall list` no coincidirá con la lista de versiones instaladas en la salida de `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-131">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="c5e13-132">En concreto, esta herramienta no mostrará las versiones instaladas mediante archivos ZIP ni administradas por Visual Studio (cualquier versión instalada con Visual Studio 2019 16.3 o posterior).</span><span class="sxs-lookup"><span data-stu-id="c5e13-132">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="c5e13-133">Una manera de comprobar si una versión está administrada por Visual Studio es verla en `Add or Remove Programs`, donde las versiones administradas de Visual Studio se marcan como tales en sus nombres para mostrar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-133">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="c5e13-134">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="c5e13-134">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="c5e13-135">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c5e13-135">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="c5e13-136">Opciones</span><span class="sxs-lookup"><span data-stu-id="c5e13-136">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="c5e13-137">Windows</span><span class="sxs-lookup"><span data-stu-id="c5e13-137">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="c5e13-138">Enumera todos los entornos en tiempo de ejecución de ASP.NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-138">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="c5e13-139">Enumera todos los conjuntos de hospedaje de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-139">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="c5e13-140">Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-140">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-141">Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-141">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-142">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-142">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-143">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-143">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-144">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-144">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="c5e13-145">Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x64 que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-145">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="c5e13-146">Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x86 que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-146">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="c5e13-147">macOS</span><span class="sxs-lookup"><span data-stu-id="c5e13-147">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="c5e13-148">Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-148">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-149">Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-149">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-150">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-150">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-151">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-152">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-152">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="c5e13-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5e13-153">Examples</span></span>

* <span data-ttu-id="c5e13-154">Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core que se pueden quitar con esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="c5e13-154">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="c5e13-155">Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="c5e13-155">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="c5e13-156">Enumerar todos los SDK de .NET Core x86:</span><span class="sxs-lookup"><span data-stu-id="c5e13-156">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="c5e13-157">Paso 2: Realizar un simulacro</span><span class="sxs-lookup"><span data-stu-id="c5e13-157">Step 2 - Do a dry run</span></span>

<span data-ttu-id="c5e13-158">Los comandos `dotnet-core-uninstall dry-run` y `dotnet-core-uninstall whatif` muestran los SDK y los entornos en tiempo de ejecución de .NET Core que se quitarán en función de las opciones proporcionadas sin realizar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="c5e13-158">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="c5e13-159">Estos comandos son sinónimos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-159">These commands are synonyms.</span></span>

<span data-ttu-id="c5e13-160">**dotnet-core-uninstall dry-run y dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="c5e13-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="c5e13-161">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c5e13-161">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="c5e13-162">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5e13-162">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="c5e13-163">La versión especificada que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-163">The specified version to uninstall.</span></span> <span data-ttu-id="c5e13-164">Puede enumerar varias versiones una detrás de la otra, separadas por espacios.</span><span class="sxs-lookup"><span data-stu-id="c5e13-164">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="c5e13-165">También se admiten los archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-165">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="c5e13-166">Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-166">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="c5e13-167">Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="c5e13-167">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="c5e13-168">Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-168">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="c5e13-169">Opciones</span><span class="sxs-lookup"><span data-stu-id="c5e13-169">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="c5e13-170">Windows</span><span class="sxs-lookup"><span data-stu-id="c5e13-170">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="c5e13-171">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-171">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-172">Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-172">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="c5e13-173">La versión especificada permanece instalada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-173">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-174">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5e13-174">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="c5e13-175">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-175">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="c5e13-176">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-176">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="c5e13-177">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="c5e13-177">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="c5e13-178">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="c5e13-178">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="c5e13-179">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-179">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="c5e13-180">Solo quita los entornos en tiempos de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-180">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="c5e13-181">Quita el entorno en tiempo de ejecución de .NET Core y los conjuntos de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c5e13-181">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="c5e13-182">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-182">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="c5e13-183">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-183">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-184">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-184">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-185">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-185">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-186">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-187">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-187">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="c5e13-188">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.</span><span class="sxs-lookup"><span data-stu-id="c5e13-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="c5e13-189">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.</span><span class="sxs-lookup"><span data-stu-id="c5e13-189">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="c5e13-190">**`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-190">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="c5e13-191">Notas:</span><span class="sxs-lookup"><span data-stu-id="c5e13-191">Notes:</span></span>

1. <span data-ttu-id="c5e13-192">Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-192">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="c5e13-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="c5e13-194">Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.</span><span class="sxs-lookup"><span data-stu-id="c5e13-194">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="c5e13-195">macOS</span><span class="sxs-lookup"><span data-stu-id="c5e13-195">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="c5e13-196">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-196">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-197">Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-197">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="c5e13-198">La versión especificada se conservará.</span><span class="sxs-lookup"><span data-stu-id="c5e13-198">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-199">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5e13-199">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="c5e13-200">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-200">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="c5e13-201">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-201">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="c5e13-202">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="c5e13-202">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="c5e13-203">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="c5e13-203">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="c5e13-204">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-204">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="c5e13-205">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-205">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="c5e13-206">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-206">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-207">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-207">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-208">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-208">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-209">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-209">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-210">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-210">The default value is `normal`.</span></span>
  
* <span data-ttu-id="c5e13-211">**`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-211">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="c5e13-212">Notas:</span><span class="sxs-lookup"><span data-stu-id="c5e13-212">Notes:</span></span>

1. <span data-ttu-id="c5e13-213">Se requiere uno de los valores `--sdk` y `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-213">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="c5e13-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="c5e13-215">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5e13-215">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="c5e13-216">De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK no se incluyen en la salida de `dotnet-core-uninstall dry-run`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-216">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="c5e13-217">En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados no se incluyan en la salida, según el estado de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c5e13-217">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="c5e13-218">Para incluir todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-218">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="c5e13-219">Realizar un simulacro de la eliminación de todos entornos en tiempo de ejecución de .NET Core que se han reemplazado por revisiones superiores:</span><span class="sxs-lookup"><span data-stu-id="c5e13-219">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="c5e13-220">Realizar un simulacro de la eliminación de todos los SDK de .NET Core inferiores a la versión `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="c5e13-220">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="c5e13-221">Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c5e13-221">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="c5e13-222">`dotnet-core-uninstall remove` desinstala los SDK y los entornos en tiempo de ejecución de .NET Core especificados por una colección de opciones.</span><span class="sxs-lookup"><span data-stu-id="c5e13-222">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="c5e13-223">La versión 1.2 y posteriores pueden desinstalar SDK y entornos de ejecución con la versión 5.0 o anteriores, mientras que las versiones anteriores de la herramienta pueden desinstalar la versión 3.1 y anteriores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-223">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

<span data-ttu-id="c5e13-224">Dado que esta herramienta tiene un comportamiento destructivo, es **altamente** recomendable que realice un simulacro antes de ejecutar el comando remove.</span><span class="sxs-lookup"><span data-stu-id="c5e13-224">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="c5e13-225">El simulacro le mostrará qué SDK y entornos en tiempo de ejecución de .NET Core se quitarán cuando use el comando `remove`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-225">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="c5e13-226">Consulte [¿Puedo quitar una versión?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) para saber qué SDK y entornos en tiempo de ejecución se pueden quitar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c5e13-226">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="c5e13-227">Tenga en cuenta las siguientes advertencias:</span><span class="sxs-lookup"><span data-stu-id="c5e13-227">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="c5e13-228">Esta herramienta puede desinstalar las versiones del SDK de .NET Core que necesitan los archivos `global.json` de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c5e13-228">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="c5e13-229">Puede volver a instalar los SDK de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c5e13-229">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="c5e13-230">Esta herramienta puede desinstalar las versiones del entorno en tiempo de ejecución de .NET Core que necesitan las aplicaciones que dependen del marco de trabajo de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c5e13-230">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="c5e13-231">Puede volver a instalar los entornos en tiempo de ejecución de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c5e13-231">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="c5e13-232">Esta herramienta puede desinstalar las versiones del SDK y del entorno en tiempo de ejecución de .NET Core en las que se basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c5e13-232">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="c5e13-233">Si interrumpe la instalación de Visual Studio, ejecute "Reparar" en el instalador de Visual Studio para volver a un estado de funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="c5e13-233">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="c5e13-234">De forma predeterminada, todos los comandos mantienen los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK.</span><span class="sxs-lookup"><span data-stu-id="c5e13-234">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="c5e13-235">Estos SDK y entornos en tiempos de ejecución se pueden desinstalar si se enumeran explícitamente como argumentos o mediante la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-235">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="c5e13-236">La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-236">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="c5e13-237">Ejecute la herramienta en un símbolo del sistema de administrador en Windows y con `sudo` en macOS.</span><span class="sxs-lookup"><span data-stu-id="c5e13-237">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="c5e13-238">Los comandos `dry-run` y `whatif` no requieren elevación.</span><span class="sxs-lookup"><span data-stu-id="c5e13-238">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="c5e13-239">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="c5e13-239">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="c5e13-240">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c5e13-240">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="c5e13-241">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c5e13-241">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="c5e13-242">La versión especificada que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-242">The specified version to uninstall.</span></span> <span data-ttu-id="c5e13-243">Puede enumerar varias versiones una detrás de la otra, separadas por espacios.</span><span class="sxs-lookup"><span data-stu-id="c5e13-243">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="c5e13-244">También se admiten los archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-244">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="c5e13-245">Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-245">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="c5e13-246">Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="c5e13-246">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="c5e13-247">Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-247">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="c5e13-248">Opciones</span><span class="sxs-lookup"><span data-stu-id="c5e13-248">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="c5e13-249">Windows</span><span class="sxs-lookup"><span data-stu-id="c5e13-249">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="c5e13-250">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-250">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-251">Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-251">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="c5e13-252">La versión especificada permanece instalada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-252">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-253">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5e13-253">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="c5e13-254">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-254">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="c5e13-255">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-255">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="c5e13-256">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="c5e13-256">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="c5e13-257">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="c5e13-257">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="c5e13-258">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-258">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="c5e13-259">Solo quita los entornos en tiempos de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-259">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="c5e13-260">Solo quita conjuntos de hospedaje de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-260">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="c5e13-261">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-261">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="c5e13-262">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-262">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-263">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-263">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-264">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-264">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-265">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-265">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-266">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-266">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="c5e13-267">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.</span><span class="sxs-lookup"><span data-stu-id="c5e13-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="c5e13-268">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.</span><span class="sxs-lookup"><span data-stu-id="c5e13-268">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="c5e13-269">**`-y, --yes`** Ejecuta el comando sin requerir una confirmación sí o no.</span><span class="sxs-lookup"><span data-stu-id="c5e13-269">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="c5e13-270">**`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-270">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="c5e13-271">Notas:</span><span class="sxs-lookup"><span data-stu-id="c5e13-271">Notes:</span></span>

1. <span data-ttu-id="c5e13-272">Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-272">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="c5e13-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="c5e13-274">Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.</span><span class="sxs-lookup"><span data-stu-id="c5e13-274">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="c5e13-275">macOS</span><span class="sxs-lookup"><span data-stu-id="c5e13-275">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="c5e13-276">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-276">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-277">Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-277">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="c5e13-278">La versión especificada se conservará.</span><span class="sxs-lookup"><span data-stu-id="c5e13-278">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="c5e13-279">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5e13-279">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="c5e13-280">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-280">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="c5e13-281">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="c5e13-281">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="c5e13-282">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="c5e13-282">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="c5e13-283">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="c5e13-283">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="c5e13-284">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-284">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="c5e13-285">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="c5e13-285">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="c5e13-286">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-286">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="c5e13-287">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5e13-287">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="c5e13-288">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="c5e13-288">Sets the verbosity level.</span></span> <span data-ttu-id="c5e13-289">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-289">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5e13-290">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-290">The default value is `normal`.</span></span>

* <span data-ttu-id="c5e13-291">**`-y, --yes`** Ejecuta el comando sin requerir una confirmación S/N.</span><span class="sxs-lookup"><span data-stu-id="c5e13-291">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="c5e13-292">**`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.</span><span class="sxs-lookup"><span data-stu-id="c5e13-292">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="c5e13-293">Notas:</span><span class="sxs-lookup"><span data-stu-id="c5e13-293">Notes:</span></span>

1. <span data-ttu-id="c5e13-294">Se requiere uno de los valores `--sdk` y `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-294">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="c5e13-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c5e13-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="c5e13-296">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5e13-296">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="c5e13-297">De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK se mantienen.</span><span class="sxs-lookup"><span data-stu-id="c5e13-297">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="c5e13-298">En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados se mantengan, según el estado de la máquina.</span><span class="sxs-lookup"><span data-stu-id="c5e13-298">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="c5e13-299">Para quitar todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-299">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="c5e13-300">Quitar todos los entornos en tiempo de ejecución de .NET Core excepto la versión `3.0.0-preview6-27804-01` sin necesidad de la confirmación S/N:</span><span class="sxs-lookup"><span data-stu-id="c5e13-300">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="c5e13-301">Quitar todos los SDK de .NET Core 1.1 sin necesidad de la confirmación de S/N:</span><span class="sxs-lookup"><span data-stu-id="c5e13-301">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="c5e13-302">Quitar el SDK de .NET Core 1.1.11 sin salida de consola:</span><span class="sxs-lookup"><span data-stu-id="c5e13-302">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="c5e13-303">Quitar todos los SDK de .NET Core que se puedan quitar con seguridad con esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="c5e13-303">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="c5e13-304">Quitar todos los SDK de .NET Core que puede quitar esta herramienta, incluidos los SDK que puede necesitar Visual Studio (no recomendado):</span><span class="sxs-lookup"><span data-stu-id="c5e13-304">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="c5e13-305">Quitar todos los SDK de .NET Core que se especifican en el archivo de respuesta `versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="c5e13-305">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="c5e13-306">El contenido de *versions.rsp* es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5e13-306">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="c5e13-307">Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)</span><span class="sxs-lookup"><span data-stu-id="c5e13-307">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="c5e13-308">En algunos casos, ya no necesita `NuGetFallbackFolder` y puede que desee eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c5e13-308">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="c5e13-309">Para más información sobre cómo eliminar esta carpeta, consulte [Quitar NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="c5e13-309">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="c5e13-310">Desinstalación de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c5e13-310">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="c5e13-311">Windows</span><span class="sxs-lookup"><span data-stu-id="c5e13-311">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="c5e13-312">Abra **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="c5e13-312">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="c5e13-313">Busque `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="c5e13-313">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="c5e13-314">Seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="c5e13-314">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="c5e13-315">macOS</span><span class="sxs-lookup"><span data-stu-id="c5e13-315">macOS</span></span>](#tab/macos)

<span data-ttu-id="c5e13-316">Elimine el archivo *dotnet-Core-Uninstall.tar.gz* descargado del directorio donde se instaló.</span><span class="sxs-lookup"><span data-stu-id="c5e13-316">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="c5e13-317">Si descomprimió el contenido de este archivo en otro directorio, asegúrese de eliminar también dicho contenido.</span><span class="sxs-lookup"><span data-stu-id="c5e13-317">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---

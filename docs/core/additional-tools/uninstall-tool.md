---
title: Herramienta de desinstalación
description: Información general de la herramienta de desinstalación de .NET Core, una herramienta guiada que permite limpiar de forma controlada los SDK y los entornos en tiempo de ejecución de .NET Core.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714551"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="6b9e8-103">Herramienta de desinstalación de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6b9e8-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="6b9e8-104">La [herramienta de desinstalación de .NET Core](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos en tiempo de ejecución de .NET Core de un sistema.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="6b9e8-105">Hay una colección de opciones disponible para especificar las versiones que desea desinstalar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="6b9e8-106">La herramienta es compatible con Windows y macOS.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="6b9e8-107">Linux no se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-107">Linux is currently not supported.</span></span>

<span data-ttu-id="6b9e8-108">En Windows, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución que se instalaron mediante uno de los siguientes instaladores:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="6b9e8-109">El instalador del SDK y del entorno en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="6b9e8-110">El instalador de Visual Studio en versiones anteriores a Visual Studio 2019, versión 16.3.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="6b9e8-111">En macOS, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución ubicados en la carpeta */usr/local/share/dotnet*.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="6b9e8-112">Debido a estas limitaciones, es posible que la herramienta no pueda desinstalar todos los SDK y los entornos en tiempo de ejecución de .NET Core de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="6b9e8-113">Puede usar el comando `dotnet --info` para buscar todos los SDK y los entornos en tiempo de ejecución de .NET Core instalados, incluidos los entornos en tiempo de ejecución y SDK que esta herramienta no puede quitar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="6b9e8-114">El comando `dotnet-core-uninstall list` muestra qué SDK se pueden desinstalar con la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="6b9e8-115">Instalación de la herramienta</span><span class="sxs-lookup"><span data-stu-id="6b9e8-115">Install the tool</span></span>

<span data-ttu-id="6b9e8-116">Puede descargar la herramienta de desinstalación de .NET Core del repositorio de GitHub [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="6b9e8-117">La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="6b9e8-118">Por lo tanto, debe instalarse en un directorio protegido contra escritura, como *C:\Archivos de programa* en Windows o */usr/local/bin* en macOS.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="6b9e8-119">Consulte también [Acceso con privilegios elevados para comandos de dotnet](../tools/elevated-access.md).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="6b9e8-120">Puede encontrar instrucciones de instalación detalladas en la [página de versiones de GitHub](https://github.com/dotnet/cli-lab/releases).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="6b9e8-121">Ejecución de la herramienta</span><span class="sxs-lookup"><span data-stu-id="6b9e8-121">Run the tool</span></span>

<span data-ttu-id="6b9e8-122">En los pasos siguientes se muestra el enfoque recomendado para ejecutar la herramienta de desinstalación:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="6b9e8-123">Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados</span><span class="sxs-lookup"><span data-stu-id="6b9e8-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="6b9e8-124">Paso 2: Realizar un simulacro</span><span class="sxs-lookup"><span data-stu-id="6b9e8-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="6b9e8-125">Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6b9e8-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="6b9e8-126">Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)</span><span class="sxs-lookup"><span data-stu-id="6b9e8-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="6b9e8-127">Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados</span><span class="sxs-lookup"><span data-stu-id="6b9e8-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="6b9e8-128">El comando `dotnet-core-uninstall list` enumera los SDK y los entornos en tiempo de ejecución de .NET Core instalados que se pueden quitar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="6b9e8-129">Visual Studio puede necesitar algunos SDK y entornos en tiempo de ejecución, que se muestran con una nota de por qué no se recomienda desinstalarlos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="6b9e8-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="6b9e8-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="6b9e8-131">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6b9e8-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="6b9e8-132">Opciones</span><span class="sxs-lookup"><span data-stu-id="6b9e8-132">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="6b9e8-133">Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e8-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="6b9e8-134">Enumera todos los entornos en tiempo de ejecución de ASP.NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="6b9e8-135">Enumera todos los entornos en tiempo de ejecución de .NET Core y conjuntos de hospedaje que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="6b9e8-136">Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-137">Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-138">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-138">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-139">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-140">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="6b9e8-141">Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x64 que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="6b9e8-142">Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x86 que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="6b9e8-143">macOS</span><span class="sxs-lookup"><span data-stu-id="6b9e8-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="6b9e8-144">Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-145">Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-146">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-146">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-147">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-148">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="6b9e8-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6b9e8-149">Examples</span></span>

* <span data-ttu-id="6b9e8-150">Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core que se pueden quitar con esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="6b9e8-151">Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core x64:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="6b9e8-152">Enumerar todos los SDK de .NET Core x86:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="6b9e8-153">Paso 2: Realizar un simulacro</span><span class="sxs-lookup"><span data-stu-id="6b9e8-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="6b9e8-154">Los comandos `dotnet-core-uninstall dry-run` y `dotnet-core-uninstall whatif` muestran los SDK y los entornos en tiempo de ejecución de .NET Core que se quitarán en función de las opciones proporcionadas sin realizar la desinstalación.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="6b9e8-155">Estos comandos son sinónimos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-155">These commands are synonyms.</span></span>

<span data-ttu-id="6b9e8-156">**dotnet-core-uninstall dry-run y dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="6b9e8-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="6b9e8-157">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6b9e8-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="6b9e8-158">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b9e8-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="6b9e8-159">La versión especificada que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-159">The specified version to uninstall.</span></span> <span data-ttu-id="6b9e8-160">Puede enumerar varias versiones una detrás de la otra, separadas por espacios.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="6b9e8-161">También se admiten los archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="6b9e8-162">Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="6b9e8-163">Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="6b9e8-164">Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="6b9e8-165">Opciones</span><span class="sxs-lookup"><span data-stu-id="6b9e8-165">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="6b9e8-166">Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e8-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="6b9e8-167">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="6b9e8-168">Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="6b9e8-169">La versión especificada permanece instalada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="6b9e8-170">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="6b9e8-171">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="6b9e8-172">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="6b9e8-173">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="6b9e8-174">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="6b9e8-175">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="6b9e8-176">Solo quita los entornos en tiempos de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="6b9e8-177">Quita el entorno en tiempo de ejecución de .NET Core y los conjuntos de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="6b9e8-178">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="6b9e8-179">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-180">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-181">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-181">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-182">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-183">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="6b9e8-184">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="6b9e8-185">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="6b9e8-186">**`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="6b9e8-187">Notas:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-187">Notes:</span></span>

1. <span data-ttu-id="6b9e8-188">Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="6b9e8-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="6b9e8-190">Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="6b9e8-191">macOS</span><span class="sxs-lookup"><span data-stu-id="6b9e8-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="6b9e8-192">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="6b9e8-193">Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="6b9e8-194">La versión especificada se conservará.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="6b9e8-195">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="6b9e8-196">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="6b9e8-197">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="6b9e8-198">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="6b9e8-199">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="6b9e8-200">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="6b9e8-201">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="6b9e8-202">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-203">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-204">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-204">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-205">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-206">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="6b9e8-207">**`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="6b9e8-208">Notas:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-208">Notes:</span></span>

1. <span data-ttu-id="6b9e8-209">Se requiere uno de los valores `--sdk` y `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="6b9e8-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="6b9e8-211">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6b9e8-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="6b9e8-212">De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK no se incluyen en la salida de `dotnet-core-uninstall dry-run`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="6b9e8-213">En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados no se incluyan en la salida, según el estado de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="6b9e8-214">Para incluir todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="6b9e8-215">Realizar un simulacro de la eliminación de todos entornos en tiempo de ejecución de .NET Core que se han reemplazado por revisiones superiores:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="6b9e8-216">Realizar un simulacro de la eliminación de todos los SDK de .NET Core inferiores a la versión `2.2.301`:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="6b9e8-217">Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6b9e8-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="6b9e8-218">`dotnet-core-uninstall remove` desinstala los SDK y los entornos en tiempo de ejecución de .NET Core especificados por una colección de opciones.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="6b9e8-219">La herramienta no se puede usar para desinstalar los SDK y entornos en tiempo de ejecución con la versión 5.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="6b9e8-220">Dado que esta herramienta tiene un comportamiento destructivo, es **altamente** recomendable que realice un simulacro antes de ejecutar el comando remove.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="6b9e8-221">El simulacro le mostrará qué SDK y entornos en tiempo de ejecución de .NET Core se quitarán cuando use el comando `remove`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="6b9e8-222">Consulte [¿Puedo quitar una versión?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) para saber qué SDK y entornos en tiempo de ejecución se pueden quitar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="6b9e8-223">Tenga en cuenta las siguientes advertencias:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="6b9e8-224">Esta herramienta puede desinstalar las versiones del SDK de .NET Core que necesitan los archivos `global.json` de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="6b9e8-225">Puede volver a instalar los SDK de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="6b9e8-226">Esta herramienta puede desinstalar las versiones del entorno en tiempo de ejecución de .NET Core que necesitan las aplicaciones que dependen del marco de trabajo de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="6b9e8-227">Puede volver a instalar los entornos en tiempo de ejecución de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="6b9e8-228">Esta herramienta puede desinstalar las versiones del SDK y del entorno en tiempo de ejecución de .NET Core en las que se basa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="6b9e8-229">Si interrumpe la instalación de Visual Studio, ejecute "Reparar" en el instalador de Visual Studio para volver a un estado de funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="6b9e8-230">De forma predeterminada, todos los comandos mantienen los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="6b9e8-231">Estos SDK y entornos en tiempos de ejecución se pueden desinstalar si se enumeran explícitamente como argumentos o mediante la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="6b9e8-232">La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="6b9e8-233">Ejecute la herramienta en un símbolo del sistema de administrador en Windows y con `sudo` en macOS.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="6b9e8-234">Los comandos `dry-run` y `whatif` no requieren elevación.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="6b9e8-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="6b9e8-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="6b9e8-236">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6b9e8-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="6b9e8-237">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b9e8-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="6b9e8-238">La versión especificada que se va a desinstalar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-238">The specified version to uninstall.</span></span> <span data-ttu-id="6b9e8-239">Puede enumerar varias versiones una detrás de la otra, separadas por espacios.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="6b9e8-240">También se admiten los archivos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="6b9e8-241">Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="6b9e8-242">Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="6b9e8-243">Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="6b9e8-244">Opciones</span><span class="sxs-lookup"><span data-stu-id="6b9e8-244">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="6b9e8-245">Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e8-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="6b9e8-246">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="6b9e8-247">Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="6b9e8-248">La versión especificada permanece instalada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="6b9e8-249">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="6b9e8-250">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="6b9e8-251">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="6b9e8-252">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="6b9e8-253">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="6b9e8-254">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="6b9e8-255">Solo quita los entornos en tiempos de ejecución de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="6b9e8-256">Quita el entorno en tiempo de ejecución de .NET Core y los conjuntos de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="6b9e8-257">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="6b9e8-258">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-259">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-260">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-260">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-261">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-262">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="6b9e8-263">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="6b9e8-264">Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="6b9e8-265">**`-y, --yes`** Ejecuta el comando sin requerir una confirmación sí o no.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="6b9e8-266">**`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="6b9e8-267">Notas:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-267">Notes:</span></span>

1. <span data-ttu-id="6b9e8-268">Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="6b9e8-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="6b9e8-270">Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="6b9e8-271">macOS</span><span class="sxs-lookup"><span data-stu-id="6b9e8-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="6b9e8-272">Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="6b9e8-273">Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="6b9e8-274">La versión especificada se conservará.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="6b9e8-275">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="6b9e8-276">Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="6b9e8-277">Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="6b9e8-278">Esta opción protege el archivo global.json.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="6b9e8-279">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="6b9e8-280">Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="6b9e8-281">Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="6b9e8-282">Solo quita los entornos en tiempo de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="6b9e8-283">Solo quita los SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="6b9e8-284">Establece el nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-284">Sets the verbosity level.</span></span> <span data-ttu-id="6b9e8-285">Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6b9e8-286">El valor predeterminado es `normal`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-286">The default value is `normal`.</span></span>

* <span data-ttu-id="6b9e8-287">**`-y, --yes`** Ejecuta el comando sin requerir una confirmación S/N.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="6b9e8-288">**`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="6b9e8-289">Notas:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-289">Notes:</span></span>

1. <span data-ttu-id="6b9e8-290">Se requiere uno de los valores `--sdk` y `--runtime`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="6b9e8-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="6b9e8-292">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6b9e8-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="6b9e8-293">De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK se mantienen.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="6b9e8-294">En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados se mantengan, según el estado de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="6b9e8-295">Para quitar todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="6b9e8-296">Quitar todos los entornos en tiempo de ejecución de .NET Core excepto la versión `3.0.0-preview6-27804-01` sin necesidad de la confirmación S/N:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="6b9e8-297">Quitar todos los SDK de .NET Core 1.1 sin necesidad de la confirmación de S/N:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="6b9e8-298">Quitar el SDK de .NET Core 1.1.11 sin salida de consola:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="6b9e8-299">Quitar todos los SDK de .NET Core que se puedan quitar con seguridad con esta herramienta:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="6b9e8-300">Quitar todos los SDK de .NET Core que puede quitar esta herramienta, incluidos los SDK que puede necesitar Visual Studio (no recomendado):</span><span class="sxs-lookup"><span data-stu-id="6b9e8-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="6b9e8-301">Quitar todos los SDK de .NET Core que se especifican en el archivo de respuesta `versions.rsp`</span><span class="sxs-lookup"><span data-stu-id="6b9e8-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="6b9e8-302">El contenido de *versions.rsp* es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b9e8-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="6b9e8-303">Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)</span><span class="sxs-lookup"><span data-stu-id="6b9e8-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="6b9e8-304">En algunos casos, ya no necesita `NuGetFallbackFolder` y puede que desee eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="6b9e8-305">Para más información sobre cómo eliminar esta carpeta, consulte [Quitar NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span><span class="sxs-lookup"><span data-stu-id="6b9e8-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="6b9e8-306">Desinstalación de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-306">Uninstall the tool</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="6b9e8-307">Windows</span><span class="sxs-lookup"><span data-stu-id="6b9e8-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="6b9e8-308">Abra **Agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="6b9e8-309">Busque `Microsoft .NET Core SDK Uninstall Tool`.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="6b9e8-310">Seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-310">Select **Uninstall**.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="6b9e8-311">macOS</span><span class="sxs-lookup"><span data-stu-id="6b9e8-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="6b9e8-312">Elimine el archivo *dotnet-Core-Uninstall.tar.gz* descargado del directorio donde se instaló.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="6b9e8-313">Si descomprimió el contenido de este archivo en otro directorio, asegúrese de eliminar también dicho contenido.</span><span class="sxs-lookup"><span data-stu-id="6b9e8-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---

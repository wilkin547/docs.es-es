---
title: 'Herramienta de diagnóstico dotnet-symbol: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-symbol para descargar los archivos necesarios para depurar minivolcados y volcados de memoria de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 4543bd965c889d93d7dc0b89ff2d6f62c4343e5f
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103189909"
---
# <a name="symbol-downloader-dotnet-symbol"></a><span data-ttu-id="5a244-103">Aplicación de descarga de símbolos (dotnet-symbol)</span><span class="sxs-lookup"><span data-stu-id="5a244-103">Symbol downloader (dotnet-symbol)</span></span>

<span data-ttu-id="5a244-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5a244-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="5a244-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="5a244-105">Install</span></span>

<span data-ttu-id="5a244-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-symbol) de `dotnet-symbol`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="5a244-106">To install the latest release version of the `dotnet-symbol` [NuGet package](https://www.nuget.org/packages/dotnet-symbol), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a><span data-ttu-id="5a244-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5a244-107">Synopsis</span></span>

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a><span data-ttu-id="5a244-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a244-108">Description</span></span>

<span data-ttu-id="5a244-109">La herramienta global `dotnet-symbol` descarga archivos (símbolos, paquetes DAC, módulos, etc.) que son necesarios para la depuración de volcados y minivolcados de núcleo.</span><span class="sxs-lookup"><span data-stu-id="5a244-109">The `dotnet-symbol` global tool downloads files (symbols, DAC, modules, etc.) needed for debugging core dumps and minidumps.</span></span> <span data-ttu-id="5a244-110">Esto puede ser útil al depurar volcados de memoria capturados en otra máquina.</span><span class="sxs-lookup"><span data-stu-id="5a244-110">This can be useful when debugging dumps captured on another machine.</span></span> <span data-ttu-id="5a244-111">`dotnet-symbol` puede descargar los módulos y símbolos necesarios para analizar el volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="5a244-111">`dotnet-symbol` can download modules and symbols needed to analyze the dump.</span></span>

## <a name="options"></a><span data-ttu-id="5a244-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="5a244-112">Options</span></span>

- **`--microsoft-symbol-server`**

  <span data-ttu-id="5a244-113">Agrega la ruta de acceso del servidor de símbolos "http://msdl.microsoft.com/download/symbols" (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="5a244-113">Add 'http://msdl.microsoft.com/download/symbols' symbol server path (default).</span></span>

- **`--server-path <symbol server path>`**

  <span data-ttu-id="5a244-114">Agrega un servidor de símbolos a la ruta de acceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="5a244-114">Add a symbol server to the server path.</span></span>

- **`authenticated-server-path <pat> <server path>`**

  <span data-ttu-id="5a244-115">Agrega un servidor de símbolos autenticado a la ruta de acceso del servidor mediante un token de acceso personal (PAT).</span><span class="sxs-lookup"><span data-stu-id="5a244-115">Add an authenticated symbol server to the server path using a personal access token (PAT).</span></span>

- **`--cache-directory <file cache directory>`**

  <span data-ttu-id="5a244-116">Agrega un directorio de caché.</span><span class="sxs-lookup"><span data-stu-id="5a244-116">Adds a cache directory.</span></span>

- **`--recurse-subdirectories`**

  <span data-ttu-id="5a244-117">Procesa archivos de entrada en todos los subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="5a244-117">Process input files in all subdirectories.</span></span>

- **`--host-only`**

  <span data-ttu-id="5a244-118">Descarga solo el programa host (es decir, dotnet) que necesita lldb para cargar volcados de núcleo.</span><span class="sxs-lookup"><span data-stu-id="5a244-118">Download only the host program (that is, dotnet) that lldb needs for loading core dumps.</span></span>

- **`--symbols`**

  <span data-ttu-id="5a244-119">Descarga archivos de símbolos (.pdb, .dbg, .dwarf).</span><span class="sxs-lookup"><span data-stu-id="5a244-119">Download symbol files (.pdb, .dbg, .dwarf).</span></span>

- **`--modules`**

  <span data-ttu-id="5a244-120">Descarga archivos de módulo (.dll, .so, .dylib).</span><span class="sxs-lookup"><span data-stu-id="5a244-120">Download the module files (.dll, .so, .dylib).</span></span>

- **`--debugging`**

  <span data-ttu-id="5a244-121">Descarga módulos de depuración especiales (DAC, DBI, SOS).</span><span class="sxs-lookup"><span data-stu-id="5a244-121">Download the special debugging modules (DAC, DBI, SOS).</span></span>

- **`--windows-pdbs`**

  <span data-ttu-id="5a244-122">Fuerza la descarga de los archivos PDB de Windows cuando también hay archivos PDB portátiles disponibles.</span><span class="sxs-lookup"><span data-stu-id="5a244-122">Force the downloading of the Windows PDBs when Portable PDBs are also available.</span></span>

- **`-o, --output <output directory>`**

  <span data-ttu-id="5a244-123">Establece el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5a244-123">Set the output directory.</span></span> <span data-ttu-id="5a244-124">De lo contrario, escribe "next" en el archivo de entrada (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="5a244-124">Otherwise, write next to the input file (default).</span></span>

- **`-d, --diagnostics`**

  <span data-ttu-id="5a244-125">Habilita la salida de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="5a244-125">Enable diagnostic output.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5a244-126">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5a244-126">Shows command-line help.</span></span>

## <a name="download-symbols"></a><span data-ttu-id="5a244-127">Descargar símbolos</span><span class="sxs-lookup"><span data-stu-id="5a244-127">Download symbols</span></span>

<span data-ttu-id="5a244-128">De forma predeterminada, al ejecutar `dotnet-symbol` en un archivo de volcado de memoria, se descargan todos los módulos, símbolos y archivos DAC/DBI necesarios para depurar el volcado, incluidos los ensamblados administrados.</span><span class="sxs-lookup"><span data-stu-id="5a244-128">Running `dotnet-symbol` against a dump file will, by default, download all the modules, symbols, and DAC/DBI files needed to debug the dump including the managed assemblies.</span></span> <span data-ttu-id="5a244-129">Dado que SOS ahora puede descargar símbolos cuando sea necesario, la mayoría de los volcados de núcleo de Linux se pueden analizar mediante lldb solo con los módulos host (dotnet) y de depuración.</span><span class="sxs-lookup"><span data-stu-id="5a244-129">Because SOS can now download symbols when needed, most Linux core dumps can be analyzed using lldb with only the host (dotnet) and debugging modules.</span></span> <span data-ttu-id="5a244-130">Para obtener estos archivos necesarios para diagnosticar un volcado de memoria con lldb, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a244-130">To get these files necessary for diagnosing a core dump with lldb run:</span></span>

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a><span data-ttu-id="5a244-131">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5a244-131">Troubleshoot</span></span>

- <span data-ttu-id="5a244-132">Error "404 No encontrado" al descargar símbolos.</span><span class="sxs-lookup"><span data-stu-id="5a244-132">404 Not Found while downloading symbols.</span></span>

   <span data-ttu-id="5a244-133">La descarga de símbolos solo se admite para las versiones oficiales del entorno de ejecución de .NET Core adquiridas a través de canales oficiales como el [sitio web oficial](https://dotnet.microsoft.com/download/dotnet) y los [orígenes predeterminados en los scripts de instalación de dotnet](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="5a244-133">Symbol download is only supported for official .NET Core runtime versions acquired through official channels such as [the official web site](https://dotnet.microsoft.com/download/dotnet) and the [default sources in the dotnet installation scripts](../tools/dotnet-install-script.md).</span></span> <span data-ttu-id="5a244-134">Un error 404 al descargar archivos de depuración puede indicar que el volcado de memoria se ha creado con un entorno de ejecución de .NET Core desde otro origen, como uno compilado localmente desde el origen o para una distribución concreta de Linux, o bien desde sitios de la comunidad como archlinux.</span><span class="sxs-lookup"><span data-stu-id="5a244-134">A 404 error while downloading debugging files may indicate that the dump was created with a .NET Core runtime from another source, such as one built from source locally or for a particular Linux distro, or from community sites like archlinux.</span></span> <span data-ttu-id="5a244-135">En estos casos, el archivo necesario para la depuración (dotnet, libcoreclr.so y libmscordaccore.so) se debe copiar desde esos orígenes o desde el entorno en el que se creó el archivo de volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="5a244-135">In such cases, file necessary for debugging (dotnet, libcoreclr.so, and libmscordaccore.so) should be copied from those sources or from the environment the dump file was created in.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a244-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a244-136">See also</span></span>

* [<span data-ttu-id="5a244-137">Depuración con símbolos</span><span class="sxs-lookup"><span data-stu-id="5a244-137">Debugging with symbols</span></span>](/windows/win32/dxtecharts/debugging-with-symbols)
* [<span data-ttu-id="5a244-138">Símbolos y archivos PDB portátiles</span><span class="sxs-lookup"><span data-stu-id="5a244-138">Symbols and Portable PDBs</span></span>](./symbols.md)

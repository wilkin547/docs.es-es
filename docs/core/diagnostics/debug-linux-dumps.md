---
title: Depuración de volcados de memoria de Linux
description: En este artículo, aprenderá a recopilar y analizar volcados de memoria desde entornos de Linux.
ms.date: 08/27/2020
ms.openlocfilehash: 42038c685c3ad0043c91df140b0133a9ddecec3b
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874280"
---
# <a name="debug-linux-dumps"></a><span data-ttu-id="24196-103">Depuración de volcados de memoria de Linux</span><span class="sxs-lookup"><span data-stu-id="24196-103">Debug Linux dumps</span></span>

<span data-ttu-id="24196-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="24196-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

## <a name="collect-dumps-on-linux"></a><span data-ttu-id="24196-105">Recopilación de volcados de memoria en Linux</span><span class="sxs-lookup"><span data-stu-id="24196-105">Collect dumps on Linux</span></span>

<span data-ttu-id="24196-106">Las dos formas recomendadas de recopilar volcados en Linux son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="24196-106">The two recommended ways of collecting dumps on Linux are:</span></span>

* <span data-ttu-id="24196-107">Herramienta de la CLI [`dotnet-dump`](dotnet-dump.md)</span><span class="sxs-lookup"><span data-stu-id="24196-107">[`dotnet-dump`](dotnet-dump.md) CLI tool</span></span>
* <span data-ttu-id="24196-108">[Variables de entorno](dumps.md#collecting-dumps-on-crash) que recopilan volcados de memoria al producirse bloqueos</span><span class="sxs-lookup"><span data-stu-id="24196-108">[Environment variables](dumps.md#collecting-dumps-on-crash) that collect dumps on crashes</span></span>

### <a name="managed-dumps-with-dotnet-dump"></a><span data-ttu-id="24196-109">Volcados administrados con `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="24196-109">Managed dumps with `dotnet-dump`</span></span>

<span data-ttu-id="24196-110">La herramienta [`dotnet-dump`](dotnet-dump.md) es fácil de usar y no depende de ningún depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="24196-110">The [`dotnet-dump`](dotnet-dump.md) tool is simple to use, and does not have a dependency on any native debuggers.</span></span> <span data-ttu-id="24196-111">`dotnet-dump` funciona en una amplia variedad de plataformas Linux (como Alpine o ARM32/ARM64) donde las herramientas tradicionales de depuración pueden no estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="24196-111">`dotnet-dump` works on a wide variety of Linux platforms (like Alpine or ARM32/ARM64) where traditional debugging tools may not be available.</span></span> <span data-ttu-id="24196-112">Pero `dotnet-dump` solo captura el estado administrado, por lo que no se puede usar para la depuración de problemas en código nativo.</span><span class="sxs-lookup"><span data-stu-id="24196-112">However, `dotnet-dump` only captures managed state so it can't be used for debugging issues in native code.</span></span> <span data-ttu-id="24196-113">Los volcados de memoria recopilados por `dotnet-dump` se analizan en un entorno con el mismo sistema operativo y la misma arquitectura con los que se ha creado el volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="24196-113">Dumps collected by `dotnet-dump` are analyzed in an environment with the same OS and architecture the dump was created on.</span></span> <span data-ttu-id="24196-114">La herramienta [`dotnet-gcdump`](dotnet-gcdump.md) se puede usar como alternativa, ya que solo captura información del montón de recolección de elementos no utilizados (GC), pero genera volcados que se puedan analizar en Windows.</span><span class="sxs-lookup"><span data-stu-id="24196-114">The [`dotnet-gcdump`](dotnet-gcdump.md) tool can be used as an alternative that only captures GC heap information but produces dumps that can be analyzed on Windows.</span></span>

### <a name="core-dumps-with-createdump"></a><span data-ttu-id="24196-115">Volcados de núcleo con `createdump`</span><span class="sxs-lookup"><span data-stu-id="24196-115">Core dumps with `createdump`</span></span>

<span data-ttu-id="24196-116">Como alternativa a `dotnet-dump`, que crea volcados solo de información administrada, [`createdump`](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/botr/xplat-minidump-generation.md) es la herramienta recomendada para crear volcados de núcleo en Linux que contienen tanto información nativa como administrada.</span><span class="sxs-lookup"><span data-stu-id="24196-116">As an alternative to `dotnet-dump`, which creates managed-only dumps, [`createdump`](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/botr/xplat-minidump-generation.md) is the recommended tool for creating core dumps on Linux containing both native and managed information.</span></span> <span data-ttu-id="24196-117">También se pueden usar otras herramientas como gdb o gcore para crear volcados de núcleo, pero puede omitir el estado necesario para la depuración administrada, lo que puede dar lugar a nombres de función o de tipo desconocidos durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="24196-117">Other tools like gdb or gcore can also be used to create core dumps but may miss state needed for managed debugging, resulting in "UNKNOWN" type or function names during analysis.</span></span>

<span data-ttu-id="24196-118">La herramienta `createdump` se instala con el entorno de ejecución de .NET y se puede encontrar junto a libcoreclr.so (normalmente en "/usr/share/dotnet/shared/Microsoft.NETCore.App/[versión]").</span><span class="sxs-lookup"><span data-stu-id="24196-118">The `createdump` tool is installed with the .NET Core runtime and can be found next to libcoreclr.so (typically in "/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]").</span></span> <span data-ttu-id="24196-119">Esta herramienta toma un identificador de proceso para recopilar un volcado de su argumento principal, y también puede tomar parámetros opcionales que especifican el tipo de volcado que se va a recopilar (el valor predeterminado es un minivolcado con montón).</span><span class="sxs-lookup"><span data-stu-id="24196-119">The tool takes a process ID to collect a dump from as its primary argument and can also take optional parameters specifying what kind of dump to collect (a minidump with heap is the default).</span></span> <span data-ttu-id="24196-120">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="24196-120">Options include:</span></span>

- **`<input-filename>`**

  <span data-ttu-id="24196-121">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="24196-121">Input trace file to be converted.</span></span> <span data-ttu-id="24196-122">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="24196-122">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="24196-123">Opciones</span><span class="sxs-lookup"><span data-stu-id="24196-123">Options</span></span>

- **`-f|--name <output-filename>`**

  <span data-ttu-id="24196-124">Archivo en el que se escribirá el volcado.</span><span class="sxs-lookup"><span data-stu-id="24196-124">The file to write the dump to.</span></span> <span data-ttu-id="24196-125">El valor predeterminado es "/tmp/coredump.%p", donde "%p" es el identificador del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="24196-125">Default is '/tmp/coredump.%p' where %p is the process ID of the target process.</span></span>

- **`-n|--normal`**

  <span data-ttu-id="24196-126">Creación de un minivolcado.</span><span class="sxs-lookup"><span data-stu-id="24196-126">Create a minidump.</span></span>

- **`-h|--withheap`**

  <span data-ttu-id="24196-127">Creación de un minivolcado con montón (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="24196-127">Create a minidump with heap (default).</span></span>

- **`-t|--triage`**

  <span data-ttu-id="24196-128">Creación de un minivolcado de evaluación de prioridades.</span><span class="sxs-lookup"><span data-stu-id="24196-128">Create a triage minidump.</span></span>

- **`-u|--full`**

  <span data-ttu-id="24196-129">Creación de un volcado de núcleo completo.</span><span class="sxs-lookup"><span data-stu-id="24196-129">Create a full core dump.</span></span>

- **`-d|--diag`**

  <span data-ttu-id="24196-130">Habilitación de mensajes de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="24196-130">Enable diagnostic messages.</span></span>

<span data-ttu-id="24196-131">La recopilación de volcados de núcleo requiere la capacidad `SYS_PTRACE` o la ejecución de `createdump` con sudo o su.</span><span class="sxs-lookup"><span data-stu-id="24196-131">Collecting core dumps requires either the `SYS_PTRACE` capability or that `createdump` be run with sudo or su.</span></span>

## <a name="analyze-dumps-on-linux"></a><span data-ttu-id="24196-132">Análisis de volcados de memoria en Linux</span><span class="sxs-lookup"><span data-stu-id="24196-132">Analyze dumps on Linux</span></span>

<span data-ttu-id="24196-133">Los volcados de memoria recopilados con `dotnet-dump` y los volcados de núcleo recopilados con `createdump` se pueden analizar con la herramienta `dotnet-dump` mediante el comando `dotnet-dump analyze`.</span><span class="sxs-lookup"><span data-stu-id="24196-133">Both managed dumps collected with `dotnet-dump` and core dumps collected with `createdump` can be analyzed with the `dotnet-dump` tool using the `dotnet-dump analyze` command.</span></span> <span data-ttu-id="24196-134">`dotnet dump` requiere que el entorno que analiza el volcado tenga el mismo sistema operativo y la misma arquitectura que el entorno en el que se capturó el volcado.</span><span class="sxs-lookup"><span data-stu-id="24196-134">The `dotnet dump` requires that the environment analyzing the dump has the same OS and architecture as the environment the dump was captured in.</span></span>

<span data-ttu-id="24196-135">Como alternativa, se puede usar [LLDB](https://lldb.llvm.org/) para analizar los volcados de núcleo en Linux, ya que permite el análisis de marcos administrados y nativos.</span><span class="sxs-lookup"><span data-stu-id="24196-135">Alternatively, [LLDB](https://lldb.llvm.org/) can be used to analyze core dumps on Linux, which allows analysis of both managed and native frames.</span></span> <span data-ttu-id="24196-136">LLDB usa la extensión SOS para depurar el código administrado.</span><span class="sxs-lookup"><span data-stu-id="24196-136">LLDB uses the SOS extension to debug managed code.</span></span> <span data-ttu-id="24196-137">La herramienta de la CLI [`dotnet-sos`](dotnet-sos.md) se puede usar para instalar SOS, que tiene [muchos comandos útiles](https://github.com/dotnet/diagnostics/blob/main/documentation/sos-debugging-extension.md) para depurar código administrado.</span><span class="sxs-lookup"><span data-stu-id="24196-137">The [`dotnet-sos`](dotnet-sos.md) CLI tool can be used to install SOS, which has [many useful commands](https://github.com/dotnet/diagnostics/blob/main/documentation/sos-debugging-extension.md) for debugging managed code.</span></span> <span data-ttu-id="24196-138">Para poder analizar los volcados de .NET Core, LLDB y SOS requieren los siguientes archivos binarios de .NET Core del entorno en el que se creó el volcado:</span><span class="sxs-lookup"><span data-stu-id="24196-138">In order to analyze .NET Core dumps, LLDB and SOS require the following .NET Core binaries from the environment the dump was created in:</span></span>

1. <span data-ttu-id="24196-139">libmscordaccore.so</span><span class="sxs-lookup"><span data-stu-id="24196-139">libmscordaccore.so</span></span>
2. <span data-ttu-id="24196-140">libcoreclr.so</span><span class="sxs-lookup"><span data-stu-id="24196-140">libcoreclr.so</span></span>
3. <span data-ttu-id="24196-141">dotnet (host usado para iniciar la aplicación)</span><span class="sxs-lookup"><span data-stu-id="24196-141">dotnet (the host used to launch the app)</span></span>

<span data-ttu-id="24196-142">En la mayoría de los casos, estos archivos binarios se pueden descargar mediante la herramienta [`dotnet-symbol`](dotnet-symbol.md).</span><span class="sxs-lookup"><span data-stu-id="24196-142">In most cases, these binaries can be downloaded using the [`dotnet-symbol`](dotnet-symbol.md) tool.</span></span> <span data-ttu-id="24196-143">Si no se pueden descargar los archivos binarios necesarios con `dotnet-symbol` (por ejemplo, si está en uso una versión privada de .NET Core creada a partir de un origen), puede que sea necesario copiar los archivos enumerados anteriormente desde el entorno en el que se creó el volcado.</span><span class="sxs-lookup"><span data-stu-id="24196-143">If the necessary binaries can't be downloaded with `dotnet-symbol` (for example, if a private version of .NET Core built from source was in use), it may be necessary to copy the files listed above from the environment the dump was created in.</span></span> <span data-ttu-id="24196-144">Si los archivos no se encuentran junto al archivo de volcado de memoria, puede usar el comando `setclrpath <path>` de LLDB/SOS para establecer la ruta de acceso desde la que se deben cargar, y `setsymbolserver -directory <path>` para establecer la ruta de acceso de los archivos de símbolos.</span><span class="sxs-lookup"><span data-stu-id="24196-144">If the files aren't located next to the dump file, you can use the LLDB/SOS command `setclrpath <path>` to set the path they should be loaded from and `setsymbolserver -directory <path>` to set the path to look in for symbol files.</span></span>

<span data-ttu-id="24196-145">Una vez que están disponibles los archivos necesarios, el volcado de memoria se puede cargar en LLDB especificando el host de dotnet como el ejecutable que se va a depurar:</span><span class="sxs-lookup"><span data-stu-id="24196-145">Once the necessary files are available, the dump can be loaded in LLDB by specifying the dotnet host as the executable to debug:</span></span>

```console
lldb --core <dump-file> <host-program>
```

<span data-ttu-id="24196-146">En la línea de comandos anterior, `<dump-file>` es la ruta de acceso del volcado que se va a analizar y `<host-program>` es el programa nativo que inició la aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="24196-146">In the above command line, `<dump-file>` is the path of the dump to analyze and `<host-program>` is the native program that started the .NET Core application.</span></span> <span data-ttu-id="24196-147">Este suele ser el archivo binario `dotnet`, a menos que la aplicación sea independiente, en cuyo caso es el nombre de la aplicación sin la extensión .dll.</span><span class="sxs-lookup"><span data-stu-id="24196-147">This is typically the `dotnet` binary unless the app is self-contained, in which case it is the name of the application without the dll extension.</span></span>

<span data-ttu-id="24196-148">Una vez que se inicia LLDB, puede que sea necesario usar el comando `setsymbolserver` para apuntar a la ubicación de los símbolos correcta (`setsymbolserver -ms` para usar el servidor de símbolos de Microsoft o `setsymbolserver -directory <path>` para especificar una ruta de acceso local).</span><span class="sxs-lookup"><span data-stu-id="24196-148">Once LLDB starts, it may be necessary to use the `setsymbolserver` command to point at the correct symbol location (`setsymbolserver -ms` to use Microsoft's symbol server or `setsymbolserver -directory <path>` to specify a local path).</span></span> <span data-ttu-id="24196-149">Los símbolos nativos se pueden cargar mediante la ejecución de `loadsymbols`.</span><span class="sxs-lookup"><span data-stu-id="24196-149">Native symbols can be loaded by running `loadsymbols`.</span></span> <span data-ttu-id="24196-150">En este punto, se pueden usar [comandos SOS](https://github.com/dotnet/diagnostics/blob/main/documentation/sos-debugging-extension.md) para analizar el volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="24196-150">At this point, [SOS commands](https://github.com/dotnet/diagnostics/blob/main/documentation/sos-debugging-extension.md) can be used to analyze the dump.</span></span>

## <a name="see-also"></a><span data-ttu-id="24196-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24196-151">See also</span></span>

- <span data-ttu-id="24196-152">[dotnet-sos](dotnet-sos.md) para obtener más información sobre la instalación de la extensión SOS.</span><span class="sxs-lookup"><span data-stu-id="24196-152">[dotnet-sos](dotnet-sos.md) for more details on installing the SOS extension.</span></span>
- <span data-ttu-id="24196-153">[dotnet-symbol](dotnet-symbol.md) para obtener más información sobre la instalación y el uso de la herramienta de descarga de símbolos.</span><span class="sxs-lookup"><span data-stu-id="24196-153">[dotnet-symbol](dotnet-symbol.md) for more details on installing and using the symbol download tool.</span></span>
- <span data-ttu-id="24196-154">[Repositorio de diagnósticos de .NET Core](https://github.com/dotnet/diagnostics/blob/main/documentation/) para obtener más información sobre la depuración, incluidas las preguntas más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="24196-154">[.NET Core diagnostics repo](https://github.com/dotnet/diagnostics/blob/main/documentation/) for more details on debugging, including a useful FAQ.</span></span>
- <span data-ttu-id="24196-155">[Instalación de LLDB](https://github.com/dotnet/diagnostics/blob/main/documentation/sos.md#getting-lldb) para obtener instrucciones sobre la instalación de LLDB en Linux o Mac.</span><span class="sxs-lookup"><span data-stu-id="24196-155">[Installing LLDB](https://github.com/dotnet/diagnostics/blob/main/documentation/sos.md#getting-lldb) for instructions on installing LLDB on Linux or Mac.</span></span>

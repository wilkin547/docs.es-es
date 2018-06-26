---
title: 'Comando dotnet nuget push: CLI de .NET Core'
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: 8a64f9cdc11d03bed82a132265c3b4e1de290807
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728581"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="6aa1d-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6aa1d-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6aa1d-104">nombre</span><span class="sxs-lookup"><span data-stu-id="6aa1d-104">Name</span></span>

<span data-ttu-id="6aa1d-105">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6aa1d-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6aa1d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6aa1d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6aa1d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6aa1d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6aa1d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6aa1d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6aa1d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="6aa1d-110">Description</span><span class="sxs-lookup"><span data-stu-id="6aa1d-110">Description</span></span>

<span data-ttu-id="6aa1d-111">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="6aa1d-112">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="6aa1d-113">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="6aa1d-114">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="6aa1d-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6aa1d-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="6aa1d-116">Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="6aa1d-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="6aa1d-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6aa1d-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6aa1d-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="6aa1d-119">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="6aa1d-120">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="6aa1d-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="6aa1d-122">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="6aa1d-123">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="6aa1d-124">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="6aa1d-125">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-125">Specifies the server URL.</span></span> <span data-ttu-id="6aa1d-126">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="6aa1d-127">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="6aa1d-128">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="6aa1d-129">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6aa1d-130">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6aa1d-131">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6aa1d-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6aa1d-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="6aa1d-133">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="6aa1d-134">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="6aa1d-135">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="6aa1d-136">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="6aa1d-137">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="6aa1d-138">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-138">Specifies the server URL.</span></span> <span data-ttu-id="6aa1d-139">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="6aa1d-140">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="6aa1d-141">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="6aa1d-142">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6aa1d-143">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6aa1d-144">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6aa1d-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6aa1d-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="6aa1d-146">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="6aa1d-147">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="6aa1d-148">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="6aa1d-149">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="6aa1d-150">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="6aa1d-151">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-151">Specifies the server URL.</span></span> <span data-ttu-id="6aa1d-152">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="6aa1d-153">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="6aa1d-154">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="6aa1d-155">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="6aa1d-156">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="6aa1d-157">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="6aa1d-158">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6aa1d-158">Examples</span></span>

<span data-ttu-id="6aa1d-159">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="6aa1d-160">Inserta *foo.nupkg* en el origen de inserción personalizado `http://customsource`, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="6aa1d-161">Inserta *foo.nupkg* en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="6aa1d-162">Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="6aa1d-163">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="6aa1d-164">Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="6aa1d-165">Inserta todos los archivos *.nupkg* del directorio actual en el origen de inserción predeterminado, y especifica un archivo de configuración personalizado *./config/My.Config*:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-165">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

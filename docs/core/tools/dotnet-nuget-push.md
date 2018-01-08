---
title: 'Comando dotnet nuget push: CLI de .NET Core'
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 52aac5ff1862397616287a77eac063582703d509
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="9132f-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="9132f-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9132f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="9132f-104">Name</span></span>

<span data-ttu-id="9132f-105">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="9132f-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9132f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9132f-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="9132f-107">Description</span><span class="sxs-lookup"><span data-stu-id="9132f-107">Description</span></span>

<span data-ttu-id="9132f-108">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="9132f-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="9132f-109">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="9132f-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="9132f-110">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="9132f-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="9132f-111">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9132f-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="9132f-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9132f-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="9132f-113">Especifica la ruta de acceso al paquete y su clave de API para insertar el paquete en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9132f-113">Specify the path to the package and your API key to push the package to the server.</span></span>

## <a name="options"></a><span data-ttu-id="9132f-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="9132f-114">Options</span></span>

`-h|--help`

<span data-ttu-id="9132f-115">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9132f-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="9132f-116">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="9132f-116">Specifies the server URL.</span></span> <span data-ttu-id="9132f-117">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="9132f-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbol-source <SOURCE>`

<span data-ttu-id="9132f-118">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9132f-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="9132f-119">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="9132f-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="9132f-120">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="9132f-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="9132f-121">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9132f-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="9132f-122">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="9132f-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="9132f-123">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9132f-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="9132f-124">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP (S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="9132f-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="9132f-125">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="9132f-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="9132f-126">Fuerza que toda la salida registrada esté en inglés.</span><span class="sxs-lookup"><span data-stu-id="9132f-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="9132f-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9132f-127">Examples</span></span>

<span data-ttu-id="9132f-128">Inserta *foo.nupkg* para adoptar como predeterminado el origen de inserción, y proporciona la clave de API:</span><span class="sxs-lookup"><span data-stu-id="9132f-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="9132f-129">Inserta *foo.nupkg* en el origen de inserción personalizado `http://customsource`, y proporciona una clave de API:</span><span class="sxs-lookup"><span data-stu-id="9132f-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="9132f-130">Inserta *foo.nupkg* en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="9132f-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="9132f-131">Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="9132f-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="9132f-132">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="9132f-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="9132f-133">Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="9132f-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="9132f-134">Inserta todos los archivos *.nupkg* del directorio actual en el origen de inserción predeterminado, y especifica un archivo de configuración personalizado *./config/My.Config*:</span><span class="sxs-lookup"><span data-stu-id="9132f-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4d5efa94c6a4494158aea447be98256d2a307cd6
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539130"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="7acbd-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="7acbd-103">dotnet nuget push</span></span>

<span data-ttu-id="7acbd-104">**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7acbd-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="7acbd-105">nombre</span><span class="sxs-lookup"><span data-stu-id="7acbd-105">Name</span></span>

<span data-ttu-id="7acbd-106">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="7acbd-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7acbd-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7acbd-107">Synopsis</span></span>

```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7acbd-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7acbd-108">Description</span></span>

<span data-ttu-id="7acbd-109">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="7acbd-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="7acbd-110">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="7acbd-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="7acbd-111">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="7acbd-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="7acbd-112">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7acbd-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="7acbd-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7acbd-113">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="7acbd-114">Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.</span><span class="sxs-lookup"><span data-stu-id="7acbd-114">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="7acbd-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="7acbd-115">Options</span></span>

* **`-d|--disable-buffering`**

  <span data-ttu-id="7acbd-116">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="7acbd-116">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="7acbd-117">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="7acbd-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="7acbd-118">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7acbd-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="7acbd-119">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="7acbd-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="7acbd-120">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="7acbd-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="7acbd-121">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="7acbd-121">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="7acbd-122">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="7acbd-122">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="7acbd-123">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="7acbd-123">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="7acbd-124">Opción disponible desde el SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="7acbd-124">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="7acbd-125">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="7acbd-125">Specifies the server URL.</span></span> <span data-ttu-id="7acbd-126">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7acbd-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="7acbd-127">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7acbd-127">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="7acbd-128">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="7acbd-128">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="7acbd-129">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="7acbd-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="7acbd-130">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="7acbd-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="7acbd-131">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7acbd-131">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="7acbd-132">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7acbd-132">Examples</span></span>

* <span data-ttu-id="7acbd-133">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="7acbd-133">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="7acbd-134">Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="7acbd-134">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="7acbd-135">Inserta *foo.nupkg* en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="7acbd-135">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="7acbd-136">Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="7acbd-136">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="7acbd-137">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="7acbd-137">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="7acbd-138">Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="7acbd-138">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```
  
  > [!NOTE]
  > <span data-ttu-id="7acbd-139">Si este comando no funciona, es posible que se deba a un error presente en versiones anteriores del SDK (SDK de .NET Core 2.1 y versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="7acbd-139">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="7acbd-140">Para solucionar este problema, actualice la versión de su SDK o ejecute el siguiente comando en su lugar: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="7acbd-140">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

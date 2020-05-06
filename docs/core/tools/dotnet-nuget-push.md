---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 8b0437d7f4ada2b56af50e30717d131668c21f7e
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728355"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="bd3f5-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="bd3f5-103">dotnet nuget push</span></span>

<span data-ttu-id="bd3f5-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bd3f5-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="bd3f5-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bd3f5-105">Name</span></span>

<span data-ttu-id="bd3f5-106">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bd3f5-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="bd3f5-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="bd3f5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd3f5-108">Description</span></span>

<span data-ttu-id="bd3f5-109">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="bd3f5-110">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="bd3f5-111">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="bd3f5-112">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="bd3f5-113">El comando inserta un paquete existente.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-113">The command pushes an existing package.</span></span> <span data-ttu-id="bd3f5-114">No crea un paquete.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-114">It doesn't create a package.</span></span> <span data-ttu-id="bd3f5-115">Para crear un paquete, use [`dotnet pack`](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="bd3f5-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bd3f5-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="bd3f5-117">Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="bd3f5-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="bd3f5-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="bd3f5-119">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="bd3f5-120">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="bd3f5-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="bd3f5-122">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="bd3f5-123">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="bd3f5-124">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-124">The API key for the server.</span></span>

- **`-n|--no-symbols`**

  <span data-ttu-id="bd3f5-125">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="bd3f5-126">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="bd3f5-127">Opción disponible desde el SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="bd3f5-128">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-128">Specifies the server URL.</span></span> <span data-ttu-id="bd3f5-129">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-129">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="bd3f5-130">Al insertar varios paquetes en un servidor HTTP(S), trata cualquier respuesta de conflicto 409 como una advertencia para que la inserción pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-130">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="bd3f5-131">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-131">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="bd3f5-132">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-132">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="bd3f5-133">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-133">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="bd3f5-134">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-134">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="bd3f5-135">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-135">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="bd3f5-136">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-136">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="bd3f5-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="bd3f5-137">Examples</span></span>

- <span data-ttu-id="bd3f5-138">Inserte *foo.nupkg* en el origen de inserción predeterminado y especifique una clave de API:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-138">Push *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="bd3f5-139">Inserte *foo.nupkg* en el servidor de NuGet oficial y especifique una clave de API:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-139">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="bd3f5-140">Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-140">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="bd3f5-141">Inserte *foo.nupkg* en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-141">Push *foo.nupkg* to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="bd3f5-142">Inserte *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-142">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="bd3f5-143">Inserte *foo.nupkg* en el origen de inserción predeterminado y especifique un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-143">Push *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="bd3f5-144">Inserte todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-144">Push all *.nupkg* files in the current directory to the default push source:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg
  ```

  > [!NOTE]
  > <span data-ttu-id="bd3f5-145">Si este comando no funciona, es posible que se deba a un error presente en versiones anteriores del SDK (SDK de .NET Core 2.1 y versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-145">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="bd3f5-146">Para solucionar este problema, actualice la versión de su SDK o ejecute el siguiente comando en su lugar: `dotnet nuget push **/*.nupkg`</span><span class="sxs-lookup"><span data-stu-id="bd3f5-146">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push **/*.nupkg`</span></span>

- <span data-ttu-id="bd3f5-147">Inserte todos los archivos *.nupkg*, aunque un servidor HTTP(S) devuelva una respuesta de conflicto 409:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-147">Push all *.nupkg* files even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg --skip-duplicate
  ```

- <span data-ttu-id="bd3f5-148">Inserte todos los archivos *.nupkg*  del directorio actual en un directorio de fuente local:</span><span class="sxs-lookup"><span data-stu-id="bd3f5-148">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push *.nupkg -s c:\mydir
  ```

  <span data-ttu-id="bd3f5-149">Este comando no almacena paquetes en una estructura de carpetas jerárquica, lo que se recomienda para optimizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="bd3f5-149">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="bd3f5-150">Para obtener más información, vea [Fuentes locales](//nuget/hosting-packages/local-feeds).</span><span class="sxs-lookup"><span data-stu-id="bd3f5-150">For more information, see [Local feeds](//nuget/hosting-packages/local-feeds).</span></span>
  
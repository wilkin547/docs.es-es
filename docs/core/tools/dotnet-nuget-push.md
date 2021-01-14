---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 99e735f7bb18b7af1c12c3ef77fc150a19083542
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970660"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="ca328-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="ca328-103">dotnet nuget push</span></span>

<span data-ttu-id="ca328-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ca328-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ca328-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ca328-105">Name</span></span>

<span data-ttu-id="ca328-106">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="ca328-106">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ca328-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ca328-107">Synopsis</span></span>

```dotnetcli
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [-n|--no-symbols true]
    [--no-service-endpoint] [-s|--source <SOURCE>] [--skip-duplicate]
    [-sk|--symbol-api-key <API_KEY>] [-ss|--symbol-source <SOURCE>]
    [-t|--timeout <TIMEOUT>]

dotnet nuget push -h|--help
```

## <a name="description"></a><span data-ttu-id="ca328-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca328-108">Description</span></span>

<span data-ttu-id="ca328-109">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="ca328-109">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="ca328-110">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="ca328-110">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="ca328-111">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="ca328-111">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="ca328-112">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca328-112">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

<span data-ttu-id="ca328-113">El comando inserta un paquete existente.</span><span class="sxs-lookup"><span data-stu-id="ca328-113">The command pushes an existing package.</span></span> <span data-ttu-id="ca328-114">No crea un paquete.</span><span class="sxs-lookup"><span data-stu-id="ca328-114">It doesn't create a package.</span></span> <span data-ttu-id="ca328-115">Para crear un paquete, use [`dotnet pack`](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ca328-115">To create a package, use [`dotnet pack`](dotnet-pack.md).</span></span>

## <a name="arguments"></a><span data-ttu-id="ca328-116">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca328-116">Arguments</span></span>

- **`ROOT`**

  <span data-ttu-id="ca328-117">Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.</span><span class="sxs-lookup"><span data-stu-id="ca328-117">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="ca328-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="ca328-118">Options</span></span>

- **`-d|--disable-buffering`**

  <span data-ttu-id="ca328-119">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="ca328-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

- **`--force-english-output`**

  <span data-ttu-id="ca328-120">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="ca328-120">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="ca328-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ca328-121">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="ca328-122">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="ca328-122">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="ca328-123">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="ca328-123">Option available since .NET Core 2.2 SDK.</span></span>

- **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="ca328-124">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="ca328-124">The API key for the server.</span></span>

- **`-n|--no-symbols true`**

  <span data-ttu-id="ca328-125">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="ca328-125">Doesn't push symbols (even if present).</span></span>

- **`--no-service-endpoint`**

  <span data-ttu-id="ca328-126">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="ca328-126">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="ca328-127">Opción disponible desde el SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="ca328-127">Option available since .NET Core 2.1 SDK.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="ca328-128">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="ca328-128">Specifies the server URL.</span></span> <span data-ttu-id="ca328-129">NuGet identifica un origen de carpeta local o UNC y simplemente copia el archivo allí, en lugar de insertarlo mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="ca328-129">NuGet identifies a UNC or local folder source and simply copies the file there instead of pushing it using HTTP.</span></span>
  > [!IMPORTANT]
  > <span data-ttu-id="ca328-130">A partir de NuGet 3.4.2, se trata de un parámetro obligatorio, a menos que el archivo de configuración de NuGet especifique un valor `DefaultPushSource`.</span><span class="sxs-lookup"><span data-stu-id="ca328-130">Starting with NuGet 3.4.2, this is a mandatory parameter unless the NuGet config file specifies a `DefaultPushSource` value.</span></span> <span data-ttu-id="ca328-131">Para más información, vea [Configuring NuGet behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="ca328-131">For more information, see [Configuring NuGet behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--skip-duplicate`**

  <span data-ttu-id="ca328-132">Al insertar varios paquetes en un servidor HTTP(S), trata cualquier respuesta de conflicto 409 como una advertencia para que la inserción pueda continuar.</span><span class="sxs-lookup"><span data-stu-id="ca328-132">When pushing multiple packages to an HTTP(S) server, treats any 409 Conflict response as a warning so that the push can continue.</span></span> <span data-ttu-id="ca328-133">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="ca328-133">Available since .NET Core 3.1 SDK.</span></span>

- **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="ca328-134">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ca328-134">The API key for the symbol server.</span></span>

- **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="ca328-135">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="ca328-135">Specifies the symbol server URL.</span></span>

- **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="ca328-136">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="ca328-136">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="ca328-137">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="ca328-137">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="ca328-138">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ca328-138">Specifying 0 (zero seconds) applies the default value.</span></span>

## <a name="examples"></a><span data-ttu-id="ca328-139">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ca328-139">Examples</span></span>

- <span data-ttu-id="ca328-140">Inserte *foo.nupkg* en el origen de inserción predeterminado especificado en el archivo de configuración de NuGet, mediante una clave de API:</span><span class="sxs-lookup"><span data-stu-id="ca328-140">Push *foo.nupkg* to the default push source specified in the NuGet config file, using an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

- <span data-ttu-id="ca328-141">Inserte *foo.nupkg* en el servidor de NuGet oficial y especifique una clave de API:</span><span class="sxs-lookup"><span data-stu-id="ca328-141">Push *foo.nupkg* to the official NuGet server, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://api.nuget.org/v3/index.json
  ```
  
  * <span data-ttu-id="ca328-142">Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="ca328-142">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

- <span data-ttu-id="ca328-143">Inserte *foo.nupkg* en el origen de inserción predeterminado especificado en el archivo de configuración de NuGet:</span><span class="sxs-lookup"><span data-stu-id="ca328-143">Push *foo.nupkg* to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg
  ```

- <span data-ttu-id="ca328-144">Inserte *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="ca328-144">Push *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```dotnetcli
  dotnet nuget push foo.symbols.nupkg
  ```

- <span data-ttu-id="ca328-145">Inserte *foo.nupkg* en el origen de inserción predeterminado especificado en el archivo de configuración de NuGet, con un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="ca328-145">Push *foo.nupkg* to the default push source specified in the NuGet config file, with a 360-second timeout:</span></span>

  ```dotnetcli
  dotnet nuget push foo.nupkg --timeout 360
  ```

- <span data-ttu-id="ca328-146">Inserte todos los archivos *.nupkg* del directorio actual en el origen de inserción predeterminado especificado en el archivo de configuración de NuGet:</span><span class="sxs-lookup"><span data-stu-id="ca328-146">Push all *.nupkg* files in the current directory to the default push source specified in the NuGet config file:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg"
  ```

  > [!NOTE]
  > <span data-ttu-id="ca328-147">Si este comando no funciona, es posible que se deba a un error presente en versiones anteriores del SDK (SDK de .NET Core 2.1 y versiones anteriores).</span><span class="sxs-lookup"><span data-stu-id="ca328-147">If this command doesn't work, it might be due to a bug that existed in older versions of the SDK (.NET Core 2.1 SDK and earlier versions).</span></span>
  > <span data-ttu-id="ca328-148">Para solucionar este problema, actualice la versión de su SDK o ejecute el siguiente comando en su lugar: `dotnet nuget push "**/*.nupkg"`</span><span class="sxs-lookup"><span data-stu-id="ca328-148">To fix this, upgrade your SDK version or run the following command instead: `dotnet nuget push "**/*.nupkg"`</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="ca328-149">Las comillas de inclusión son necesarias para los shells como bash que usan comodines de archivo.</span><span class="sxs-lookup"><span data-stu-id="ca328-149">The enclosing quotes are required for shells such as bash that perform file globbing.</span></span> <span data-ttu-id="ca328-150">Para obtener más información, vea [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).</span><span class="sxs-lookup"><span data-stu-id="ca328-150">For more information, see [NuGet/Home#4393](https://github.com/NuGet/Home/issues/4393#issuecomment-667618120).</span></span>

- <span data-ttu-id="ca328-151">Inserte todos los archivos *.nupkg* en el origen de inserción predeterminado especificado en el archivo de configuración de NuGet, incluso si un servidor HTTP(S) devuelve una respuesta de conflicto 409:</span><span class="sxs-lookup"><span data-stu-id="ca328-151">Push all *.nupkg* files to the default push source specified in the NuGet config file, even if a 409 Conflict response is returned by an HTTP(S) server:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" --skip-duplicate
  ```

- <span data-ttu-id="ca328-152">Inserte todos los archivos *.nupkg*  del directorio actual en un directorio de fuente local:</span><span class="sxs-lookup"><span data-stu-id="ca328-152">Push all *.nupkg* files in the current directory to a local feed directory:</span></span>

  ```dotnetcli
  dotnet nuget push "*.nupkg" -s c:\mydir
  ```

  <span data-ttu-id="ca328-153">Este comando no almacena paquetes en una estructura de carpetas jerárquica, lo que se recomienda para optimizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ca328-153">This command doesn't store packages in a hierarchical folder structure, which is recommended to optimize performance.</span></span> <span data-ttu-id="ca328-154">Para obtener más información, vea [Fuentes locales](/nuget/hosting-packages/local-feeds).</span><span class="sxs-lookup"><span data-stu-id="ca328-154">For more information, see [Local feeds](/nuget/hosting-packages/local-feeds).</span></span>  

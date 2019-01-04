---
title: Comando dotnet nuget push
description: El comando dotnet nuget push inserta un paquete en el servidor y lo publica.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 4f0d127d8b9f37b1c381d8981f54035a2fc3b0e5
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169357"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="921c7-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="921c7-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="921c7-104">nombre</span><span class="sxs-lookup"><span data-stu-id="921c7-104">Name</span></span>

<span data-ttu-id="921c7-105">`dotnet nuget push`: inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="921c7-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="921c7-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="921c7-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="921c7-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="921c7-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [--interactive] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="921c7-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="921c7-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="921c7-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="921c7-109">Description</span></span>

<span data-ttu-id="921c7-110">El comando `dotnet nuget push` inserta un paquete en el servidor y lo publica.</span><span class="sxs-lookup"><span data-stu-id="921c7-110">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="921c7-111">El comando push usa los detalles del servidor y de las credenciales encontrados en el archivo de configuración NuGet del sistema o en la cadena de archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="921c7-111">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="921c7-112">Para más información sobre los archivos de configuración, consulte [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior) (Configuración del comportamiento de NuGet).</span><span class="sxs-lookup"><span data-stu-id="921c7-112">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="921c7-113">La configuración predeterminada de NuGet se obtiene mediante la carga de *%AppData%\NuGet\NuGet.config* (Windows) o *$HOME/.local/share* (Linux/macOS), y luego la carga de cualquier archivo *nuget.config* o *.nuget\nuget.config* comenzando desde la raíz de la unidad y finalizando en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="921c7-113">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="921c7-114">Argumentos</span><span class="sxs-lookup"><span data-stu-id="921c7-114">Arguments</span></span>

* **`ROOT`**

  <span data-ttu-id="921c7-115">Especifica la ruta de acceso al archivo en la que se debe insertar el paquete.</span><span class="sxs-lookup"><span data-stu-id="921c7-115">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="921c7-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="921c7-116">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="921c7-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="921c7-117">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="921c7-118">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="921c7-118">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="921c7-119">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="921c7-119">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

<span data-ttu-id="921c7-120">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="921c7-120">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="921c7-121">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="921c7-121">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="921c7-122">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="921c7-122">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="921c7-123">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="921c7-123">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="921c7-124">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="921c7-124">Doesn't push symbols (even if present).</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="921c7-125">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="921c7-125">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="921c7-126">Opción disponible desde el SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="921c7-126">Option available since .NET Core 2.1 SDK.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="921c7-127">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="921c7-127">Specifies the server URL.</span></span> <span data-ttu-id="921c7-128">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="921c7-128">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="921c7-129">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="921c7-129">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="921c7-130">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="921c7-130">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="921c7-131">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="921c7-131">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="921c7-132">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="921c7-132">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="921c7-133">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="921c7-133">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="921c7-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="921c7-134">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-d|--disable-buffering`**

  <span data-ttu-id="921c7-135">Deshabilita el almacenamiento en búfer al realizar inserciones en un servidor HTTP(S) para reducir el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="921c7-135">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

* **`--force-english-output`**

  <span data-ttu-id="921c7-136">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="921c7-136">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="921c7-137">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="921c7-137">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="921c7-138">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="921c7-138">The API key for the server.</span></span>

* **`-n|--no-symbols`**

  <span data-ttu-id="921c7-139">No inserta símbolos (incluso si está presente).</span><span class="sxs-lookup"><span data-stu-id="921c7-139">Doesn't push symbols (even if present).</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="921c7-140">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="921c7-140">Specifies the server URL.</span></span> <span data-ttu-id="921c7-141">Esta opción es necesaria a menos que el valor de configuración `DefaultPushSource` esté establecido en el archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="921c7-141">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

* **`-sk|--symbol-api-key <API_KEY>`**

  <span data-ttu-id="921c7-142">La clave de API para el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="921c7-142">The API key for the symbol server.</span></span>

* **`-ss|--symbol-source <SOURCE>`**

  <span data-ttu-id="921c7-143">Especifica la dirección URL del servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="921c7-143">Specifies the symbol server URL.</span></span>

* **`-t|--timeout <TIMEOUT>`**

  <span data-ttu-id="921c7-144">Especifica el tiempo de espera para la inserción en un servidor en segundos.</span><span class="sxs-lookup"><span data-stu-id="921c7-144">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="921c7-145">El valor predeterminado es 300 segundos (5 minutos).</span><span class="sxs-lookup"><span data-stu-id="921c7-145">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="921c7-146">Si se especifica 0 (cero segundos), se aplica el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="921c7-146">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="921c7-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="921c7-147">Examples</span></span>

* <span data-ttu-id="921c7-148">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="921c7-148">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a
  ```

* <span data-ttu-id="921c7-149">Inserta *foo.nupkg* en el origen de inserción personalizado `https://customsource`, y especifica una clave de API:</span><span class="sxs-lookup"><span data-stu-id="921c7-149">Push *foo.nupkg* to the custom push source `https://customsource`, specifying an API key:</span></span>

  ```console
  dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s https://customsource/
  ```

* <span data-ttu-id="921c7-150">Inserta *foo.nupkg* en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="921c7-150">Pushes *foo.nupkg* to the default push source:</span></span>

  ```console
  dotnet nuget push foo.nupkg
  ```

* <span data-ttu-id="921c7-151">Inserta *foo.symbols.nupkp* en el origen de símbolos predeterminado:</span><span class="sxs-lookup"><span data-stu-id="921c7-151">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

  ```console
  dotnet nuget push foo.symbols.nupkg
  ```

* <span data-ttu-id="921c7-152">Inserta *foo.nupkg* en el origen de inserción predeterminado, y especifica un tiempo de espera de 360 segundos:</span><span class="sxs-lookup"><span data-stu-id="921c7-152">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

  ```console
  dotnet nuget push foo.nupkg --timeout 360
  ```

* <span data-ttu-id="921c7-153">Inserta todos los archivos *.nupkg*  del directorio actual en el origen de inserción predeterminado:</span><span class="sxs-lookup"><span data-stu-id="921c7-153">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

  ```console
  dotnet nuget push *.nupkg
  ```
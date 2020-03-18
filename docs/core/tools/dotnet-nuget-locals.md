---
title: Comando dotnet nuget locals
description: El comando dotnet nuget locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
author: karann-msft
ms.date: 02/14/2020
ms.openlocfilehash: 3fdd7d946b08b4c18cfaeb65013de259b927a7fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503685"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="71d58-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="71d58-103">dotnet nuget locals</span></span>

<span data-ttu-id="71d58-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="71d58-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="71d58-105">Name</span><span class="sxs-lookup"><span data-stu-id="71d58-105">Name</span></span>

<span data-ttu-id="71d58-106">`dotnet nuget locals`: borra o enumera recursos locales de NuGet.</span><span class="sxs-lookup"><span data-stu-id="71d58-106">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="71d58-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="71d58-107">Synopsis</span></span>

```dotnetcli
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="71d58-108">Description</span><span class="sxs-lookup"><span data-stu-id="71d58-108">Description</span></span>

<span data-ttu-id="71d58-109">El comando `dotnet nuget locals` borra o enumera los recursos locales de NuGet en la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="71d58-109">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="71d58-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="71d58-110">Arguments</span></span>

- **`CACHE_LOCATION`**

  <span data-ttu-id="71d58-111">La ubicación de caché que se va a mostrar o borrar.</span><span class="sxs-lookup"><span data-stu-id="71d58-111">The cache location to list or clear.</span></span> <span data-ttu-id="71d58-112">Acepta uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="71d58-112">It accepts one of the following values:</span></span>

  * <span data-ttu-id="71d58-113">`all`: indica que la operación especificada se debe aplicar a todos los tipos de caché: caché de solicitudes http, caché de paquetes globales y caché temporal.</span><span class="sxs-lookup"><span data-stu-id="71d58-113">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="71d58-114">`http-cache`: indica que la operación especificada se aplica solo a la caché de solicitudes http.</span><span class="sxs-lookup"><span data-stu-id="71d58-114">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="71d58-115">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="71d58-115">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="71d58-116">`global-packages`: indica que la operación especificada se aplica solo a la caché de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="71d58-116">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="71d58-117">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="71d58-117">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="71d58-118">`temp`: indica que la operación especificada se aplica solo a la caché temporal.</span><span class="sxs-lookup"><span data-stu-id="71d58-118">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="71d58-119">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="71d58-119">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="71d58-120">Opciones</span><span class="sxs-lookup"><span data-stu-id="71d58-120">Options</span></span>

- **`--force-english-output`**

  <span data-ttu-id="71d58-121">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="71d58-121">Forces the application to run using an invariant, English-based culture.</span></span>

- **`-h|--help`**

  <span data-ttu-id="71d58-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="71d58-122">Prints out a short help for the command.</span></span>

- **`-c|--clear`**

  <span data-ttu-id="71d58-123">La opción de borrado ejecuta una operación de borrado sobre el tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="71d58-123">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="71d58-124">El contenido de los directorios de caché se elimina de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="71d58-124">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="71d58-125">El usuario o grupo de ejecución deben tener permiso para los archivos en los directorios de la caché.</span><span class="sxs-lookup"><span data-stu-id="71d58-125">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="71d58-126">En caso contrario, se muestra un error para indicar los archivos o las carpetas que no se han borrado.</span><span class="sxs-lookup"><span data-stu-id="71d58-126">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

- **`-l|--list`**

  <span data-ttu-id="71d58-127">La opción de lista se usa para mostrar la ubicación del tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="71d58-127">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="71d58-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="71d58-128">Examples</span></span>

- <span data-ttu-id="71d58-129">Muestra las rutas de acceso de todos los directorios de caché locales (el directorio de caché http, el directorio de caché de paquetes globales y el directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="71d58-129">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all –l
  ```

- <span data-ttu-id="71d58-130">Muestra la ruta de acceso del directorio de la caché de solicitudes http:</span><span class="sxs-lookup"><span data-stu-id="71d58-130">Displays the path for the local http-cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals http-cache --list
  ```

- <span data-ttu-id="71d58-131">Borra todos los archivos de todos los directorios de caché locales (directorio de caché http, directorio de caché de paquetes globales y directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="71d58-131">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```dotnetcli
  dotnet nuget locals all --clear
  ```

- <span data-ttu-id="71d58-132">Borra todos los archivos del directorio local de la caché de paquetes globales:</span><span class="sxs-lookup"><span data-stu-id="71d58-132">Clears all files in local global-packages cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals global-packages -c
  ```

- <span data-ttu-id="71d58-133">Borra todos los archivos del directorio local de la caché temporal:</span><span class="sxs-lookup"><span data-stu-id="71d58-133">Clears all files in local temporary cache directory:</span></span>

  ```dotnetcli
  dotnet nuget locals temp -c
  ```

## <a name="troubleshooting"></a><span data-ttu-id="71d58-134">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="71d58-134">Troubleshooting</span></span>

<span data-ttu-id="71d58-135">Para más información sobre problemas y errores comunes encontrados al usar el comando `dotnet nuget locals`, consulte [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).</span><span class="sxs-lookup"><span data-stu-id="71d58-135">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>

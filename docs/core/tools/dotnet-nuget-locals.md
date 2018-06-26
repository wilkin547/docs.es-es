---
title: 'Comando dotnet nuget locals: CLI de .NET Core'
description: El comando dotnet nuget locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
author: karann-msft
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 799acb92d6ab7439e15c23c9f0b7b572c966adda
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696876"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="0c287-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="0c287-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0c287-104">nombre</span><span class="sxs-lookup"><span data-stu-id="0c287-104">Name</span></span>

<span data-ttu-id="0c287-105">`dotnet nuget locals`: borra o enumera recursos locales de NuGet.</span><span class="sxs-lookup"><span data-stu-id="0c287-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c287-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0c287-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="0c287-107">Description</span><span class="sxs-lookup"><span data-stu-id="0c287-107">Description</span></span>

<span data-ttu-id="0c287-108">El comando `dotnet nuget locals` borra o enumera los recursos locales de NuGet en la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="0c287-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="0c287-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0c287-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="0c287-110">La ubicación de caché que se va a mostrar o borrar.</span><span class="sxs-lookup"><span data-stu-id="0c287-110">The cache location to list or clear.</span></span> <span data-ttu-id="0c287-111">Acepta uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c287-111">It accepts one of the following values:</span></span>

* <span data-ttu-id="0c287-112">`all`: indica que la operación especificada se debe aplicar a todos los tipos de caché: caché de solicitudes http, caché de paquetes globales y caché temporal.</span><span class="sxs-lookup"><span data-stu-id="0c287-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="0c287-113">`http-cache`: indica que la operación especificada se aplica solo a la caché de solicitudes http.</span><span class="sxs-lookup"><span data-stu-id="0c287-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="0c287-114">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="0c287-114">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="0c287-115">`global-packages`: indica que la operación especificada se aplica solo a la caché de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="0c287-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="0c287-116">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="0c287-116">The other cache locations aren't affected.</span></span>
* <span data-ttu-id="0c287-117">`temp`: indica que la operación especificada se aplica solo a la caché temporal.</span><span class="sxs-lookup"><span data-stu-id="0c287-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="0c287-118">Las otras ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="0c287-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="0c287-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="0c287-119">Options</span></span>

`--force-english-output`

<span data-ttu-id="0c287-120">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="0c287-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="0c287-121">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0c287-121">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="0c287-122">La opción de borrado ejecuta una operación de borrado sobre el tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="0c287-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="0c287-123">El contenido de los directorios de caché se elimina de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="0c287-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="0c287-124">El usuario o grupo de ejecución deben tener permiso para los archivos en los directorios de la caché.</span><span class="sxs-lookup"><span data-stu-id="0c287-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="0c287-125">En caso contrario, se muestra un error para indicar los archivos o las carpetas que no se han borrado.</span><span class="sxs-lookup"><span data-stu-id="0c287-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

`-l|--list`

<span data-ttu-id="0c287-126">La opción de lista se usa para mostrar la ubicación del tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="0c287-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="0c287-127">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0c287-127">Examples</span></span>

<span data-ttu-id="0c287-128">Muestra las rutas de acceso de todos los directorios de caché locales (el directorio de caché http, el directorio de caché de paquetes globales y el directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="0c287-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="0c287-129">Muestra la ruta de acceso del directorio de la caché de solicitudes http:</span><span class="sxs-lookup"><span data-stu-id="0c287-129">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="0c287-130">Borra todos los archivos de todos los directorios de caché locales (directorio de caché http, directorio de caché de paquetes globales y directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="0c287-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="0c287-131">Borra todos los archivos del directorio local de la caché de paquetes globales:</span><span class="sxs-lookup"><span data-stu-id="0c287-131">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="0c287-132">Borra todos los archivos del directorio local de la caché temporal:</span><span class="sxs-lookup"><span data-stu-id="0c287-132">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="0c287-133">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="0c287-133">Troubleshooting</span></span>

<span data-ttu-id="0c287-134">Para más información sobre problemas y errores comunes encontrados al usar el comando `dotnet nuget locals`, consulte [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).</span><span class="sxs-lookup"><span data-stu-id="0c287-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
---
title: 'Comando dotnet nuget locals: CLI de .NET Core'
description: "El comando dotnet nuget locals borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 2b66198ac3e33c640abda0c96fb05944f5ea91df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="29cda-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="29cda-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="29cda-104">Name</span><span class="sxs-lookup"><span data-stu-id="29cda-104">Name</span></span>

<span data-ttu-id="29cda-105">`dotnet nuget locals`: borra o enumera recursos locales de NuGet.</span><span class="sxs-lookup"><span data-stu-id="29cda-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="29cda-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="29cda-106">Synopsis</span></span>

`dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="29cda-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="29cda-107">Description</span></span>

<span data-ttu-id="29cda-108">El comando `dotnet nuget locals` borra o enumera los recursos locales de NuGet en la caché de solicitudes http, la caché temporal o la carpeta de paquetes globales de toda la máquina.</span><span class="sxs-lookup"><span data-stu-id="29cda-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="29cda-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="29cda-109">Arguments</span></span>

`CACHE_LOCATION`

<span data-ttu-id="29cda-110">Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="29cda-110">One of the following values:</span></span>

* <span data-ttu-id="29cda-111">`all`: indica que la operación especificada se debe aplicar a todos los tipos de caché: caché de solicitudes http, caché de paquetes globales y caché temporal.</span><span class="sxs-lookup"><span data-stu-id="29cda-111">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
* <span data-ttu-id="29cda-112">`http-cache`: indica que la operación especificada se aplica solo a la caché de solicitudes http.</span><span class="sxs-lookup"><span data-stu-id="29cda-112">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="29cda-113">Las otra ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="29cda-113">The other cache locations are not affected.</span></span>
* <span data-ttu-id="29cda-114">`global-packages`: indica que la operación especificada se aplica solo a la caché de paquetes globales.</span><span class="sxs-lookup"><span data-stu-id="29cda-114">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="29cda-115">Las otra ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="29cda-115">The other cache locations are not affected.</span></span>
* <span data-ttu-id="29cda-116">`temp`: indica que la operación especificada se aplica solo a la caché temporal.</span><span class="sxs-lookup"><span data-stu-id="29cda-116">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="29cda-117">Las otra ubicaciones de caché no se ven afectadas.</span><span class="sxs-lookup"><span data-stu-id="29cda-117">The other cache locations are not affected.</span></span>

## <a name="options"></a><span data-ttu-id="29cda-118">Opciones</span><span class="sxs-lookup"><span data-stu-id="29cda-118">Options</span></span>

`-h|--help`

<span data-ttu-id="29cda-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="29cda-119">Prints out a short help for the command.</span></span>

`-c|--clear`

<span data-ttu-id="29cda-120">La opción de borrado realiza una operación de borrado sobre el tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="29cda-120">The clear option performs a clear operation on the specified cache type.</span></span> <span data-ttu-id="29cda-121">El contenido de los directorios de caché se elimina de forma recursiva.</span><span class="sxs-lookup"><span data-stu-id="29cda-121">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="29cda-122">El usuario o grupo de ejecución deben tener permiso para los archivos en los directorios de la caché.</span><span class="sxs-lookup"><span data-stu-id="29cda-122">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="29cda-123">En caso contrario, se muestra un error para indicar que los archivos o carpetas no se han borrado.</span><span class="sxs-lookup"><span data-stu-id="29cda-123">If not, an error is displayed indicating the files/folders which were not cleared.</span></span>

`-l|--list`

<span data-ttu-id="29cda-124">La opción de lista se usa para mostrar la ubicación del tipo de caché especificado.</span><span class="sxs-lookup"><span data-stu-id="29cda-124">The list option is used to display the location of the specified cache type.</span></span> 

`--force-english-output`

<span data-ttu-id="29cda-125">Fuerza la salida de la línea de comandos en inglés.</span><span class="sxs-lookup"><span data-stu-id="29cda-125">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="29cda-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="29cda-126">Examples</span></span>

<span data-ttu-id="29cda-127">Muestra las rutas de acceso de todos los directorios de caché locales (el directorio de caché http, el directorio de caché de paquetes globales y el directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="29cda-127">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals –l all`

<span data-ttu-id="29cda-128">Muestra la ruta de acceso del directorio de la caché de solicitudes http:</span><span class="sxs-lookup"><span data-stu-id="29cda-128">Displays the path for the local http-cache directory:</span></span>

`dotnet nuget locals --list http-cache`

<span data-ttu-id="29cda-129">Borra todos los archivos de todos los directorios de caché locales (directorio de caché http, directorio de caché de paquetes globales y directorio de caché temporal):</span><span class="sxs-lookup"><span data-stu-id="29cda-129">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

`dotnet nuget locals --clear all`

<span data-ttu-id="29cda-130">Borra todos los archivos del directorio local de la caché de paquetes globales:</span><span class="sxs-lookup"><span data-stu-id="29cda-130">Clears all files in local global-packages cache directory:</span></span>

`dotnet nuget locals -c global-packages`

<span data-ttu-id="29cda-131">Borra todos los archivos del directorio local de la caché temporal:</span><span class="sxs-lookup"><span data-stu-id="29cda-131">Clears all files in local temporary cache directory:</span></span>

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a><span data-ttu-id="29cda-132">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="29cda-132">Troubleshooting</span></span>

<span data-ttu-id="29cda-133">Para más información sobre problemas y errores comunes encontrados al usar el comando `dotnet nuget locals`, consulte [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache) (Administración de la caché de NuGet).</span><span class="sxs-lookup"><span data-stu-id="29cda-133">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
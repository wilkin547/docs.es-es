---
title: 'Sondeo predeterminado: .NET Core'
description: Información general de la lógica de sondeo System.Runtime.Loader.AssemblyLoadContext.Default de .NET Core para buscar dependencias.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608423"
---
# <a name="default-probing"></a><span data-ttu-id="109b2-103">Sondeo predeterminado</span><span class="sxs-lookup"><span data-stu-id="109b2-103">Default probing</span></span>

<span data-ttu-id="109b2-104">La instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> se encarga de buscar las dependencias de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="109b2-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="109b2-105">En este artículo se describe la lógica de sondeo de la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="109b2-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="109b2-106">Propiedades de sondeo configuradas por host</span><span class="sxs-lookup"><span data-stu-id="109b2-106">Host configured probing properties</span></span>

<span data-ttu-id="109b2-107">Cuando se inicia el runtime, el host de tiempo de ejecución proporciona un conjunto de propiedades de sondeo con nombre que configuran las rutas de acceso de sondeo de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="109b2-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="109b2-108">Cada propiedad de sondeo es opcional.</span><span class="sxs-lookup"><span data-stu-id="109b2-108">Each probing property is optional.</span></span> <span data-ttu-id="109b2-109">Si está presente, cada propiedad es un valor de cadena que contiene una lista delimitada de rutas de acceso absolutas.</span><span class="sxs-lookup"><span data-stu-id="109b2-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="109b2-110">El delimitador es ";" en Windows y ":" en el resto de plataformas.</span><span class="sxs-lookup"><span data-stu-id="109b2-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="109b2-111">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="109b2-111">Property Name</span></span>                 |<span data-ttu-id="109b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="109b2-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="109b2-113">Lista de rutas de acceso de archivos de ensamblado de plataforma y aplicación.</span><span class="sxs-lookup"><span data-stu-id="109b2-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="109b2-114">Lista de rutas de acceso de directorio para buscar ensamblados de recursos satélite.</span><span class="sxs-lookup"><span data-stu-id="109b2-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="109b2-115">Lista de rutas de acceso de directorio para buscar bibliotecas no administradas (nativas).</span><span class="sxs-lookup"><span data-stu-id="109b2-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="109b2-116">Lista de rutas de acceso de directorio para buscar bibliotecas administradas.</span><span class="sxs-lookup"><span data-stu-id="109b2-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="109b2-117">Lista de rutas de acceso de directorio para buscar imágenes nativas de ensamblados administrados.</span><span class="sxs-lookup"><span data-stu-id="109b2-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="109b2-118">¿Cómo se rellenan las propiedades?</span><span class="sxs-lookup"><span data-stu-id="109b2-118">How are the properties populated?</span></span>

<span data-ttu-id="109b2-119">Existen dos escenarios principales para rellenar las propiedades, en función de si existe el archivo *\<myapp>.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="109b2-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="109b2-120">Cuando el archivo *\*.deps.json* está presente, se analiza para rellenar las propiedades de sondeo.</span><span class="sxs-lookup"><span data-stu-id="109b2-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="109b2-121">Cuando el archivo *\*.deps.json* no está presente, se supone que el directorio de la aplicación contiene todas las dependencias.</span><span class="sxs-lookup"><span data-stu-id="109b2-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="109b2-122">El contenido del directorio se usa para rellenar las propiedades de sondeo.</span><span class="sxs-lookup"><span data-stu-id="109b2-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="109b2-123">Además, los archivos *\*.deps.json* para cualquier marco al que se hace referencia se analizan de forma similar.</span><span class="sxs-lookup"><span data-stu-id="109b2-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="109b2-124">Por último, se puede usar la variable de entorno `ADDITIONAL_DEPS` para agregar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="109b2-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="109b2-125">`dotnet.exe` también contiene un parámetro `--additional-deps` opcional para establecer este valor en el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="109b2-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="109b2-126">Las propiedades `APP_PATHS` y `APP_NI_PATHS` no se rellenan de forma predeterminada y se omiten en la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="109b2-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="109b2-127">Se puede tener acceso a la lista de todos los archivos *\*.deps.json* usados por la aplicación a través de `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span><span class="sxs-lookup"><span data-stu-id="109b2-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="109b2-128">Cómo ver las propiedades de sondeo desde un código administrado</span><span class="sxs-lookup"><span data-stu-id="109b2-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="109b2-129">Cada propiedad está disponible mediante una llamada a la función <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> con el nombre de la propiedad de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="109b2-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="109b2-130">Cómo depurar la construcción de las propiedades de sondeo</span><span class="sxs-lookup"><span data-stu-id="109b2-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="109b2-131">El host de tiempo de ejecución de .NET Core generará mensajes de seguimiento útiles cuando se habiliten determinadas variables de entorno:</span><span class="sxs-lookup"><span data-stu-id="109b2-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="109b2-132">Variable de entorno</span><span class="sxs-lookup"><span data-stu-id="109b2-132">Environment Variable</span></span>        |<span data-ttu-id="109b2-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="109b2-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="109b2-134">Habilita el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="109b2-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="109b2-135">Realiza un seguimiento de una ruta de acceso de archivo en lugar del elemento `stderr` predeterminado.</span><span class="sxs-lookup"><span data-stu-id="109b2-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="109b2-136">Establece el nivel de detalle de 1 (inferior) a 4 (superior).</span><span class="sxs-lookup"><span data-stu-id="109b2-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="109b2-137">Sondeo predeterminado de ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="109b2-137">Managed assembly default probing</span></span>

<span data-ttu-id="109b2-138">Al realizar un sondeo para buscar un ensamblado administrado, <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> busca en orden en:</span><span class="sxs-lookup"><span data-stu-id="109b2-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="109b2-139">Archivos que coinciden con <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> en `TRUSTED_PLATFORM_ASSEMBLIES` (después de quitar extensiones de archivo).</span><span class="sxs-lookup"><span data-stu-id="109b2-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="109b2-140">Archivos de ensamblado de imagen nativa en `APP_NI_PATHS` con extensiones de archivo comunes.</span><span class="sxs-lookup"><span data-stu-id="109b2-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="109b2-141">Archivos de ensamblado en `APP_PATHS` con extensiones de archivo comunes.</span><span class="sxs-lookup"><span data-stu-id="109b2-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="109b2-142">Sondeo de ensamblado satélite (recurso)</span><span class="sxs-lookup"><span data-stu-id="109b2-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="109b2-143">Con el fin de buscar un ensamblado satélite para una referencia cultural concreta, construya un conjunto de rutas de acceso de archivos.</span><span class="sxs-lookup"><span data-stu-id="109b2-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="109b2-144">Para cada ruta de acceso de `PLATFORM_RESOURCE_ROOTS` y, después, `APP_PATHS`, anexe la cadena <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, un separador de directorios, la cadena <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> y la extensión ".dll".</span><span class="sxs-lookup"><span data-stu-id="109b2-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="109b2-145">Si existe algún archivo coincidente, intente cargarlo y devolverlo.</span><span class="sxs-lookup"><span data-stu-id="109b2-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="109b2-146">Sondeo de biblioteca no administrada (nativa)</span><span class="sxs-lookup"><span data-stu-id="109b2-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="109b2-147">Al realizar un sondeo para buscar una biblioteca no administrada, `NATIVE_DLL_SEARCH_DIRECTORIES` se busca mediante una búsqueda de una biblioteca coincidente.</span><span class="sxs-lookup"><span data-stu-id="109b2-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>

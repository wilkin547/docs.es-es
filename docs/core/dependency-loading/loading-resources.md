---
title: 'Algoritmo de carga de ensamblado satélite: .NET Core'
description: Descripción de los detalles del algoritmo de carga de ensamblado satélite en .NET Core
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 17f29a9aca79019daa91736e586bf1b6b753a9ec
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859534"
---
# <a name="satellite-assembly-loading-algorithm"></a><span data-ttu-id="1e976-103">Algoritmo de carga de ensamblado satélite</span><span class="sxs-lookup"><span data-stu-id="1e976-103">Satellite assembly loading algorithm</span></span>

<span data-ttu-id="1e976-104">Los ensamblados satélite se utilizan con el fin de almacenar los recursos localizados personalizados para el idioma y la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="1e976-104">Satellite assemblies are used to store localized resources customized for language and culture.</span></span>

<span data-ttu-id="1e976-105">Los ensamblados satélite usan un algoritmo de carga distinto al de los ensamblados administrados generales.</span><span class="sxs-lookup"><span data-stu-id="1e976-105">Satellite assemblies use a different loading algorithm than general managed assemblies.</span></span>

## <a name="when-are-satellite-assemblies-loaded"></a><span data-ttu-id="1e976-106">¿Cuándo se cargan los ensamblados satélite?</span><span class="sxs-lookup"><span data-stu-id="1e976-106">When are satellite assemblies loaded?</span></span>

<span data-ttu-id="1e976-107">Los ensamblados satélite se cargan al cargar un recurso localizado.</span><span class="sxs-lookup"><span data-stu-id="1e976-107">Satellite assemblies are loaded when loading a localized resource.</span></span>

<span data-ttu-id="1e976-108">La API básica para cargar recursos localizados es la clase <xref:System.Resources.ResourceManager?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1e976-108">The basic API to load localized resources is the <xref:System.Resources.ResourceManager?displayProperty=fullName> class.</span></span> <span data-ttu-id="1e976-109">En última instancia, la clase <xref:System.Resources.ResourceManager> llamará al método <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> para cada <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-109">Ultimately the <xref:System.Resources.ResourceManager> class will call the <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A> method for each <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="1e976-110">Las API de nivel alto pueden abstraer la API de nivel bajo.</span><span class="sxs-lookup"><span data-stu-id="1e976-110">Higher-level APIs may abstract the low-level API.</span></span>

## <a name="algorithm"></a><span data-ttu-id="1e976-111">Algoritmo</span><span class="sxs-lookup"><span data-stu-id="1e976-111">Algorithm</span></span>

<span data-ttu-id="1e976-112">El proceso de reserva de recursos de .NET Core conlleva los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e976-112">The .NET Core resource fallback process involves the following steps:</span></span>

1. <span data-ttu-id="1e976-113">Determine la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext> `active`.</span><span class="sxs-lookup"><span data-stu-id="1e976-113">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext> instance.</span></span> <span data-ttu-id="1e976-114">En todos los casos, la instancia de `active` es el elemento <xref:System.Runtime.Loader.AssemblyLoadContext> del ensamblado que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="1e976-114">In all cases, the `active` instance is the executing assembly's <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span>

2. <span data-ttu-id="1e976-115">La instancia de `active` intenta cargar un ensamblado satélite para la referencia cultural solicitada por orden de prioridad al realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e976-115">The `active` instance attempts to load a satellite assembly for the requested culture in priority order by:</span></span>
    - <span data-ttu-id="1e976-116">Comprobar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1e976-116">Checking its cache.</span></span>
    - <span data-ttu-id="1e976-117">Comprobar en el directorio del ensamblado actualmente en ejecución un subdirectorio que coincida con el elemento <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> solicitado (por ejemplo, `es-MX`).</span><span class="sxs-lookup"><span data-stu-id="1e976-117">Checking the directory of the currently executing assembly for a subdirectory that matches the requested <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> (for example `es-MX`).</span></span>

        > [!NOTE]
        > <span data-ttu-id="1e976-118">Esta característica no se ha implementado en .NET Core antes de la versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="1e976-118">This feature was not implemented in .NET Core before 3.0.</span></span>
        >
        > [!NOTE]
        > <span data-ttu-id="1e976-119">En Linux y macOS, el subdirectorio distingue entre mayúsculas y minúsculas y debe cumplir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1e976-119">On Linux and macOS, the subdirectory is case-sensitive and must either:</span></span>
        >
        > - <span data-ttu-id="1e976-120">Coincidir exactamente con mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1e976-120">Exactly match case.</span></span>
        > - <span data-ttu-id="1e976-121">Estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1e976-121">Be in lower case.</span></span>

    - <span data-ttu-id="1e976-122">Si `active` es la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType>, ejecutar la lógica [sondeo del ensamblado de satélite (recurso) predeterminado](default-probing.md#satellite-resource-assembly-probing).</span><span class="sxs-lookup"><span data-stu-id="1e976-122">If `active` is the <xref:System.Runtime.Loader.AssemblyLoadContext.Default?displayProperty=nameWithType> instance, by running the [default satellite (resource) assembly probing](default-probing.md#satellite-resource-assembly-probing) logic.</span></span>

    - <span data-ttu-id="1e976-123">Llamar a la función de <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-123">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType> function.</span></span>

    - <span data-ttu-id="1e976-124">Generar el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-124">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> event.</span></span>

    - <span data-ttu-id="1e976-125">Generar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-125">Raising the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>

3. <span data-ttu-id="1e976-126">Si se carga un ensamblado satélite:</span><span class="sxs-lookup"><span data-stu-id="1e976-126">If a satellite assembly is loaded:</span></span>
   - <span data-ttu-id="1e976-127">Se genera el evento <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-127">The <xref:System.AppDomain.AssemblyLoad?displayProperty=nameWithType> event is raised.</span></span>
   - <span data-ttu-id="1e976-128">Se busca en el ensamblado el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="1e976-128">The assembly is searched it for the requested resource.</span></span> <span data-ttu-id="1e976-129">Si el runtime encuentra el recurso en el ensamblado, lo usará.</span><span class="sxs-lookup"><span data-stu-id="1e976-129">If the runtime finds the resource in the assembly, it uses it.</span></span> <span data-ttu-id="1e976-130">Si no encuentra el recurso, seguirá con la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1e976-130">If it doesn't find the resource, it continues the search.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e976-131">Para buscar un recurso dentro del ensamblado satélite, el entorno de ejecución busca el archivo de recursos solicitado por <xref:System.Resources.ResourceManager> para el <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> actual.</span><span class="sxs-lookup"><span data-stu-id="1e976-131">To find a resource within the satellite assembly, the runtime searches for the resource file requested by the <xref:System.Resources.ResourceManager> for the current <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1e976-132">En el archivo de recursos, busca el nombre del recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="1e976-132">Within the resource file, it searches for the requested resource name.</span></span> <span data-ttu-id="1e976-133">Si no se encuentra ninguno, se considera que no se encontró el recurso.</span><span class="sxs-lookup"><span data-stu-id="1e976-133">If either is not found, the resource is treated as not found.</span></span>

4. <span data-ttu-id="1e976-134">Luego, el runtime busca los ensamblados de referencias culturales primarias a través de muchos niveles potenciales, y cada vez repite los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="1e976-134">The runtime next searches the parent culture assemblies through many potential levels, each time repeating steps 2 & 3.</span></span>

    <span data-ttu-id="1e976-135">Cada referencia cultural tiene solo un elemento primario, que está definido mediante la propiedad <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-135">Each culture has only one parent, which is defined by the <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType> property.</span></span>

    <span data-ttu-id="1e976-136">La búsqueda de las referencias culturales primarias se detiene cuando la propiedad <xref:System.Globalization.CultureInfo.Parent%2A> de una referencia cultural es <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-136">The search for parent cultures stops when a culture's <xref:System.Globalization.CultureInfo.Parent%2A> property is <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.</span></span>

    <span data-ttu-id="1e976-137">En el caso de <xref:System.Globalization.CultureInfo.InvariantCulture>, no se vuelve a los pasos 2 y 3, sino que continúa con el paso 5.</span><span class="sxs-lookup"><span data-stu-id="1e976-137">For the <xref:System.Globalization.CultureInfo.InvariantCulture>, we don't return to steps 2 & 3, but rather continue with step 5.</span></span>

5. <span data-ttu-id="1e976-138">Si todavía no se encuentra el recurso, se usa el recurso para la referencia cultural predeterminada (de reserva).</span><span class="sxs-lookup"><span data-stu-id="1e976-138">If the resource is still not found, the resource for the default (fallback) culture is used.</span></span>

   <span data-ttu-id="1e976-139">Normalmente, los recursos de la referencia cultural predeterminada se incluyen en el ensamblado de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="1e976-139">Typically, the resources for the default culture are included in the main application assembly.</span></span> <span data-ttu-id="1e976-140">Sin embargo, se puede especificar <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> para la propiedad <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e976-140">However, you can specify <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty=nameWithType> for the <xref:System.Resources.NeutralResourcesLanguageAttribute.Location?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1e976-141">Este valor indica que la ubicación de reserva final para los recursos es un ensamblado satélite, en lugar del ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="1e976-141">This value indicates that the ultimate fallback location for resources is a satellite assembly rather than the main assembly.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e976-142">La referencia cultural predeterminada es la reserva final.</span><span class="sxs-lookup"><span data-stu-id="1e976-142">The default culture is the ultimate fallback.</span></span> <span data-ttu-id="1e976-143">Por lo tanto, se recomienda incluir siempre un conjunto de recursos exhaustivo en el archivo de recursos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1e976-143">Therefore, we recommend that you always include an exhaustive set of resources in the default resource file.</span></span> <span data-ttu-id="1e976-144">Esto ayuda a evitar que se produzcan excepciones.</span><span class="sxs-lookup"><span data-stu-id="1e976-144">This helps prevent exceptions from being thrown.</span></span> <span data-ttu-id="1e976-145">Al tener un conjunto exhaustivo, se proporciona una reserva para todos los recursos y se garantiza que al menos un recurso esté siempre presente para el usuario, incluso si no es específico de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="1e976-145">By having an exhaustive set, you provide a fallback for all resources and ensure that at least one resource is always present for the user, even if it is not culturally specific.</span></span>

6. <span data-ttu-id="1e976-146">Por último,</span><span class="sxs-lookup"><span data-stu-id="1e976-146">Finally,</span></span>
   - <span data-ttu-id="1e976-147">si el tiempo de ejecución no encuentra un archivo de recursos para una referencia cultural predeterminada (de reserva), se produce una excepción <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException>.</span><span class="sxs-lookup"><span data-stu-id="1e976-147">If the runtime doesn't find a resource file for a default (fallback) culture, a <xref:System.Resources.MissingManifestResourceException> or <xref:System.Resources.MissingSatelliteAssemblyException> exception is thrown.</span></span>
   - <span data-ttu-id="1e976-148">Si se encuentra el archivo de recursos pero el recurso solicitado no se encuentra, la solicitud devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="1e976-148">If the resource file is found but the requested resource isn't present, the request returns `null`.</span></span>

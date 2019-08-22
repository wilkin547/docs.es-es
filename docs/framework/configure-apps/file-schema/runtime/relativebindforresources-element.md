---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 859e8a12421ea92aa48c54317e052683eb8e83f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663482"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="5997e-102">\<relativeBindForResources >, elemento</span><span class="sxs-lookup"><span data-stu-id="5997e-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="5997e-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="5997e-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="5997e-104">\<configuration> Element</span></span>  
<span data-ttu-id="5997e-105">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5997e-105">\<runtime> Element</span></span>  
<span data-ttu-id="5997e-106">\<relativeBindForResources >, elemento</span><span class="sxs-lookup"><span data-stu-id="5997e-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5997e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5997e-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5997e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5997e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5997e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5997e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5997e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5997e-110">Attributes</span></span>  
  
|<span data-ttu-id="5997e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5997e-111">Attribute</span></span>|<span data-ttu-id="5997e-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5997e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5997e-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5997e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5997e-114">Especifica si el Common Language Runtime optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5997e-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="5997e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5997e-116">Value</span><span class="sxs-lookup"><span data-stu-id="5997e-116">Value</span></span>|<span data-ttu-id="5997e-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5997e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5997e-118">El motor en tiempo de ejecución no optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="5997e-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5997e-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="5997e-120">El motor en tiempo de ejecución optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5997e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5997e-121">Child Elements</span></span>  
 <span data-ttu-id="5997e-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5997e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5997e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5997e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5997e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5997e-124">Element</span></span>|<span data-ttu-id="5997e-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5997e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5997e-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5997e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5997e-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5997e-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5997e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5997e-128">Remarks</span></span>  
 <span data-ttu-id="5997e-129">En general, Administrador de recursos sondea los recursos, tal como se documenta en el tema [empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="5997e-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="5997e-130">Esto significa que, cuando Administrador de recursos sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar en una carpeta específica de la referencia cultural en la base de código de la aplicación, Windows Installer de consulta para los ensamblados satélite y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="5997e-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="5997e-131">El `<relativeBindForResources>` elemento optimiza la manera en que administrador de recursos sondea para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="5997e-132">Puede mejorar el rendimiento al buscar recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="5997e-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="5997e-133">Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="5997e-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="5997e-134">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también se deben instalar allí.</span><span class="sxs-lookup"><span data-stu-id="5997e-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="5997e-135">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también se deben instalar en una carpeta específica de la referencia cultural en el código base.</span><span class="sxs-lookup"><span data-stu-id="5997e-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="5997e-136">Cuando Windows Installer no se usa o solo se usa con poca frecuencia para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="5997e-137">Cuando el código de aplicación no controla <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> el evento.</span><span class="sxs-lookup"><span data-stu-id="5997e-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="5997e-138">Establecer el `enabled` atributo del elemento `<relativeBindForResources>` para `true` optimizar el sondeo de administrador de recursos para los ensamblados satélite de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5997e-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="5997e-139">Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="5997e-140">No consulta Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5997e-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="5997e-141">No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="5997e-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5997e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5997e-142">See also</span></span>

- [<span data-ttu-id="5997e-143">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="5997e-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="5997e-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5997e-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5997e-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5997e-145">Configuration File Schema</span></span>](../index.md)

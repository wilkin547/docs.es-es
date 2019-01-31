---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51129f9bb3a278d32a5da723dcc339f5e918c0f4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289814"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="433e8-102">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="433e8-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="433e8-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="433e8-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="433e8-104">\<configuration> Element</span></span>  
<span data-ttu-id="433e8-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="433e8-105">\<runtime> Element</span></span>  
<span data-ttu-id="433e8-106">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="433e8-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="433e8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="433e8-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="433e8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="433e8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="433e8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="433e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="433e8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="433e8-110">Attributes</span></span>  
  
|<span data-ttu-id="433e8-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="433e8-111">Attribute</span></span>|<span data-ttu-id="433e8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="433e8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="433e8-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="433e8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="433e8-114">Especifica si common language runtime optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="433e8-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="433e8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="433e8-116">Valor</span><span class="sxs-lookup"><span data-stu-id="433e8-116">Value</span></span>|<span data-ttu-id="433e8-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="433e8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="433e8-118">El tiempo de ejecución no optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="433e8-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="433e8-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="433e8-120">El tiempo de ejecución optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="433e8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="433e8-121">Child Elements</span></span>  
 <span data-ttu-id="433e8-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="433e8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="433e8-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="433e8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="433e8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="433e8-124">Element</span></span>|<span data-ttu-id="433e8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="433e8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="433e8-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="433e8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="433e8-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="433e8-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="433e8-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="433e8-128">Remarks</span></span>  
 <span data-ttu-id="433e8-129">En general, Resource Manager sondea los recursos, como se documenta en el [empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) tema.</span><span class="sxs-lookup"><span data-stu-id="433e8-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="433e8-130">Esto significa que cuando los sondeos de administrador de recursos para una determinada versión localizada de un recurso, puede buscar en la caché global de ensamblados, busque los ensamblados satélite en una carpeta específica de la referencia cultural en la consulta de base, de código de la aplicación Windows Installer y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="433e8-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="433e8-131">El `<relativeBindForResources>` elemento optimiza la manera en que Resource Manager sondea los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="433e8-132">Puede mejorar el rendimiento cuando el sondeo para los recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="433e8-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="433e8-133">Cuando se implementa el ensamblado satélite en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="433e8-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="433e8-134">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también deben instalarse allí.</span><span class="sxs-lookup"><span data-stu-id="433e8-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="433e8-135">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también deben instalarse en una carpeta específica de la referencia cultural de la base de código.</span><span class="sxs-lookup"><span data-stu-id="433e8-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="433e8-136">Cuando Windows Installer no se usa o se usa solo en raras ocasiones para la instalación y a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="433e8-137">Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="433e8-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="433e8-138">Establecer el `enabled` atributo de la `<relativeBindForResources>` elemento `true` optimiza el sondeo del Administrador de recursos de los ensamblados satélite como sigue:</span><span class="sxs-lookup"><span data-stu-id="433e8-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="433e8-139">La ubicación del ensamblado de código principal usa para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="433e8-140">No consulta a Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="433e8-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="433e8-141">No provoca la <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="433e8-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="433e8-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="433e8-142">See also</span></span>
- [<span data-ttu-id="433e8-143">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="433e8-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="433e8-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="433e8-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="433e8-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="433e8-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

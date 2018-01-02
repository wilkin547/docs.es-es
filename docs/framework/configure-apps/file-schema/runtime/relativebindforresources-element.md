---
title: '&lt;relativeBindForResources&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8409b1fe86776397ceb3db5b338fb8aaadef9cbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltrelativebindforresourcesgt-element"></a><span data-ttu-id="4d055-102">&lt;relativeBindForResources&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="4d055-102">&lt;relativeBindForResources&gt; Element</span></span>
<span data-ttu-id="4d055-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-103">Optimizes the probe for satellite assemblies.</span></span>  
  
 <span data-ttu-id="4d055-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="4d055-104">\<configuration> Element</span></span>  
<span data-ttu-id="4d055-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="4d055-105">\<runtime> Element</span></span>  
<span data-ttu-id="4d055-106">\<relativeBindForResources > elemento</span><span class="sxs-lookup"><span data-stu-id="4d055-106">\<relativeBindForResources> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d055-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d055-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d055-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d055-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4d055-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d055-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d055-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d055-110">Attributes</span></span>  
  
|<span data-ttu-id="4d055-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d055-111">Attribute</span></span>|<span data-ttu-id="4d055-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d055-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4d055-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4d055-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d055-114">Especifica si common language runtime optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4d055-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4d055-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4d055-116">Valor</span><span class="sxs-lookup"><span data-stu-id="4d055-116">Value</span></span>|<span data-ttu-id="4d055-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d055-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4d055-118">El tiempo de ejecución no optimizar el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="4d055-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4d055-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="4d055-120">El tiempo de ejecución, optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d055-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d055-121">Child Elements</span></span>  
 <span data-ttu-id="4d055-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4d055-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d055-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d055-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4d055-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d055-124">Element</span></span>|<span data-ttu-id="4d055-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d055-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4d055-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d055-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4d055-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d055-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d055-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d055-128">Remarks</span></span>  
 <span data-ttu-id="4d055-129">En general, el Administrador de recursos sondea los recursos, como se documenta en la [empaquetar e implementar recursos](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) tema.</span><span class="sxs-lookup"><span data-stu-id="4d055-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="4d055-130">Esto significa que cuando el Administrador de recursos sondea una determinada versión localizada de un recurso, puede buscar en la caché global de ensamblados, busque los ensamblados satélite en una carpeta específica de la referencia cultural en la consulta de base de código de la aplicación Windows Installer y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="4d055-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="4d055-131">El `<relativeBindForResources>` elemento optimiza la manera en que el Administrador de recursos sondea los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="4d055-132">Puede mejorar el rendimiento cuando la búsqueda de recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="4d055-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
-   <span data-ttu-id="4d055-133">Cuando se implementa el ensamblado satélite en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="4d055-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="4d055-134">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite deben también instalarse no existe.</span><span class="sxs-lookup"><span data-stu-id="4d055-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="4d055-135">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también deben instalarse en una carpeta específica de la referencia cultural de la base de código.</span><span class="sxs-lookup"><span data-stu-id="4d055-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
-   <span data-ttu-id="4d055-136">Cuando Windows Installer no se utiliza o se usa sólo en raras ocasiones para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
-   <span data-ttu-id="4d055-137">Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="4d055-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="4d055-138">Establecer el `enabled` atributo de la `<relativeBindForResources>` elemento `true` optimiza el sondeo del Administrador de recursos de los ensamblados satélite como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4d055-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
-   <span data-ttu-id="4d055-139">La ubicación del ensamblado de código principal usa para buscar el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
-   <span data-ttu-id="4d055-140">No se consulta a Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4d055-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
-   <span data-ttu-id="4d055-141">No provoca la <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="4d055-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d055-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d055-142">See Also</span></span>  
 [<span data-ttu-id="4d055-143">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="4d055-143">Packaging and Deploying Resources</span></span>](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)  
 [<span data-ttu-id="4d055-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4d055-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="4d055-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d055-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153911"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="4f255-102">\<relativeBindForResources> Element</span><span class="sxs-lookup"><span data-stu-id="4f255-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="4f255-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="4f255-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f255-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f255-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f255-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="4f255-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span><span class="sxs-lookup"><span data-stu-id="4f255-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f255-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f255-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f255-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f255-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f255-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f255-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f255-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f255-110">Attributes</span></span>  
  
|<span data-ttu-id="4f255-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f255-111">Attribute</span></span>|<span data-ttu-id="4f255-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f255-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="4f255-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4f255-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="4f255-114">Especifica si Common Language Runtime optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="4f255-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4f255-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="4f255-116">Value</span><span class="sxs-lookup"><span data-stu-id="4f255-116">Value</span></span>|<span data-ttu-id="4f255-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f255-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4f255-118">El tiempo de ejecución no optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="4f255-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4f255-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="4f255-120">El tiempo de ejecución optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f255-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f255-121">Child Elements</span></span>  
 <span data-ttu-id="4f255-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f255-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f255-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f255-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4f255-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f255-124">Element</span></span>|<span data-ttu-id="4f255-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f255-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f255-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f255-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4f255-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f255-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f255-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4f255-128">Remarks</span></span>  
 <span data-ttu-id="4f255-129">En general, Resource Manager busca recursos, como se documenta en el tema [Empaquetado e implementación de recursos.](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)</span><span class="sxs-lookup"><span data-stu-id="4f255-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="4f255-130">Esto significa que cuando Resource Manager sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> en una carpeta específica de la referencia cultural en la base de código de la aplicación, consultar windows Installer para ensamblados satélite y generar el evento.</span><span class="sxs-lookup"><span data-stu-id="4f255-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="4f255-131">El `<relativeBindForResources>` elemento optimiza la forma en que Resource Manager sondea los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="4f255-132">Puede mejorar el rendimiento al sondear recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="4f255-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="4f255-133">Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="4f255-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="4f255-134">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también deben instalarse allí.</span><span class="sxs-lookup"><span data-stu-id="4f255-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="4f255-135">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también deben instalarse en una carpeta específica de la referencia cultural en la base de código.</span><span class="sxs-lookup"><span data-stu-id="4f255-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="4f255-136">Cuando Windows Installer no se utiliza o solo se usa raramente para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="4f255-137">Cuando el código de <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> la aplicación no controla el evento.</span><span class="sxs-lookup"><span data-stu-id="4f255-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="4f255-138">Establecer `enabled` el atributo `<relativeBindForResources>` del `true` elemento para optimizar el sondeo de Resource Manager para ensamblados satélite de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4f255-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="4f255-139">Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="4f255-140">No consulta windows Installer para ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="4f255-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="4f255-141">No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="4f255-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f255-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f255-142">See also</span></span>

- [<span data-ttu-id="4f255-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="4f255-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="4f255-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4f255-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4f255-145">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4f255-145">Configuration File Schema</span></span>](../index.md)

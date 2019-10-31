---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: 6a418fc546313b74bb965a0b223eca9c2e5acc08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115800"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="5fb32-102">\<elemento > relativeBindForResources</span><span class="sxs-lookup"><span data-stu-id="5fb32-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="5fb32-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="5fb32-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fb32-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5fb32-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fb32-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5fb32-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<relativeBindForResources >**</span><span class="sxs-lookup"><span data-stu-id="5fb32-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb32-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fb32-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fb32-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5fb32-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5fb32-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5fb32-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fb32-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5fb32-110">Attributes</span></span>  
  
|<span data-ttu-id="5fb32-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5fb32-111">Attribute</span></span>|<span data-ttu-id="5fb32-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fb32-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5fb32-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5fb32-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5fb32-114">Especifica si el Common Language Runtime optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5fb32-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="5fb32-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5fb32-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5fb32-116">Value</span></span>|<span data-ttu-id="5fb32-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fb32-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5fb32-118">El motor en tiempo de ejecución no optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="5fb32-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5fb32-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="5fb32-120">El motor en tiempo de ejecución optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fb32-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5fb32-121">Child Elements</span></span>  
 <span data-ttu-id="5fb32-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5fb32-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fb32-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5fb32-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5fb32-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5fb32-124">Element</span></span>|<span data-ttu-id="5fb32-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fb32-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5fb32-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5fb32-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5fb32-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5fb32-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fb32-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fb32-128">Remarks</span></span>  
 <span data-ttu-id="5fb32-129">En general, Administrador de recursos sondea los recursos, tal como se documenta en el tema [empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="5fb32-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="5fb32-130">Esto significa que, cuando Administrador de recursos sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar en una carpeta específica de la referencia cultural en la base de código de la aplicación, Windows Installer de consulta para los ensamblados satélite y generar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5fb32-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="5fb32-131">El elemento `<relativeBindForResources>` optimiza el modo en que Administrador de recursos sondea para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="5fb32-132">Puede mejorar el rendimiento al buscar recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="5fb32-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="5fb32-133">Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="5fb32-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="5fb32-134">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también se deben instalar allí.</span><span class="sxs-lookup"><span data-stu-id="5fb32-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="5fb32-135">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también se deben instalar en una carpeta específica de la referencia cultural en el código base.</span><span class="sxs-lookup"><span data-stu-id="5fb32-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="5fb32-136">Cuando Windows Installer no se usa o solo se usa con poca frecuencia para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="5fb32-137">Cuando el código de aplicación no controla el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5fb32-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="5fb32-138">Al establecer el atributo `enabled` del elemento `<relativeBindForResources>` en `true`, se optimiza el sondeo de Administrador de recursos para los ensamblados satélite de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fb32-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="5fb32-139">Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="5fb32-140">No consulta Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="5fb32-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="5fb32-141">No genera el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5fb32-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb32-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fb32-142">See also</span></span>

- [<span data-ttu-id="5fb32-143">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="5fb32-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="5fb32-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5fb32-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5fb32-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5fb32-145">Configuration File Schema</span></span>](../index.md)

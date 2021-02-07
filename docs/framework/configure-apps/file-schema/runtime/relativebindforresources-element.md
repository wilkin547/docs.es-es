---
description: 'Más información acerca de: <relativeBindForResources> elemento'
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: f08d8f8a8fc4bb14d28762254dca99788d44a858
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712927"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="70825-103">\<relativeBindForResources> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="70825-103">\<relativeBindForResources> Element</span></span>

<span data-ttu-id="70825-104">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-104">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="70825-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70825-105">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70825-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70825-106">Attributes and Elements</span></span>  

 <span data-ttu-id="70825-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70825-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70825-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="70825-108">Attributes</span></span>  
  
|<span data-ttu-id="70825-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="70825-109">Attribute</span></span>|<span data-ttu-id="70825-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="70825-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="70825-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="70825-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="70825-112">Especifica si el Common Language Runtime optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-112">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="70825-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="70825-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="70825-114">Value</span><span class="sxs-lookup"><span data-stu-id="70825-114">Value</span></span>|<span data-ttu-id="70825-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="70825-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="70825-116">El motor en tiempo de ejecución no optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-116">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="70825-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="70825-117">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="70825-118">El motor en tiempo de ejecución optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-118">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70825-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70825-119">Child Elements</span></span>  

 <span data-ttu-id="70825-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="70825-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70825-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70825-121">Parent Elements</span></span>  
  
|<span data-ttu-id="70825-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="70825-122">Element</span></span>|<span data-ttu-id="70825-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="70825-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="70825-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70825-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="70825-125">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70825-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70825-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70825-126">Remarks</span></span>  

 <span data-ttu-id="70825-127">En general, Administrador de recursos sondea los recursos, tal como se documenta en el tema [empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="70825-127">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="70825-128">Esto significa que, cuando Administrador de recursos sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar una carpeta específica de la referencia cultural en la base de código de la aplicación, Windows Installer de consulta para los ensamblados satélite y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="70825-128">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="70825-129">El `<relativeBindForResources>` elemento optimiza la manera en que administrador de recursos sondea para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-129">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="70825-130">Puede mejorar el rendimiento al buscar recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="70825-130">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="70825-131">Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="70825-131">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="70825-132">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también se deben instalar allí.</span><span class="sxs-lookup"><span data-stu-id="70825-132">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="70825-133">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también se deben instalar en una carpeta específica de la referencia cultural en el código base.</span><span class="sxs-lookup"><span data-stu-id="70825-133">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="70825-134">Cuando Windows Installer no se usa o solo se usa con poca frecuencia para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-134">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="70825-135">Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="70825-135">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="70825-136">Establecer el `enabled` atributo del `<relativeBindForResources>` elemento para `true` optimizar el sondeo de administrador de recursos para los ensamblados satélite de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="70825-136">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="70825-137">Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-137">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="70825-138">No consulta Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="70825-138">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="70825-139">No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="70825-139">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70825-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="70825-140">See also</span></span>

- [<span data-ttu-id="70825-141">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="70825-141">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="70825-142">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="70825-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="70825-143">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="70825-143">Configuration File Schema</span></span>](../index.md)

---
title: <relativeBindForResources> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153911"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="13ee3-102">\<relativeBindForResources> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="13ee3-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="13ee3-103">Optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="13ee3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13ee3-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13ee3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13ee3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="13ee3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13ee3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13ee3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="13ee3-107">Attributes</span></span>  
  
|<span data-ttu-id="13ee3-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="13ee3-108">Attribute</span></span>|<span data-ttu-id="13ee3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="13ee3-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="13ee3-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="13ee3-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="13ee3-111">Especifica si el Common Language Runtime optimiza el sondeo para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="13ee3-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="13ee3-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="13ee3-113">Value</span><span class="sxs-lookup"><span data-stu-id="13ee3-113">Value</span></span>|<span data-ttu-id="13ee3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="13ee3-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="13ee3-115">El motor en tiempo de ejecución no optimiza el sondeo de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="13ee3-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="13ee3-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="13ee3-117">El motor en tiempo de ejecución optimiza el sondeo de los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13ee3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13ee3-118">Child Elements</span></span>  
 <span data-ttu-id="13ee3-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13ee3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13ee3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13ee3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="13ee3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="13ee3-121">Element</span></span>|<span data-ttu-id="13ee3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="13ee3-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="13ee3-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="13ee3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="13ee3-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="13ee3-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13ee3-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13ee3-125">Remarks</span></span>  
 <span data-ttu-id="13ee3-126">En general, Administrador de recursos sondea los recursos, tal como se documenta en el tema [empaquetar e implementar recursos](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="13ee3-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="13ee3-127">Esto significa que, cuando Administrador de recursos sondea una versión localizada determinada de un recurso, puede buscar en la caché global de ensamblados, buscar una carpeta específica de la referencia cultural en la base de código de la aplicación, Windows Installer de consulta para los ensamblados satélite y generar el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="13ee3-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="13ee3-128">El `<relativeBindForResources>` elemento optimiza la manera en que administrador de recursos sondea para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="13ee3-129">Puede mejorar el rendimiento al buscar recursos en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="13ee3-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="13ee3-130">Cuando el ensamblado satélite se implementa en la misma ubicación que el ensamblado de código.</span><span class="sxs-lookup"><span data-stu-id="13ee3-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="13ee3-131">En otras palabras, si el ensamblado de código está instalado en la caché global de ensamblados, los ensamblados satélite también se deben instalar allí.</span><span class="sxs-lookup"><span data-stu-id="13ee3-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="13ee3-132">Si el ensamblado de código está instalado en la base de código de la aplicación, los ensamblados satélite también se deben instalar en una carpeta específica de la referencia cultural en el código base.</span><span class="sxs-lookup"><span data-stu-id="13ee3-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="13ee3-133">Cuando Windows Installer no se usa o solo se usa con poca frecuencia para la instalación a petición de ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="13ee3-134">Cuando el código de aplicación no controla el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="13ee3-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="13ee3-135">Establecer el `enabled` atributo del `<relativeBindForResources>` elemento para `true` optimizar el sondeo de administrador de recursos para los ensamblados satélite de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="13ee3-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="13ee3-136">Utiliza la ubicación del ensamblado de código primario para sondear el ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="13ee3-137">No consulta Windows Installer para los ensamblados satélite.</span><span class="sxs-lookup"><span data-stu-id="13ee3-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="13ee3-138">No genera el <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="13ee3-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ee3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="13ee3-139">See also</span></span>

- [<span data-ttu-id="13ee3-140">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="13ee3-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="13ee3-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="13ee3-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="13ee3-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="13ee3-142">Configuration File Schema</span></span>](../index.md)

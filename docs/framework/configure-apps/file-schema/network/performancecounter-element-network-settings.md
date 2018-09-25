---
title: '&lt;performanceCounter&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 549f3dcfd7225937fd04ad2116e2be311687861b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074945"
---
# <a name="ltperformancecountergt-element-network-settings"></a><span data-ttu-id="bac5f-102">&lt;performanceCounter&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="bac5f-102">&lt;performanceCounter&gt; Element (Network Settings)</span></span>
<span data-ttu-id="bac5f-103">Habilita o deshabilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="bac5f-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="bac5f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bac5f-104">\<configuration></span></span>  
<span data-ttu-id="bac5f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="bac5f-105">\<system.net></span></span>  
<span data-ttu-id="bac5f-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="bac5f-106">\<settings></span></span>  
<span data-ttu-id="bac5f-107">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="bac5f-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac5f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bac5f-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bac5f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bac5f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bac5f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bac5f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bac5f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bac5f-111">Attributes</span></span>  
  
|<span data-ttu-id="bac5f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="bac5f-112">Attribute</span></span>|<span data-ttu-id="bac5f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="bac5f-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bac5f-114">Especifica si se habilitan los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="bac5f-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="bac5f-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="bac5f-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bac5f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bac5f-116">Child Elements</span></span>  
 <span data-ttu-id="bac5f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bac5f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bac5f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bac5f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bac5f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bac5f-119">Element</span></span>|<span data-ttu-id="bac5f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bac5f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bac5f-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="bac5f-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="bac5f-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="bac5f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bac5f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bac5f-123">Remarks</span></span>  
 <span data-ttu-id="bac5f-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bac5f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="bac5f-125">Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará.</span><span class="sxs-lookup"><span data-stu-id="bac5f-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="bac5f-126">Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bac5f-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="bac5f-127">Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="bac5f-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="bac5f-128">Para obtener más información sobre los contadores de rendimiento de red específicas, consulte [contadores de rendimiento de red](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span><span class="sxs-lookup"><span data-stu-id="bac5f-128">For more information on the specific networking performance counters, see [Networking Performance Counters](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd).</span></span>  
  
 <span data-ttu-id="bac5f-129">El valor predeterminado es que se deshabilitan los contadores de rendimiento en la red.</span><span class="sxs-lookup"><span data-stu-id="bac5f-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="bac5f-130">El <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la **habilitado** atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="bac5f-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bac5f-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bac5f-131">Example</span></span>  
 <span data-ttu-id="bac5f-132">El ejemplo siguiente muestra cómo configurar el <xref:System.Net> y espacios de nombres para habilitar los contadores de rendimiento de red relacionados.</span><span class="sxs-lookup"><span data-stu-id="bac5f-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bac5f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bac5f-133">See Also</span></span>  
 <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bac5f-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bac5f-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="bac5f-135">Contadores de rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="bac5f-135">Networking Performance Counters</span></span>](https://msdn.microsoft.com/library/d1860235-f643-46ae-846c-ff0ed8b0e3cd)

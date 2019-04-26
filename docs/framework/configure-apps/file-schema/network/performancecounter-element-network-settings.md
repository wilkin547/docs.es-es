---
title: Elemento <performanceCounter> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 30c5cd07c92a8fc3c340cab0ff9ae74e940c0c12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705245"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="060f7-102">\<performanceCounter > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="060f7-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="060f7-103">Habilita o deshabilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="060f7-103">Enables or disables networking performance counters.</span></span>  
  
 <span data-ttu-id="060f7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="060f7-104">\<configuration></span></span>  
<span data-ttu-id="060f7-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="060f7-105">\<system.net></span></span>  
<span data-ttu-id="060f7-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="060f7-106">\<settings></span></span>  
<span data-ttu-id="060f7-107">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="060f7-107">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060f7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="060f7-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="060f7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="060f7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="060f7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="060f7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="060f7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="060f7-111">Attributes</span></span>  
  
|<span data-ttu-id="060f7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="060f7-112">Attribute</span></span>|<span data-ttu-id="060f7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="060f7-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="060f7-114">Especifica si se habilitan los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="060f7-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="060f7-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="060f7-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="060f7-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="060f7-116">Child Elements</span></span>  
 <span data-ttu-id="060f7-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="060f7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="060f7-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="060f7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="060f7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="060f7-119">Element</span></span>|<span data-ttu-id="060f7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="060f7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="060f7-121">settings</span><span class="sxs-lookup"><span data-stu-id="060f7-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="060f7-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="060f7-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="060f7-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="060f7-123">Remarks</span></span>  
 <span data-ttu-id="060f7-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="060f7-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="060f7-125">Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará.</span><span class="sxs-lookup"><span data-stu-id="060f7-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="060f7-126">Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="060f7-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="060f7-127">Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="060f7-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="060f7-128">Para obtener más información sobre los contadores de rendimiento de red específicas, consulte [contadores de rendimiento de red](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span><span class="sxs-lookup"><span data-stu-id="060f7-128">For more information on the specific networking performance counters, see [Networking Performance Counters](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking).</span></span>  
  
 <span data-ttu-id="060f7-129">El valor predeterminado es que se deshabilitan los contadores de rendimiento en la red.</span><span class="sxs-lookup"><span data-stu-id="060f7-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="060f7-130">El <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad puede usarse para obtener el valor actual de la **habilitado** atributo desde archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="060f7-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="060f7-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="060f7-131">Example</span></span>  
 <span data-ttu-id="060f7-132">El ejemplo siguiente muestra cómo configurar el <xref:System.Net> y espacios de nombres para habilitar los contadores de rendimiento de red relacionados.</span><span class="sxs-lookup"><span data-stu-id="060f7-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="060f7-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="060f7-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="060f7-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="060f7-134">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="060f7-135">Contadores de rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="060f7-135">Networking Performance Counters</span></span>](../../../../../docs/framework/debug-trace-profile/performance-counters.md#networking)

---
description: 'Más información acerca de: <performanceCounters> elemento (configuración de red)'
title: Elemento <performanceCounters> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: a923ba2420bd15e33f4564a196854fdf9e130e12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804119"
---
# <a name="performancecounters-element-network-settings"></a><span data-ttu-id="5161c-103">Elemento \<performanceCounters> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5161c-103">\<performanceCounters> Element (Network Settings)</span></span>

<span data-ttu-id="5161c-104">Habilita o deshabilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="5161c-104">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="5161c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5161c-105">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5161c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5161c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5161c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5161c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5161c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5161c-108">Attributes</span></span>  
  
|<span data-ttu-id="5161c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5161c-109">Attribute</span></span>|<span data-ttu-id="5161c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5161c-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5161c-111">Especifica si los contadores de rendimiento de red están habilitados.</span><span class="sxs-lookup"><span data-stu-id="5161c-111">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="5161c-112">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="5161c-112">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5161c-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5161c-113">Child Elements</span></span>  

 <span data-ttu-id="5161c-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5161c-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5161c-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5161c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="5161c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5161c-116">Element</span></span>|<span data-ttu-id="5161c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5161c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5161c-118">settings</span><span class="sxs-lookup"><span data-stu-id="5161c-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="5161c-119">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="5161c-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5161c-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5161c-120">Remarks</span></span>  

 <span data-ttu-id="5161c-121">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5161c-121">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="5161c-122">Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará.</span><span class="sxs-lookup"><span data-stu-id="5161c-122">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="5161c-123">Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5161c-123">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="5161c-124">Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="5161c-124">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="5161c-125">Para obtener más información sobre los contadores de rendimiento de red específicos, vea [contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span><span class="sxs-lookup"><span data-stu-id="5161c-125">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="5161c-126">El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="5161c-126">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="5161c-127">La <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="5161c-127">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5161c-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5161c-128">Example</span></span>  

 <span data-ttu-id="5161c-129">En el ejemplo siguiente se muestra cómo configurar el <xref:System.Net> y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="5161c-129">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5161c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5161c-130">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5161c-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5161c-131">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5161c-132">Contadores de rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="5161c-132">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)

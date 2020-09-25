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
ms.openlocfilehash: 4859f3a9e6de4f1bf8a56212bfe01f94d66f5650
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190246"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="17933-102">Elemento \<performanceCounter> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="17933-102">\<performanceCounter> Element (Network Settings)</span></span>

<span data-ttu-id="17933-103">Habilita o deshabilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="17933-103">Enables or disables networking performance counters.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**

## <a name="syntax"></a><span data-ttu-id="17933-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17933-104">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17933-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="17933-105">Attributes and Elements</span></span>  

 <span data-ttu-id="17933-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="17933-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17933-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="17933-107">Attributes</span></span>  
  
|<span data-ttu-id="17933-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="17933-108">Attribute</span></span>|<span data-ttu-id="17933-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="17933-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="17933-110">Especifica si los contadores de rendimiento de red están habilitados.</span><span class="sxs-lookup"><span data-stu-id="17933-110">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="17933-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="17933-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17933-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="17933-112">Child Elements</span></span>  

 <span data-ttu-id="17933-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="17933-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17933-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="17933-114">Parent Elements</span></span>  
  
|<span data-ttu-id="17933-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="17933-115">Element</span></span>|<span data-ttu-id="17933-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="17933-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17933-117">settings</span><span class="sxs-lookup"><span data-stu-id="17933-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="17933-118">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="17933-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17933-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17933-119">Remarks</span></span>  

 <span data-ttu-id="17933-120">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="17933-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="17933-121">Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará.</span><span class="sxs-lookup"><span data-stu-id="17933-121">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="17933-122">Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="17933-122">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="17933-123">Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="17933-123">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="17933-124">Para obtener más información sobre los contadores de rendimiento de red específicos, vea [contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span><span class="sxs-lookup"><span data-stu-id="17933-124">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="17933-125">El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="17933-125">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="17933-126">La <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> propiedad se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="17933-126">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17933-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17933-127">Example</span></span>  

 <span data-ttu-id="17933-128">En el ejemplo siguiente se muestra cómo configurar el <xref:System.Net> y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="17933-128">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17933-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17933-129">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="17933-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="17933-130">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="17933-131">Contadores de rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="17933-131">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)

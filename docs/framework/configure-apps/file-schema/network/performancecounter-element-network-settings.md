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
ms.openlocfilehash: 58a2bf5118a3a2cd9c33301eca5dcc751c2351bf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283091"
---
# <a name="performancecounter-element-network-settings"></a><span data-ttu-id="c192f-102">\<elemento > performanceCounter (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c192f-102">\<performanceCounter> Element (Network Settings)</span></span>
<span data-ttu-id="c192f-103">Habilita o deshabilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="c192f-103">Enables or disables networking performance counters.</span></span>  

<span data-ttu-id="c192f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c192f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c192f-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c192f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c192f-106">&nbsp;&nbsp;[ \**&nbsp;&nbsp;\<>\** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c192f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\</span></span>
<span data-ttu-id="c192f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<performanceCounters >**</span><span class="sxs-lookup"><span data-stu-id="c192f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c192f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c192f-108">Syntax</span></span>  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c192f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c192f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c192f-110">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c192f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c192f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c192f-111">Attributes</span></span>  
  
|<span data-ttu-id="c192f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c192f-112">Attribute</span></span>|<span data-ttu-id="c192f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c192f-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c192f-114">Especifica si los contadores de rendimiento de red están habilitados.</span><span class="sxs-lookup"><span data-stu-id="c192f-114">Specifies whether the networking performance counters are enabled.</span></span> <span data-ttu-id="c192f-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="c192f-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c192f-116">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="c192f-116">Child Elements</span></span>  
 <span data-ttu-id="c192f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c192f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c192f-118">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="c192f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c192f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c192f-119">Element</span></span>|<span data-ttu-id="c192f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c192f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c192f-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="c192f-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="c192f-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="c192f-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c192f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c192f-123">Remarks</span></span>  
 <span data-ttu-id="c192f-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c192f-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="c192f-125">Los contadores de rendimiento de red deben estar habilitados en el archivo de configuración que se usará.</span><span class="sxs-lookup"><span data-stu-id="c192f-125">Networking performance counters need to be enabled in the configuration file to be used.</span></span> <span data-ttu-id="c192f-126">Todos los contadores de rendimiento red se habilitan o deshabilitan con un solo valor en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c192f-126">All networking performance counters are enabled or disabled with a single setting in the configuration file.</span></span> <span data-ttu-id="c192f-127">Los contadores de rendimiento de red individuales no pueden habilitarse ni deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="c192f-127">Individual networking performance counters cannot be enabled or disabled.</span></span> <span data-ttu-id="c192f-128">Para obtener más información sobre los contadores de rendimiento de red específicos, vea [contadores de rendimiento de red](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span><span class="sxs-lookup"><span data-stu-id="c192f-128">For more information on the specific networking performance counters, see [Networking performance counters](../../../debug-trace-profile/performance-counters.md#networking-performance-counters).</span></span>  
  
 <span data-ttu-id="c192f-129">El valor predeterminado es que los contadores de rendimiento de red están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="c192f-129">The default value is that networking performance counters are disabled.</span></span>  
  
 <span data-ttu-id="c192f-130">La propiedad <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> se puede utilizar para obtener el valor actual del atributo **Enabled** de los archivos de configuración aplicables.</span><span class="sxs-lookup"><span data-stu-id="c192f-130">The <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType> property can be used to get the current value of the **enabled** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c192f-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c192f-131">Example</span></span>  
 <span data-ttu-id="c192f-132">En el ejemplo siguiente se muestra cómo configurar el <xref:System.Net> y los espacios de nombres relacionados para habilitar los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="c192f-132">The following example shows how to configure the <xref:System.Net> and related namespaces to enable networking performance counters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c192f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c192f-133">See also</span></span>

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c192f-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c192f-134">Network Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c192f-135">Contadores de rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="c192f-135">Networking Performance Counters</span></span>](../../../debug-trace-profile/performance-counters.md#networking-performance-counters)

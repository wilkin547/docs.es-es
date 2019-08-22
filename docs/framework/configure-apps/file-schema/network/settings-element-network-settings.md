---
title: Elemento <settings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 12797e2f06d03aacd81700eae57d5776c1a6f354
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663992"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="4fab5-102">\<Elemento > de configuración (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4fab5-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="4fab5-103">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4fab5-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="4fab5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4fab5-104">\<configuration></span></span>  
<span data-ttu-id="4fab5-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4fab5-105">\<system.net></span></span>  
<span data-ttu-id="4fab5-106">\<> de configuración</span><span class="sxs-lookup"><span data-stu-id="4fab5-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fab5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fab5-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fab5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4fab5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4fab5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4fab5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fab5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4fab5-110">Attributes</span></span>  
 <span data-ttu-id="4fab5-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4fab5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fab5-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4fab5-112">Child Elements</span></span>  
  
|<span data-ttu-id="4fab5-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fab5-113">Element</span></span>|<span data-ttu-id="4fab5-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4fab5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fab5-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="4fab5-115">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="4fab5-116">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="4fab5-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="4fab5-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="4fab5-117">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="4fab5-118">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="4fab5-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="4fab5-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="4fab5-119">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="4fab5-120">Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="4fab5-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="4fab5-121">\<Elemento > performanceCounter (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4fab5-121">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="4fab5-122">Habilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="4fab5-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="4fab5-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="4fab5-123">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="4fab5-124">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="4fab5-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="4fab5-125">tomacorriente</span><span class="sxs-lookup"><span data-stu-id="4fab5-125">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="4fab5-126">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="4fab5-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="4fab5-127">\<webProxyScript > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4fab5-127">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="4fab5-128">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="4fab5-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fab5-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4fab5-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4fab5-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fab5-130">Element</span></span>|<span data-ttu-id="4fab5-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4fab5-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fab5-132">system.net</span><span class="sxs-lookup"><span data-stu-id="4fab5-132">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="4fab5-133">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="4fab5-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fab5-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fab5-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4fab5-135">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4fab5-135">Configuration Files</span></span>  
 <span data-ttu-id="4fab5-136">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4fab5-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fab5-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fab5-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="4fab5-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="4fab5-138">Network Settings Schema</span></span>](index.md)

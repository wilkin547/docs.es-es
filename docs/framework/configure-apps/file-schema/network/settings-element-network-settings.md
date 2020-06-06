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
ms.openlocfilehash: d510c445c585a36005ed415b14188efc4be03984
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089115"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="515ac-102">Elemento \<settings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="515ac-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="515ac-103">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="515ac-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="515ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="515ac-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="515ac-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="515ac-105">Attributes and Elements</span></span>  
 <span data-ttu-id="515ac-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="515ac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="515ac-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="515ac-107">Attributes</span></span>  
 <span data-ttu-id="515ac-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="515ac-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="515ac-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="515ac-109">Child Elements</span></span>  
  
|<span data-ttu-id="515ac-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="515ac-110">Element</span></span>|<span data-ttu-id="515ac-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="515ac-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="515ac-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="515ac-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="515ac-113">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="515ac-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="515ac-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="515ac-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="515ac-115">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="515ac-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="515ac-116">Protocolo</span><span class="sxs-lookup"><span data-stu-id="515ac-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="515ac-117">Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="515ac-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="515ac-118">\<performanceCounter>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="515ac-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="515ac-119">Habilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="515ac-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="515ac-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="515ac-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="515ac-121">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="515ac-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="515ac-122">tomacorriente</span><span class="sxs-lookup"><span data-stu-id="515ac-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="515ac-123">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="515ac-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="515ac-124">\<webProxyScript>(Elemento, configuración de red)</span><span class="sxs-lookup"><span data-stu-id="515ac-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="515ac-125">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="515ac-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="515ac-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="515ac-126">Parent Elements</span></span>  
  
|<span data-ttu-id="515ac-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="515ac-127">Element</span></span>|<span data-ttu-id="515ac-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="515ac-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="515ac-129">system.net</span><span class="sxs-lookup"><span data-stu-id="515ac-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="515ac-130">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="515ac-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="515ac-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="515ac-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="515ac-132">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="515ac-132">Configuration Files</span></span>  
 <span data-ttu-id="515ac-133">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="515ac-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515ac-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="515ac-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="515ac-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="515ac-135">Network Settings Schema</span></span>](index.md)

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
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167280"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="13600-102">Elemento \<settings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="13600-102">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="13600-103">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="13600-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="13600-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13600-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13600-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13600-105">Attributes and Elements</span></span>  

 <span data-ttu-id="13600-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13600-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13600-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="13600-107">Attributes</span></span>  

 <span data-ttu-id="13600-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13600-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13600-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13600-109">Child Elements</span></span>  
  
|<span data-ttu-id="13600-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="13600-110">Element</span></span>|<span data-ttu-id="13600-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="13600-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13600-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="13600-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="13600-113">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="13600-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="13600-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="13600-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="13600-115">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="13600-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="13600-116">Protocolo</span><span class="sxs-lookup"><span data-stu-id="13600-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="13600-117">Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="13600-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="13600-118">Elemento \<performanceCounter> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="13600-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="13600-119">Habilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="13600-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="13600-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="13600-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="13600-121">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="13600-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="13600-122">tomacorriente</span><span class="sxs-lookup"><span data-stu-id="13600-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="13600-123">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="13600-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="13600-124">Elemento \<webProxyScript> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="13600-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="13600-125">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="13600-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13600-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13600-126">Parent Elements</span></span>  
  
|<span data-ttu-id="13600-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="13600-127">Element</span></span>|<span data-ttu-id="13600-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="13600-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13600-129">system.net</span><span class="sxs-lookup"><span data-stu-id="13600-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="13600-130">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="13600-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13600-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13600-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="13600-132">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="13600-132">Configuration Files</span></span>  

 <span data-ttu-id="13600-133">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="13600-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13600-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13600-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="13600-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="13600-135">Network Settings Schema</span></span>](index.md)

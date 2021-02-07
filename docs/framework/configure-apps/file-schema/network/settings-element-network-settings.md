---
description: 'Más información acerca de: <settings> elemento (configuración de red)'
title: Elemento <settings> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: e6ed242e68ac9a9e2c20067d66681bbcd51fcc50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712979"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="c988e-103">Elemento \<settings> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c988e-103">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="c988e-104">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c988e-104">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="c988e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c988e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c988e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c988e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c988e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c988e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c988e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c988e-108">Attributes</span></span>  

 <span data-ttu-id="c988e-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c988e-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c988e-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c988e-110">Child Elements</span></span>  
  
|<span data-ttu-id="c988e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="c988e-111">Element</span></span>|<span data-ttu-id="c988e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c988e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c988e-113">httpListener</span><span class="sxs-lookup"><span data-stu-id="c988e-113">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="c988e-114">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="c988e-114">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="c988e-115">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="c988e-115">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="c988e-116">Personaliza los parámetros de la solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="c988e-116">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="c988e-117">Protocolo</span><span class="sxs-lookup"><span data-stu-id="c988e-117">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="c988e-118">Habilita la compatibilidad con el protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="c988e-118">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="c988e-119">Elemento \<performanceCounter> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c988e-119">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="c988e-120">Habilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="c988e-120">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="c988e-121">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="c988e-121">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="c988e-122">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="c988e-122">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="c988e-123">tomacorriente</span><span class="sxs-lookup"><span data-stu-id="c988e-123">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="c988e-124">Especifica si las operaciones de socket utilizan puertos de finalización.</span><span class="sxs-lookup"><span data-stu-id="c988e-124">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="c988e-125">Elemento \<webProxyScript> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c988e-125">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="c988e-126">Configura las características del script que se usan para detectar los proxies Web.</span><span class="sxs-lookup"><span data-stu-id="c988e-126">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c988e-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c988e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c988e-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="c988e-128">Element</span></span>|<span data-ttu-id="c988e-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="c988e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c988e-130">system.net</span><span class="sxs-lookup"><span data-stu-id="c988e-130">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="c988e-131">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="c988e-131">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c988e-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c988e-132">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c988e-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c988e-133">Configuration Files</span></span>  

 <span data-ttu-id="c988e-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c988e-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c988e-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c988e-135">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="c988e-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c988e-136">Network Settings Schema</span></span>](index.md)

---
title: '&lt;configuración de&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: 7db55dd9d2ca79342cadb2320d08ca9235223def
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671859"
---
# <a name="ltsettingsgt-element-network-settings"></a><span data-ttu-id="1cdce-102">&lt;configuración de&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1cdce-102">&lt;settings&gt; Element (Network Settings)</span></span>
<span data-ttu-id="1cdce-103">Configura opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1cdce-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="1cdce-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1cdce-104">\<configuration></span></span>  
<span data-ttu-id="1cdce-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="1cdce-105">\<system.net></span></span>  
<span data-ttu-id="1cdce-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="1cdce-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cdce-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cdce-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1cdce-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1cdce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1cdce-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1cdce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1cdce-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1cdce-110">Attributes</span></span>  
 <span data-ttu-id="1cdce-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1cdce-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1cdce-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1cdce-112">Child Elements</span></span>  
  
|<span data-ttu-id="1cdce-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cdce-113">Element</span></span>|<span data-ttu-id="1cdce-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cdce-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cdce-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="1cdce-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="1cdce-116">Personaliza los parámetros utilizados por la <xref:System.Net.HttpListener> clase.</span><span class="sxs-lookup"><span data-stu-id="1cdce-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="1cdce-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="1cdce-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="1cdce-118">Personaliza los parámetros de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="1cdce-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="1cdce-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="1cdce-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="1cdce-120">Habilita el protocolo de Internet versión 6 (IPv6) admite.</span><span class="sxs-lookup"><span data-stu-id="1cdce-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="1cdce-121">\<performanceCounter > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1cdce-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="1cdce-122">Habilita los contadores de rendimiento de red.</span><span class="sxs-lookup"><span data-stu-id="1cdce-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="1cdce-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="1cdce-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="1cdce-124">Configura las conexiones a los recursos de red.</span><span class="sxs-lookup"><span data-stu-id="1cdce-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="1cdce-125">socket</span><span class="sxs-lookup"><span data-stu-id="1cdce-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="1cdce-126">Especifica si las operaciones de socket utilizan puertos de terminación.</span><span class="sxs-lookup"><span data-stu-id="1cdce-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="1cdce-127">\<webProxyScript > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="1cdce-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="1cdce-128">Configura las características de la secuencia de comandos que se usa para detectar a servidores proxy Web.</span><span class="sxs-lookup"><span data-stu-id="1cdce-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1cdce-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1cdce-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1cdce-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="1cdce-130">Element</span></span>|<span data-ttu-id="1cdce-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cdce-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1cdce-132">system.net</span><span class="sxs-lookup"><span data-stu-id="1cdce-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="1cdce-133">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="1cdce-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cdce-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cdce-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1cdce-135">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1cdce-135">Configuration Files</span></span>  
 <span data-ttu-id="1cdce-136">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1cdce-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cdce-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cdce-137">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="1cdce-138">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="1cdce-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

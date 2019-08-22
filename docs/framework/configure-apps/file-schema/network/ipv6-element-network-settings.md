---
title: Elemento <ipv6> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: d89c2e2c6943aca38f8a71092ba3121447a77574
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664093"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="73c56-102">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="73c56-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="73c56-103">Habilita las respuestas del Protocolo de Internet versión 6 (IPv6) de los miembros <xref:System.Net.Dns> obsoletos de la clase.</span><span class="sxs-lookup"><span data-stu-id="73c56-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="73c56-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73c56-104">\<configuration></span></span>  
<span data-ttu-id="73c56-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="73c56-105">\<system.net></span></span>  
<span data-ttu-id="73c56-106">\<> de configuración</span><span class="sxs-lookup"><span data-stu-id="73c56-106">\<settings></span></span>  
<span data-ttu-id="73c56-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="73c56-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73c56-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73c56-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73c56-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73c56-109">Attributes and Elements</span></span>  
 <span data-ttu-id="73c56-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73c56-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73c56-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="73c56-111">Attributes</span></span>  
  
|<span data-ttu-id="73c56-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="73c56-112">**Attribute**</span></span>|<span data-ttu-id="73c56-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73c56-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="73c56-114">Especifica si los miembros de <xref:System.Net.Dns> la clase devuelven direcciones del Protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="73c56-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="73c56-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73c56-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73c56-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73c56-116">Child Elements</span></span>  
 <span data-ttu-id="73c56-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73c56-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73c56-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73c56-118">Parent Elements</span></span>  
  
|<span data-ttu-id="73c56-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="73c56-119">**Element**</span></span>|<span data-ttu-id="73c56-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73c56-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73c56-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="73c56-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="73c56-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="73c56-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73c56-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73c56-123">Remarks</span></span>  
 <span data-ttu-id="73c56-124">Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos <xref:System.Net.Dns> de la <xref:System.Net.Dns.BeginGetHostByName%2A>clase <xref:System.Net.Dns.BeginResolve%2A>: <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>,, <xref:System.Net.Dns.Resolve%2A>y.</span><span class="sxs-lookup"><span data-stu-id="73c56-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="73c56-125">Para otros miembros del <xref:System.Net?displayProperty=nameWithType> espacio de nombres, es posible que se devuelvan direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="73c56-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73c56-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="73c56-126">Configuration Files</span></span>  
 <span data-ttu-id="73c56-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="73c56-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73c56-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73c56-128">Example</span></span>  
 <span data-ttu-id="73c56-129">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con <xref:System.Net.Dns> IPv6 para la clase.</span><span class="sxs-lookup"><span data-stu-id="73c56-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73c56-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="73c56-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="73c56-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="73c56-131">Network Settings Schema</span></span>](index.md)

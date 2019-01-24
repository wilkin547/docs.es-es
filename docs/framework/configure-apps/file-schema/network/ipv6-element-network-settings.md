---
title: '&lt;IPv6&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 1ca1bb6a0b1a9c3deab9cb3ba15e9b3b2c29f1f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531894"
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="56a30-102">&lt;IPv6&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="56a30-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="56a30-103">Habilita el protocolo de Internet versión 6 (IPv6) las respuestas de miembros obsoletos de la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="56a30-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="56a30-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="56a30-104">\<configuration></span></span>  
<span data-ttu-id="56a30-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="56a30-105">\<system.net></span></span>  
<span data-ttu-id="56a30-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="56a30-106">\<settings></span></span>  
<span data-ttu-id="56a30-107">\<ipv6></span><span class="sxs-lookup"><span data-stu-id="56a30-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56a30-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56a30-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56a30-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="56a30-109">Attributes and Elements</span></span>  
 <span data-ttu-id="56a30-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="56a30-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56a30-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="56a30-111">Attributes</span></span>  
  
|<span data-ttu-id="56a30-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="56a30-112">**Attribute**</span></span>|<span data-ttu-id="56a30-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="56a30-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="56a30-114">Especifica si los miembros de la <xref:System.Net.Dns> clase devolver el protocolo de Internet versión 6 (IPv6) las direcciones.</span><span class="sxs-lookup"><span data-stu-id="56a30-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="56a30-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="56a30-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56a30-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="56a30-116">Child Elements</span></span>  
 <span data-ttu-id="56a30-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="56a30-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56a30-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="56a30-118">Parent Elements</span></span>  
  
|<span data-ttu-id="56a30-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="56a30-119">**Element**</span></span>|<span data-ttu-id="56a30-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="56a30-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="56a30-121">settings</span><span class="sxs-lookup"><span data-stu-id="56a30-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="56a30-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="56a30-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56a30-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56a30-123">Remarks</span></span>  
 <span data-ttu-id="56a30-124">Esta configuración habilita la compatibilidad de IPv6 para los miembros obsoletos de la <xref:System.Net.Dns> clase: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, y <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="56a30-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="56a30-125">Para otros miembros de la <xref:System.Net?displayProperty=nameWithType> espacio de nombres, se pueden devolver direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="56a30-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="56a30-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="56a30-126">Configuration Files</span></span>  
 <span data-ttu-id="56a30-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="56a30-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56a30-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56a30-128">Example</span></span>  
 <span data-ttu-id="56a30-129">El ejemplo siguiente muestra cómo habilitar la compatibilidad con IPv6 para el <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="56a30-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56a30-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="56a30-130">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="56a30-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="56a30-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

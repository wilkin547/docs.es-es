---
title: "&lt;IPv6&gt; elemento (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dd5366b4110d9ec2290e2669919575e07e8ec98a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltipv6gt-element-network-settings"></a><span data-ttu-id="dc250-102">&lt;IPv6&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="dc250-102">&lt;ipv6&gt; Element (Network Settings)</span></span>
<span data-ttu-id="dc250-103">Habilita el protocolo de Internet versión 6 (IPv6) las respuestas de miembros obsoletos de la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="dc250-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
 <span data-ttu-id="dc250-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dc250-104">\<configuration></span></span>  
<span data-ttu-id="dc250-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="dc250-105">\<system.net></span></span>  
<span data-ttu-id="dc250-106">\<Configuración ></span><span class="sxs-lookup"><span data-stu-id="dc250-106">\<settings></span></span>  
<span data-ttu-id="dc250-107">\<IPv6 ></span><span class="sxs-lookup"><span data-stu-id="dc250-107">\<ipv6></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc250-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc250-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc250-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc250-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dc250-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc250-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc250-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc250-111">Attributes</span></span>  
  
|<span data-ttu-id="dc250-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="dc250-112">**Attribute**</span></span>|<span data-ttu-id="dc250-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dc250-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="dc250-114">Especifica si los miembros de la <xref:System.Net.Dns> clase devolver protocolo de Internet versión 6 (IPv6) las direcciones.</span><span class="sxs-lookup"><span data-stu-id="dc250-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="dc250-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="dc250-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc250-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc250-116">Child Elements</span></span>  
 <span data-ttu-id="dc250-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc250-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc250-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc250-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc250-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="dc250-119">**Element**</span></span>|<span data-ttu-id="dc250-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="dc250-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dc250-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="dc250-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="dc250-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="dc250-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc250-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc250-123">Remarks</span></span>  
 <span data-ttu-id="dc250-124">Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos de la <xref:System.Net.Dns> clase: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, y <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="dc250-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="dc250-125">Para otros miembros de la <xref:System.Net?displayProperty=nameWithType> espacio de nombres, se pueden devolver direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dc250-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="dc250-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="dc250-126">Configuration Files</span></span>  
 <span data-ttu-id="dc250-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="dc250-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc250-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc250-128">Example</span></span>  
 <span data-ttu-id="dc250-129">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con IPv6 para el <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="dc250-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc250-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc250-130">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="dc250-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="dc250-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

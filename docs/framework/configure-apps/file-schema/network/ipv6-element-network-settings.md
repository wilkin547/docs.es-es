---
description: 'Más información acerca de: <ipv6> elemento (configuración de red)'
title: Elemento <ipv6> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 667acaebdb290140f67ea36020bb191cd1a44f34
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698653"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="e78ae-103">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e78ae-103">\<ipv6> Element (Network Settings)</span></span>

<span data-ttu-id="e78ae-104">Habilita las respuestas del Protocolo de Internet versión 6 (IPv6) de los miembros obsoletos de la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="e78ae-104">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="e78ae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e78ae-105">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e78ae-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e78ae-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e78ae-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e78ae-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e78ae-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e78ae-108">Attributes</span></span>  
  
|<span data-ttu-id="e78ae-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="e78ae-109">**Attribute**</span></span>|<span data-ttu-id="e78ae-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e78ae-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="e78ae-111">Especifica si los miembros de la <xref:System.Net.Dns> clase devuelven direcciones del Protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="e78ae-111">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="e78ae-112">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e78ae-112">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e78ae-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e78ae-113">Child Elements</span></span>  

 <span data-ttu-id="e78ae-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e78ae-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e78ae-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e78ae-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e78ae-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="e78ae-116">**Element**</span></span>|<span data-ttu-id="e78ae-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e78ae-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e78ae-118">settings</span><span class="sxs-lookup"><span data-stu-id="e78ae-118">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e78ae-119">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e78ae-119">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e78ae-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e78ae-120">Remarks</span></span>  

 <span data-ttu-id="e78ae-121">Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos de la <xref:System.Net.Dns> clase: <xref:System.Net.Dns.BeginGetHostByName%2A> , <xref:System.Net.Dns.BeginResolve%2A> , <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> , <xref:System.Net.Dns.GetHostByAddress%2A> , <xref:System.Net.Dns.GetHostByName%2A> y <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="e78ae-121">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="e78ae-122">Para otros miembros del <xref:System.Net?displayProperty=nameWithType> espacio de nombres, es posible que se devuelvan direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e78ae-122">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e78ae-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e78ae-123">Configuration Files</span></span>  

 <span data-ttu-id="e78ae-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e78ae-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e78ae-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e78ae-125">Example</span></span>  

 <span data-ttu-id="e78ae-126">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con IPv6 para la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="e78ae-126">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e78ae-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e78ae-127">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e78ae-128">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e78ae-128">Network Settings Schema</span></span>](index.md)

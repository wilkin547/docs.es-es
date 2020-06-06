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
ms.openlocfilehash: c16949171d082bd02abb0a02db83c2e71c2f17df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088131"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="ca999-102">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="ca999-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="ca999-103">Habilita las respuestas del Protocolo de Internet versión 6 (IPv6) de los miembros obsoletos de la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="ca999-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**

## <a name="syntax"></a><span data-ttu-id="ca999-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca999-104">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca999-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca999-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ca999-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca999-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca999-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca999-107">Attributes</span></span>  
  
|<span data-ttu-id="ca999-108">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="ca999-108">**Attribute**</span></span>|<span data-ttu-id="ca999-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca999-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="ca999-110">Especifica si los miembros de la <xref:System.Net.Dns> clase devuelven direcciones del Protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="ca999-110">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="ca999-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="ca999-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca999-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca999-112">Child Elements</span></span>  
 <span data-ttu-id="ca999-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ca999-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca999-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca999-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ca999-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="ca999-115">**Element**</span></span>|<span data-ttu-id="ca999-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca999-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ca999-117">settings</span><span class="sxs-lookup"><span data-stu-id="ca999-117">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="ca999-118">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="ca999-118">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca999-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca999-119">Remarks</span></span>  
 <span data-ttu-id="ca999-120">Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos de la <xref:System.Net.Dns> clase: <xref:System.Net.Dns.BeginGetHostByName%2A> , <xref:System.Net.Dns.BeginResolve%2A> , <xref:System.Net.Dns.EndGetHostByName%2A> , <xref:System.Net.Dns.EndResolve%2A> , <xref:System.Net.Dns.GetHostByAddress%2A> , <xref:System.Net.Dns.GetHostByName%2A> y <xref:System.Net.Dns.Resolve%2A> .</span><span class="sxs-lookup"><span data-stu-id="ca999-120">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="ca999-121">Para otros miembros del <xref:System.Net?displayProperty=nameWithType> espacio de nombres, es posible que se devuelvan direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ca999-121">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ca999-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ca999-122">Configuration Files</span></span>  
 <span data-ttu-id="ca999-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ca999-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca999-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca999-124">Example</span></span>  
 <span data-ttu-id="ca999-125">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con IPv6 para la <xref:System.Net.Dns> clase.</span><span class="sxs-lookup"><span data-stu-id="ca999-125">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca999-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca999-126">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ca999-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="ca999-127">Network Settings Schema</span></span>](index.md)

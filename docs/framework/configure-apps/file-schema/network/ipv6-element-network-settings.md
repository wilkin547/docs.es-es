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
ms.openlocfilehash: bf04b16682c2c1bc677fecbd6dc966090c77e1da
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698130"
---
# <a name="ipv6-element-network-settings"></a><span data-ttu-id="bc47b-102">Elemento \<ipv6> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="bc47b-102">\<ipv6> Element (Network Settings)</span></span>
<span data-ttu-id="bc47b-103">Habilita las respuestas del Protocolo de Internet versión 6 (IPv6) de los miembros obsoletos de la clase <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="bc47b-103">Enables Internet Protocol version 6 (IPv6) responses from obsolete members of the <xref:System.Net.Dns> class.</span></span>  
  
[<span data-ttu-id="bc47b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="bc47b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="bc47b-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bc47b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="bc47b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bc47b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="bc47b-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<ipv6 >**</span><span class="sxs-lookup"><span data-stu-id="bc47b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ipv6>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc47b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc47b-108">Syntax</span></span>  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc47b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bc47b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bc47b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bc47b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc47b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bc47b-111">Attributes</span></span>  
  
|<span data-ttu-id="bc47b-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="bc47b-112">**Attribute**</span></span>|<span data-ttu-id="bc47b-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc47b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`enabled`|<span data-ttu-id="bc47b-114">Especifica si los miembros de la clase <xref:System.Net.Dns> devuelven direcciones del Protocolo de Internet versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="bc47b-114">Specifies whether members of the <xref:System.Net.Dns> class return Internet Protocol version 6 (IPv6) addresses.</span></span> <span data-ttu-id="bc47b-115">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="bc47b-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc47b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bc47b-116">Child Elements</span></span>  
 <span data-ttu-id="bc47b-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bc47b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc47b-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bc47b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="bc47b-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="bc47b-119">**Element**</span></span>|<span data-ttu-id="bc47b-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc47b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bc47b-121">Configuración</span><span class="sxs-lookup"><span data-stu-id="bc47b-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="bc47b-122">Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="bc47b-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc47b-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc47b-123">Remarks</span></span>  
 <span data-ttu-id="bc47b-124">Esta configuración habilita la compatibilidad con IPv6 para los miembros obsoletos de la clase <xref:System.Net.Dns>: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A> y <xref:System.Net.Dns.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="bc47b-124">This setting enables IPv6 support for the obsolete members of the <xref:System.Net.Dns> class: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, and <xref:System.Net.Dns.Resolve%2A>.</span></span> <span data-ttu-id="bc47b-125">Para otros miembros del espacio de nombres <xref:System.Net?displayProperty=nameWithType>, se pueden devolver direcciones IPv6 si IPv6 está habilitado en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bc47b-125">For other members of the <xref:System.Net?displayProperty=nameWithType> namespace, IPv6 addresses may be returned if IPv6 is enabled in the operating system.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bc47b-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bc47b-126">Configuration Files</span></span>  
 <span data-ttu-id="bc47b-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bc47b-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc47b-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc47b-128">Example</span></span>  
 <span data-ttu-id="bc47b-129">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con IPv6 para la clase <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="bc47b-129">The following example shows how to enable IPv6 support for the <xref:System.Net.Dns> class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc47b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc47b-130">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bc47b-131">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bc47b-131">Network Settings Schema</span></span>](index.md)

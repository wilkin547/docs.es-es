---
title: Elemento <bypasslist> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 7a6c1282c9ca8381d2dbb21ffdc82f95732c42b3
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087523"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="c6c6e-102">\<BypassList > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c6c6e-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="c6c6e-103">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="c6c6e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6c6e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6c6e-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6c6e-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="c6c6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="c6c6e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="c6c6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bypasslist >**</span><span class="sxs-lookup"><span data-stu-id="c6c6e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c6c6e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6c6e-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6c6e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c6c6e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6c6e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6c6e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c6c6e-111">Attributes</span></span>  
 <span data-ttu-id="c6c6e-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c6c6e-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c6c6e-113">Child Elements</span></span>  
  
|<span data-ttu-id="c6c6e-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="c6c6e-114">**Element**</span></span>|<span data-ttu-id="c6c6e-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c6c6e-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6c6e-116">add</span><span class="sxs-lookup"><span data-stu-id="c6c6e-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c6c6e-117">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="c6c6e-118">clear</span><span class="sxs-lookup"><span data-stu-id="c6c6e-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c6c6e-119">Borra la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="c6c6e-120">remove</span><span class="sxs-lookup"><span data-stu-id="c6c6e-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c6c6e-121">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6c6e-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c6c6e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c6c6e-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="c6c6e-123">**Element**</span></span>|<span data-ttu-id="c6c6e-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c6c6e-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c6c6e-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c6c6e-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c6c6e-126">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="c6c6e-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6c6e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6c6e-127">Remarks</span></span>  
 <span data-ttu-id="c6c6e-128">La lista de omisión contiene expresiones regulares que describen los URI que <xref:System.Net.WebRequest> instancias acceden directamente en lugar de a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="c6c6e-129">Debe tener precaución al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="c6c6e-130">La expresión regular "[a-z] +\\. contoso\\. com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="c6c6e-131">Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-z] +\\. contoso\\. com $".</span><span class="sxs-lookup"><span data-stu-id="c6c6e-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="c6c6e-132">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c6c6e-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c6c6e-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c6c6e-133">Configuration Files</span></span>  
 <span data-ttu-id="c6c6e-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c6c6e-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c6e-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6c6e-135">Example</span></span>  
 <span data-ttu-id="c6c6e-136">En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="c6c6e-137">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192,168.</span><span class="sxs-lookup"><span data-stu-id="c6c6e-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6c6e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6c6e-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c6c6e-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c6c6e-139">Network Settings Schema</span></span>](index.md)

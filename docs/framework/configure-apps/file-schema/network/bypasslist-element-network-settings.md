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
ms.openlocfilehash: 97e69a4978aa4700d13a994619a65312cf70aeaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154951"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="8aa5b-102">\<bypasslist> Element (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="8aa5b-103">Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

<span data-ttu-id="8aa5b-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8aa5b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="8aa5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8aa5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="8aa5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de lista de derivación**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8aa5b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8aa5b-108">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aa5b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8aa5b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8aa5b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aa5b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8aa5b-111">Attributes</span></span>  
 <span data-ttu-id="8aa5b-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8aa5b-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8aa5b-113">Child Elements</span></span>  
  
|<span data-ttu-id="8aa5b-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-114">**Element**</span></span>|<span data-ttu-id="8aa5b-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8aa5b-116">agregar</span><span class="sxs-lookup"><span data-stu-id="8aa5b-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8aa5b-117">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="8aa5b-118">Claro</span><span class="sxs-lookup"><span data-stu-id="8aa5b-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8aa5b-119">Borra la lista de derivación.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="8aa5b-120">quitar</span><span class="sxs-lookup"><span data-stu-id="8aa5b-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="8aa5b-121">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8aa5b-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8aa5b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8aa5b-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-123">**Element**</span></span>|<span data-ttu-id="8aa5b-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8aa5b-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8aa5b-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="8aa5b-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="8aa5b-126">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="8aa5b-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8aa5b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8aa5b-127">Remarks</span></span>  
 <span data-ttu-id="8aa5b-128">La lista de omisión contiene <xref:System.Net.WebRequest> expresiones regulares que describen los URI a los que las instancias tienen acceso directamente en lugar de a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="8aa5b-129">Debe tener cuidado al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="8aa5b-130">La expresión regular "[a-z]+\\.contoso\\.com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="8aa5b-131">Para que solo coincida con un host del dominio contoso.com, use un\\delimitador\\("$"): "[a-z]+ .contoso .com$".</span><span class="sxs-lookup"><span data-stu-id="8aa5b-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="8aa5b-132">Para obtener más información acerca de las expresiones regulares, consulte . [Expresiones regulares de .NET Framework](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="8aa5b-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8aa5b-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8aa5b-133">Configuration Files</span></span>  
 <span data-ttu-id="8aa5b-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8aa5b-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8aa5b-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8aa5b-135">Example</span></span>  
 <span data-ttu-id="8aa5b-136">En el ejemplo siguiente se agregan dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="8aa5b-137">El primero omite el proxy para todos los servidores del dominio contoso.com; el segundo omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192.168.</span><span class="sxs-lookup"><span data-stu-id="8aa5b-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8aa5b-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8aa5b-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="8aa5b-139">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="8aa5b-139">Network Settings Schema</span></span>](index.md)

---
title: Elemento <bypasslist> (configuración de red)
description: El <bypasslist> elemento de configuración de red proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy en el .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: 0a03b391c839b7255fdd423a305d474d0e48ad39
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259361"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="c45d2-103">Elemento \<bypasslist> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c45d2-103">\<bypasslist> Element (Network Settings)</span></span>

<span data-ttu-id="c45d2-104">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="c45d2-104">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bypasslist>**

## <a name="syntax"></a><span data-ttu-id="c45d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c45d2-105">Syntax</span></span>  
  
```xml  
<bypasslist>
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c45d2-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c45d2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c45d2-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c45d2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c45d2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c45d2-108">Attributes</span></span>  

 <span data-ttu-id="c45d2-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c45d2-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c45d2-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c45d2-110">Child Elements</span></span>  
  
|<span data-ttu-id="c45d2-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="c45d2-111">**Element**</span></span>|<span data-ttu-id="c45d2-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c45d2-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c45d2-113">add</span><span class="sxs-lookup"><span data-stu-id="c45d2-113">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c45d2-114">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="c45d2-114">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="c45d2-115">clear</span><span class="sxs-lookup"><span data-stu-id="c45d2-115">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c45d2-116">Borra la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="c45d2-116">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="c45d2-117">remove</span><span class="sxs-lookup"><span data-stu-id="c45d2-117">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="c45d2-118">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="c45d2-118">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c45d2-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c45d2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c45d2-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="c45d2-120">**Element**</span></span>|<span data-ttu-id="c45d2-121">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c45d2-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c45d2-122">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="c45d2-122">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="c45d2-123">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="c45d2-123">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c45d2-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c45d2-124">Remarks</span></span>  

 <span data-ttu-id="c45d2-125">La lista de omisión contiene expresiones regulares que describen <xref:System.Net.WebRequest> los URI a los que las instancias tienen acceso directamente en lugar de a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="c45d2-125">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="c45d2-126">Debe tener precaución al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="c45d2-126">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="c45d2-127">La expresión regular `[a-z]+\\.contoso\\.com` coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.CPANDL.com.</span><span class="sxs-lookup"><span data-stu-id="c45d2-127">The regular expression `[a-z]+\\.contoso\\.com` matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="c45d2-128">Para que solo coincida con un host del dominio contoso.com, use un delimitador ( `$` ): `[a-z]+\\.contoso\\.com$` .</span><span class="sxs-lookup"><span data-stu-id="c45d2-128">To match only a host in the contoso.com domain, use an anchor (`$`): `[a-z]+\\.contoso\\.com$`.</span></span>
  
 <span data-ttu-id="c45d2-129">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c45d2-129">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c45d2-130">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c45d2-130">Configuration Files</span></span>  

 <span data-ttu-id="c45d2-131">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c45d2-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c45d2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c45d2-132">Example</span></span>  

 <span data-ttu-id="c45d2-133">En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="c45d2-133">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="c45d2-134">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192,168.</span><span class="sxs-lookup"><span data-stu-id="c45d2-134">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c45d2-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c45d2-135">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="c45d2-136">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c45d2-136">Network Settings Schema</span></span>](index.md)

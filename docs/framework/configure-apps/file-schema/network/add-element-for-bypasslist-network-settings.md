---
title: Elemento <add> para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 927a43f352fd776d9e6ba52ebea6ba2a1ccd4d48
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149496"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="ca3e2-102">Elemento \<add> para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="ca3e2-102">\<add> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="ca3e2-103">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="ca3e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca3e2-104">Syntax</span></span>  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca3e2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca3e2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ca3e2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca3e2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca3e2-107">Attributes</span></span>  
  
|<span data-ttu-id="ca3e2-108">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-108">**Attribute**</span></span>|<span data-ttu-id="ca3e2-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-109">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="ca3e2-110">**address**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-110">**address**</span></span>|<span data-ttu-id="ca3e2-111">Expresión regular que describe una dirección IP o un nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-111">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca3e2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca3e2-112">Child Elements</span></span>  

 <span data-ttu-id="ca3e2-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca3e2-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca3e2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ca3e2-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-115">**Element**</span></span>|<span data-ttu-id="ca3e2-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ca3e2-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ca3e2-117">bypasslist</span><span class="sxs-lookup"><span data-stu-id="ca3e2-117">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="ca3e2-118">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-118">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca3e2-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca3e2-119">Remarks</span></span>  

 <span data-ttu-id="ca3e2-120">El `add` elemento inserta expresiones regulares que describen las direcciones IP o los nombres de servidor DNS en la lista de direcciones que omiten un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-120">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="ca3e2-121">El valor del `address` atributo debe ser una expresión regular que describa un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-121">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="ca3e2-122">Debe tener precaución al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-122">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="ca3e2-123">La expresión regular "[a-z] + \\ . contoso \\ . com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.CPANDL.com.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-123">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="ca3e2-124">Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-z] + \\ . contoso \\ . com $".</span><span class="sxs-lookup"><span data-stu-id="ca3e2-124">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="ca3e2-125">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ca3e2-125">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ca3e2-126">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ca3e2-126">Configuration Files</span></span>  

 <span data-ttu-id="ca3e2-127">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ca3e2-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca3e2-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca3e2-128">Example</span></span>  

 <span data-ttu-id="ca3e2-129">En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-129">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="ca3e2-130">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuya dirección IP comienza con 192,168.</span><span class="sxs-lookup"><span data-stu-id="ca3e2-130">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca3e2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca3e2-131">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ca3e2-132">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="ca3e2-132">Network Settings Schema</span></span>](index.md)

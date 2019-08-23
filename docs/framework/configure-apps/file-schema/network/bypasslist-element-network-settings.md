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
ms.openlocfilehash: bd746f07b4c4eb08bf34b01d555b5799d9af0cf3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927475"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="d2457-102">\<BypassList > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d2457-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="d2457-103">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="d2457-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="d2457-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d2457-104">\<configuration></span></span>  
<span data-ttu-id="d2457-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d2457-105">\<system.net></span></span>  
<span data-ttu-id="d2457-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="d2457-106">\<defaultProxy></span></span>  
<span data-ttu-id="d2457-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="d2457-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2457-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2457-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2457-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2457-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d2457-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d2457-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2457-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2457-111">Attributes</span></span>  
 <span data-ttu-id="d2457-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2457-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2457-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2457-113">Child Elements</span></span>  
  
|<span data-ttu-id="d2457-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="d2457-114">**Element**</span></span>|<span data-ttu-id="d2457-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d2457-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d2457-116">add</span><span class="sxs-lookup"><span data-stu-id="d2457-116">add</span></span>](add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="d2457-117">Agrega una dirección IP o un nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="d2457-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="d2457-118">clear</span><span class="sxs-lookup"><span data-stu-id="d2457-118">clear</span></span>](clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="d2457-119">Borra la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="d2457-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="d2457-120">remove</span><span class="sxs-lookup"><span data-stu-id="d2457-120">remove</span></span>](remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="d2457-121">Quita una dirección IP o un nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="d2457-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2457-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2457-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d2457-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="d2457-123">**Element**</span></span>|<span data-ttu-id="d2457-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d2457-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d2457-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="d2457-125">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="d2457-126">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="d2457-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2457-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2457-127">Remarks</span></span>  
 <span data-ttu-id="d2457-128">La lista de omisión contiene expresiones regulares que describen los <xref:System.Net.WebRequest> URI a los que las instancias tienen acceso directamente en lugar de a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="d2457-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="d2457-129">Debe tener precaución al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="d2457-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="d2457-130">La expresión regular "[a-z] +\\. contoso\\. com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.CPANDL.com.</span><span class="sxs-lookup"><span data-stu-id="d2457-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="d2457-131">Para que solo coincida con un host del dominio contoso.com, use un delimitador ("$"): "[a-\\z]\\+. contoso. com $".</span><span class="sxs-lookup"><span data-stu-id="d2457-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="d2457-132">Para obtener más información acerca de las expresiones regulares, vea. [.NET Framework expresiones regulares](../../../../standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d2457-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d2457-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d2457-133">Configuration Files</span></span>  
 <span data-ttu-id="d2457-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d2457-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2457-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2457-135">Example</span></span>  
 <span data-ttu-id="d2457-136">En el ejemplo siguiente se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="d2457-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="d2457-137">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuyas direcciones IP comienzan con 192,168.</span><span class="sxs-lookup"><span data-stu-id="d2457-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2457-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2457-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="d2457-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d2457-139">Network Settings Schema</span></span>](index.md)

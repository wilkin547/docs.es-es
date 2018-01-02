---
title: '&lt;bypasslist&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 20e3676e69357dc73433876275cb2737ee235552
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="bf99a-102">&lt;bypasslist&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="bf99a-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="bf99a-103">Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan a un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bf99a-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="bf99a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bf99a-104">\<configuration></span></span>  
<span data-ttu-id="bf99a-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="bf99a-105">\<system.net></span></span>  
<span data-ttu-id="bf99a-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="bf99a-106">\<defaultProxy></span></span>  
<span data-ttu-id="bf99a-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="bf99a-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf99a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf99a-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf99a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf99a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bf99a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf99a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf99a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf99a-111">Attributes</span></span>  
 <span data-ttu-id="bf99a-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bf99a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf99a-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf99a-113">Child Elements</span></span>  
  
|<span data-ttu-id="bf99a-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="bf99a-114">**Element**</span></span>|<span data-ttu-id="bf99a-115">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bf99a-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bf99a-116">add</span><span class="sxs-lookup"><span data-stu-id="bf99a-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="bf99a-117">Agrega una dirección IP o nombre DNS a la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="bf99a-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="bf99a-118">clear</span><span class="sxs-lookup"><span data-stu-id="bf99a-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="bf99a-119">Borra la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="bf99a-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="bf99a-120">remove</span><span class="sxs-lookup"><span data-stu-id="bf99a-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="bf99a-121">Quita una dirección IP o nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="bf99a-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf99a-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf99a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bf99a-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="bf99a-123">**Element**</span></span>|<span data-ttu-id="bf99a-124">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bf99a-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bf99a-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="bf99a-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="bf99a-126">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="bf99a-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf99a-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf99a-127">Remarks</span></span>  
 <span data-ttu-id="bf99a-128">La lista de omisión contiene expresiones regulares que describen las direcciones URI que <xref:System.Net.WebRequest> instancias directamente en lugar de tener acceso a través del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bf99a-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="bf99a-129">Debe tener cuidado al especificar una expresión regular para este elemento.</span><span class="sxs-lookup"><span data-stu-id="bf99a-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="bf99a-130">La expresión regular "[a-z] +\\.contoso\\.com" coincide con cualquier host del dominio contoso.com, pero también coincide con cualquier host del dominio contoso.com.cpandl.com.</span><span class="sxs-lookup"><span data-stu-id="bf99a-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="bf99a-131">Para buscar sólo un host en el dominio contoso.com, utilice un delimitador ("$"): "[a-z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="bf99a-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="bf99a-132">Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bf99a-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="bf99a-133">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bf99a-133">Configuration Files</span></span>  
 <span data-ttu-id="bf99a-134">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="bf99a-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf99a-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf99a-135">Example</span></span>  
 <span data-ttu-id="bf99a-136">En el ejemplo siguiente se agrega dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="bf99a-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="bf99a-137">La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuyas direcciones IP comienzan con 192.168.</span><span class="sxs-lookup"><span data-stu-id="bf99a-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf99a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf99a-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="bf99a-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bf99a-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

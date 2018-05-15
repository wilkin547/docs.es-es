---
title: '&lt;quitar&gt; elemento para bypasslist (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5c7918048743d53d8523ec399d1a11c67152a2bf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="38d8f-102">&lt;quitar&gt; elemento para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="38d8f-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="38d8f-103">Quita una dirección IP o nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="38d8f-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="38d8f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38d8f-104">\<configuration></span></span>  
<span data-ttu-id="38d8f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="38d8f-105">\<system.net></span></span>  
<span data-ttu-id="38d8f-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="38d8f-106">\<defaultProxy></span></span>  
<span data-ttu-id="38d8f-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="38d8f-107">\<bypasslist></span></span>  
<span data-ttu-id="38d8f-108">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="38d8f-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d8f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38d8f-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38d8f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38d8f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="38d8f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38d8f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38d8f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="38d8f-112">Attributes</span></span>  
  
|<span data-ttu-id="38d8f-113">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="38d8f-113">**Attribute**</span></span>|<span data-ttu-id="38d8f-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="38d8f-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="38d8f-115">Una expresión regular que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="38d8f-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38d8f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38d8f-116">Child Elements</span></span>  
 <span data-ttu-id="38d8f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="38d8f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38d8f-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38d8f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="38d8f-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="38d8f-119">**Element**</span></span>|<span data-ttu-id="38d8f-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="38d8f-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38d8f-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="38d8f-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="38d8f-122">Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan a un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="38d8f-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38d8f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38d8f-123">Remarks</span></span>  
 <span data-ttu-id="38d8f-124">El `remove` elemento quita expresiones regulares que describen direcciones IP o nombres de los servidores DNS de la lista de direcciones que omiten un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="38d8f-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="38d8f-125">Las direcciones se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="38d8f-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="38d8f-126">El valor de la `address` atributo debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="38d8f-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="38d8f-127">Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="38d8f-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="38d8f-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="38d8f-128">Configuration Files</span></span>  
 <span data-ttu-id="38d8f-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="38d8f-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38d8f-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38d8f-130">Example</span></span>  
 <span data-ttu-id="38d8f-131">En el ejemplo siguiente se quita cualquier definición anterior para el dominio adventure-works.com y, a continuación, agrega el dominio contoso.com a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="38d8f-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38d8f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="38d8f-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="38d8f-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="38d8f-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

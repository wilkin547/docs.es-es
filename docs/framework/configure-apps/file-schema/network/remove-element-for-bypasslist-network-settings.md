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
ms.openlocfilehash: b6c72d9780088fddcaa59e644ff8069afbb4e43d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397103"
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="2f9db-102">&lt;quitar&gt; elemento para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="2f9db-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="2f9db-103">Quita una dirección IP o nombre DNS de la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="2f9db-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="2f9db-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f9db-104">\<configuration></span></span>  
<span data-ttu-id="2f9db-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="2f9db-105">\<system.net></span></span>  
<span data-ttu-id="2f9db-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="2f9db-106">\<defaultProxy></span></span>  
<span data-ttu-id="2f9db-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="2f9db-107">\<bypasslist></span></span>  
<span data-ttu-id="2f9db-108">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="2f9db-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9db-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f9db-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f9db-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f9db-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f9db-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f9db-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f9db-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f9db-112">Attributes</span></span>  
  
|<span data-ttu-id="2f9db-113">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="2f9db-113">**Attribute**</span></span>|<span data-ttu-id="2f9db-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2f9db-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="2f9db-115">Una expresión regular que describe una dirección IP o nombre DNS.</span><span class="sxs-lookup"><span data-stu-id="2f9db-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f9db-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f9db-116">Child Elements</span></span>  
 <span data-ttu-id="2f9db-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f9db-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f9db-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f9db-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2f9db-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="2f9db-119">**Element**</span></span>|<span data-ttu-id="2f9db-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2f9db-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f9db-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="2f9db-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="2f9db-122">Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.</span><span class="sxs-lookup"><span data-stu-id="2f9db-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f9db-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f9db-123">Remarks</span></span>  
 <span data-ttu-id="2f9db-124">El `remove` elemento quita expresiones regulares que describen direcciones IP o nombres de servidor DNS en la lista de direcciones que omitir un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2f9db-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="2f9db-125">Las direcciones definidas anteriormente en el archivo de configuración o en un nivel superior de la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="2f9db-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="2f9db-126">El valor de la `address` atributo debe ser una expresión regular que describe un conjunto de direcciones IP o nombres de host.</span><span class="sxs-lookup"><span data-stu-id="2f9db-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="2f9db-127">Para obtener más información sobre las expresiones regulares, vea. [Expresiones regulares de .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2f9db-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2f9db-128">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2f9db-128">Configuration Files</span></span>  
 <span data-ttu-id="2f9db-129">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2f9db-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f9db-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f9db-130">Example</span></span>  
 <span data-ttu-id="2f9db-131">El ejemplo siguiente quita cualquier definición anterior para el dominio adventure-works.com y, a continuación, agrega el dominio contoso.com a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="2f9db-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f9db-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f9db-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="2f9db-133">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="2f9db-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

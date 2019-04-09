---
title: <clear> Elemento para bypasslist (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203527"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="19ea4-102">\<Borrar > elemento para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="19ea4-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="19ea4-103">Borra la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="19ea4-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="19ea4-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="19ea4-104">\<configuration></span></span>  
<span data-ttu-id="19ea4-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="19ea4-105">\<system.net></span></span>  
<span data-ttu-id="19ea4-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="19ea4-106">\<defaultProxy></span></span>  
<span data-ttu-id="19ea4-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="19ea4-107">\<bypasslist></span></span>  
<span data-ttu-id="19ea4-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="19ea4-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ea4-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19ea4-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19ea4-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="19ea4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19ea4-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="19ea4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19ea4-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="19ea4-112">Attributes</span></span>  
 <span data-ttu-id="19ea4-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="19ea4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19ea4-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="19ea4-114">Child Elements</span></span>  
 <span data-ttu-id="19ea4-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="19ea4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19ea4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="19ea4-116">Parent Elements</span></span>  
  
|**<span data-ttu-id="19ea4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="19ea4-117">Element</span></span>**|**<span data-ttu-id="19ea4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="19ea4-118">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="19ea4-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="19ea4-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="19ea4-120">Proporciona un conjunto de expresiones regulares que describen direcciones que no se usa a un proxy.</span><span class="sxs-lookup"><span data-stu-id="19ea4-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ea4-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19ea4-121">Remarks</span></span>  
 <span data-ttu-id="19ea4-122">El `clear` elemento borra todas las entradas de la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="19ea4-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="19ea4-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="19ea4-123">Configuration Files</span></span>  
 <span data-ttu-id="19ea4-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="19ea4-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ea4-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19ea4-125">Example</span></span>  
 <span data-ttu-id="19ea4-126">El siguiente ejemplo borra la lista de omisión y, a continuación, agrega dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="19ea4-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="19ea4-127">La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuya dirección IP comienza con 192.168.</span><span class="sxs-lookup"><span data-stu-id="19ea4-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="19ea4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="19ea4-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="19ea4-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="19ea4-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

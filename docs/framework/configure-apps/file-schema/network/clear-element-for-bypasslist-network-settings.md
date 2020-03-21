---
title: Elemento <clear> para bypasslist (configuración de red)
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
ms.openlocfilehash: c25477c2c99be66b34b07e1f7e50115bfa8d14e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154938"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="625ad-102">\<borrar> Elemento para bypasslist (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="625ad-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="625ad-103">Borra la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="625ad-103">Clears the proxy bypass list.</span></span>  
  
<span data-ttu-id="625ad-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="625ad-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="625ad-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="625ad-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="625ad-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="625ad-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="625ad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>de lista de derivación**](bypasslist-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="625ad-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)</span></span>\
<span data-ttu-id="625ad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="625ad-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="625ad-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="625ad-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="625ad-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="625ad-110">Attributes and Elements</span></span>  
 <span data-ttu-id="625ad-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="625ad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="625ad-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="625ad-112">Attributes</span></span>  
 <span data-ttu-id="625ad-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="625ad-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="625ad-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="625ad-114">Child Elements</span></span>  
 <span data-ttu-id="625ad-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="625ad-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="625ad-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="625ad-116">Parent Elements</span></span>  
  
|<span data-ttu-id="625ad-117">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="625ad-117">**Element**</span></span>|<span data-ttu-id="625ad-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="625ad-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="625ad-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="625ad-119">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="625ad-120">Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="625ad-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="625ad-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="625ad-121">Remarks</span></span>  
 <span data-ttu-id="625ad-122">El `clear` elemento borra todas las entradas de la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="625ad-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="625ad-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="625ad-123">Configuration Files</span></span>  
 <span data-ttu-id="625ad-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="625ad-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="625ad-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="625ad-125">Example</span></span>  
 <span data-ttu-id="625ad-126">En el ejemplo siguiente se borra la lista de omisión y, a continuación, se agregan dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="625ad-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="625ad-127">El primero omite el proxy para todos los servidores del dominio contoso.com; el segundo omite el proxy para todos los servidores cuya dirección IP comienza con 192.168.</span><span class="sxs-lookup"><span data-stu-id="625ad-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="625ad-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="625ad-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="625ad-129">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="625ad-129">Network Settings Schema</span></span>](index.md)

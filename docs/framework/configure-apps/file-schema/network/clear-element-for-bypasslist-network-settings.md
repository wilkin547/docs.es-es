---
description: 'Más información sobre: <clear> elemento para BypassList (configuración de red)'
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
ms.openlocfilehash: 4ddb66c837c55391a19826c44c6df7a3e88c8e0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729905"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="5a1c6-103">Elemento \<clear> para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5a1c6-103">\<clear> Element for bypasslist (Network Settings)</span></span>

<span data-ttu-id="5a1c6-104">Borra la lista de omisión del proxy.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-104">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="5a1c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a1c6-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a1c6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a1c6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="5a1c6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a1c6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a1c6-108">Attributes</span></span>  

 <span data-ttu-id="5a1c6-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a1c6-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a1c6-110">Child Elements</span></span>  

 <span data-ttu-id="5a1c6-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a1c6-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a1c6-112">Parent Elements</span></span>  
  
|<span data-ttu-id="5a1c6-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="5a1c6-113">**Element**</span></span>|<span data-ttu-id="5a1c6-114">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5a1c6-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5a1c6-115">bypasslist</span><span class="sxs-lookup"><span data-stu-id="5a1c6-115">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="5a1c6-116">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-116">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a1c6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a1c6-117">Remarks</span></span>  

 <span data-ttu-id="5a1c6-118">El `clear` elemento borra todas las entradas de la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-118">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5a1c6-119">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5a1c6-119">Configuration Files</span></span>  

 <span data-ttu-id="5a1c6-120">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5a1c6-120">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1c6-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a1c6-121">Example</span></span>  

 <span data-ttu-id="5a1c6-122">En el siguiente ejemplo se borra la lista de omisión y, a continuación, se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-122">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="5a1c6-123">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuya dirección IP comienza con 192,168.</span><span class="sxs-lookup"><span data-stu-id="5a1c6-123">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5a1c6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a1c6-124">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="5a1c6-125">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5a1c6-125">Network Settings Schema</span></span>](index.md)

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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154938"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="48e71-102">Elemento \<clear> para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="48e71-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="48e71-103">Borra la lista de omisión del proxy.</span><span class="sxs-lookup"><span data-stu-id="48e71-103">Clears the proxy bypass list.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bypasslist>**](bypasslist-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="48e71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48e71-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48e71-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48e71-105">Attributes and Elements</span></span>  
 <span data-ttu-id="48e71-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48e71-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48e71-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="48e71-107">Attributes</span></span>  
 <span data-ttu-id="48e71-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48e71-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48e71-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48e71-109">Child Elements</span></span>  
 <span data-ttu-id="48e71-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48e71-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48e71-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48e71-111">Parent Elements</span></span>  
  
|<span data-ttu-id="48e71-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="48e71-112">**Element**</span></span>|<span data-ttu-id="48e71-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="48e71-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48e71-114">bypasslist</span><span class="sxs-lookup"><span data-stu-id="48e71-114">bypasslist</span></span>](bypasslist-element-network-settings.md)|<span data-ttu-id="48e71-115">Proporciona un conjunto de expresiones regulares que describen las direcciones que no utilizan un proxy.</span><span class="sxs-lookup"><span data-stu-id="48e71-115">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48e71-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48e71-116">Remarks</span></span>  
 <span data-ttu-id="48e71-117">El `clear` elemento borra todas las entradas de la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="48e71-117">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="48e71-118">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="48e71-118">Configuration Files</span></span>  
 <span data-ttu-id="48e71-119">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="48e71-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e71-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48e71-120">Example</span></span>  
 <span data-ttu-id="48e71-121">En el siguiente ejemplo se borra la lista de omisión y, a continuación, se agregan dos direcciones a la lista de omisiones.</span><span class="sxs-lookup"><span data-stu-id="48e71-121">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="48e71-122">El primero omite el proxy para todos los servidores del dominio contoso.com; la segunda omite el proxy para todos los servidores cuya dirección IP comienza con 192,168.</span><span class="sxs-lookup"><span data-stu-id="48e71-122">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48e71-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48e71-123">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="48e71-124">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="48e71-124">Network Settings Schema</span></span>](index.md)

---
title: "&lt;Borrar&gt; elemento para bypasslist (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5ee20b9177d519010c40351e335973dce10256f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="e9259-102">&lt;Borrar&gt; elemento para bypasslist (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="e9259-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="e9259-103">Borra la lista de omisión de proxy.</span><span class="sxs-lookup"><span data-stu-id="e9259-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="e9259-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e9259-104">\<configuration></span></span>  
<span data-ttu-id="e9259-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="e9259-105">\<system.net></span></span>  
<span data-ttu-id="e9259-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="e9259-106">\<defaultProxy></span></span>  
<span data-ttu-id="e9259-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="e9259-107">\<bypasslist></span></span>  
<span data-ttu-id="e9259-108">\<Borrar ></span><span class="sxs-lookup"><span data-stu-id="e9259-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9259-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9259-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9259-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e9259-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e9259-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e9259-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9259-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e9259-112">Attributes</span></span>  
 <span data-ttu-id="e9259-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9259-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9259-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e9259-114">Child Elements</span></span>  
 <span data-ttu-id="e9259-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9259-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9259-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e9259-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e9259-117">**Element**</span><span class="sxs-lookup"><span data-stu-id="e9259-117">**Element**</span></span>|<span data-ttu-id="e9259-118">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e9259-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e9259-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="e9259-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="e9259-120">Proporciona un conjunto de expresiones regulares que describen direcciones que no utilizan a un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="e9259-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9259-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9259-121">Remarks</span></span>  
 <span data-ttu-id="e9259-122">El `clear` elemento borra todas las entradas de la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="e9259-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e9259-123">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e9259-123">Configuration Files</span></span>  
 <span data-ttu-id="e9259-124">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e9259-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9259-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9259-125">Example</span></span>  
 <span data-ttu-id="e9259-126">En el ejemplo siguiente se borra la lista de omisión y, a continuación, se agrega dos direcciones a la lista de omisión.</span><span class="sxs-lookup"><span data-stu-id="e9259-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="e9259-127">La primera omite al proxy para todos los servidores en el dominio contoso.com; la segunda omite al proxy para todos los servidores cuya dirección IP comienza con 192.168.</span><span class="sxs-lookup"><span data-stu-id="e9259-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9259-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9259-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="e9259-129">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="e9259-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

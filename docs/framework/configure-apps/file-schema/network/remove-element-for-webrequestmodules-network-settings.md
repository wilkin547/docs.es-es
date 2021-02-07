---
description: 'Más información sobre: <remove> elemento para webRequestModules (configuración de red)'
title: Elemento <remove> para webRequestModules (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: db65c91417af2538e27b65e0ae28d06a6bfcde0a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713005"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="adfb6-103">Elemento \<remove> para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="adfb6-103">\<remove> Element for webRequestModules (Network Settings)</span></span>

<span data-ttu-id="adfb6-104">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="adfb6-104">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="adfb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adfb6-105">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adfb6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="adfb6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="adfb6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="adfb6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adfb6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="adfb6-108">Attributes</span></span>  
  
|<span data-ttu-id="adfb6-109">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="adfb6-109">**Attribute**</span></span>|<span data-ttu-id="adfb6-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adfb6-110">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="adfb6-111">El prefijo URI para las solicitudes controladas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="adfb6-111">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adfb6-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="adfb6-112">Child Elements</span></span>  

 <span data-ttu-id="adfb6-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="adfb6-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adfb6-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="adfb6-114">Parent Elements</span></span>  
  
|<span data-ttu-id="adfb6-115">**Element**</span><span class="sxs-lookup"><span data-stu-id="adfb6-115">**Element**</span></span>|<span data-ttu-id="adfb6-116">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="adfb6-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="adfb6-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="adfb6-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="adfb6-118">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="adfb6-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adfb6-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="adfb6-119">Remarks</span></span>  

 <span data-ttu-id="adfb6-120">El `remove` elemento quita el módulo de solicitud Web registrado para el prefijo de URI especificado.</span><span class="sxs-lookup"><span data-stu-id="adfb6-120">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="adfb6-121">El valor del `prefix` atributo debe ser el carácter inicial de un URI válido (por ejemplo, " `http` " o " `http://www.contoso.com` ").</span><span class="sxs-lookup"><span data-stu-id="adfb6-121">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="adfb6-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="adfb6-122">Configuration Files</span></span>  

 <span data-ttu-id="adfb6-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="adfb6-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfb6-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adfb6-124">Example</span></span>  

<span data-ttu-id="adfb6-125">En el ejemplo siguiente se quita el módulo de solicitud Web existente para HTTP y, después, se registra un nuevo módulo de solicitud web personalizado para las solicitudes HTTP a `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="adfb6-125">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="adfb6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="adfb6-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="adfb6-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="adfb6-127">Network Settings Schema</span></span>](index.md)

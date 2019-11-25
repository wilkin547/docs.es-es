---
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
ms.openlocfilehash: ca3a78a491c61b6e23dab0f96eebceb3157706ae
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089134"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="db107-102">\<quitar > elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="db107-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="db107-103">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db107-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="db107-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="db107-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="db107-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="db107-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="db107-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webRequestModules**](webrequestmodules-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="db107-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="db107-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**quitar >**</span><span class="sxs-lookup"><span data-stu-id="db107-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="db107-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db107-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db107-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db107-109">Attributes and Elements</span></span>  
 <span data-ttu-id="db107-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="db107-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db107-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="db107-111">Attributes</span></span>  
  
|<span data-ttu-id="db107-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="db107-112">**Attribute**</span></span>|<span data-ttu-id="db107-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="db107-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="db107-114">El prefijo URI para las solicitudes controladas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="db107-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db107-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db107-115">Child Elements</span></span>  
 <span data-ttu-id="db107-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="db107-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db107-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db107-117">Parent Elements</span></span>  
  
|<span data-ttu-id="db107-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="db107-118">**Element**</span></span>|<span data-ttu-id="db107-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="db107-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="db107-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="db107-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="db107-121">Especifica los módulos que se van a usar para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="db107-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db107-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db107-122">Remarks</span></span>  
 <span data-ttu-id="db107-123">El elemento `remove` quita el módulo de solicitud Web registrado para el prefijo de URI especificado.</span><span class="sxs-lookup"><span data-stu-id="db107-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="db107-124">El valor del atributo `prefix` debe ser el carácter inicial de un URI válido (por ejemplo, "`http`" o "`http://www.contoso.com`").</span><span class="sxs-lookup"><span data-stu-id="db107-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="db107-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="db107-125">Configuration Files</span></span>  
 <span data-ttu-id="db107-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="db107-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db107-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db107-127">Example</span></span>  

<span data-ttu-id="db107-128">En el ejemplo siguiente se quita el módulo de solicitud Web existente para HTTP y, después, se registra un nuevo módulo de solicitud web personalizado para que las solicitudes HTTP `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="db107-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="db107-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="db107-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="db107-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="db107-130">Network Settings Schema</span></span>](index.md)

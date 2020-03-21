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
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154730"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="4028a-102">\<quitar> Element para webRequestModules (Configuración de red)</span><span class="sxs-lookup"><span data-stu-id="4028a-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="4028a-103">Quita un módulo de solicitud web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4028a-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="4028a-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4028a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4028a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4028a-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4028a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4028a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="4028a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<eliminar>**</span><span class="sxs-lookup"><span data-stu-id="4028a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="4028a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4028a-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4028a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4028a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4028a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4028a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4028a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4028a-111">Attributes</span></span>  
  
|<span data-ttu-id="4028a-112">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="4028a-112">**Attribute**</span></span>|<span data-ttu-id="4028a-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4028a-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="4028a-114">El prefijo URI para las solicitudes controladas por este módulo de solicitud web.</span><span class="sxs-lookup"><span data-stu-id="4028a-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4028a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4028a-115">Child Elements</span></span>  
 <span data-ttu-id="4028a-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4028a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4028a-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4028a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4028a-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4028a-118">**Element**</span></span>|<span data-ttu-id="4028a-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4028a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4028a-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="4028a-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="4028a-121">Especifica los módulos que se utilizarán para solicitar información de los hosts de red.</span><span class="sxs-lookup"><span data-stu-id="4028a-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4028a-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4028a-122">Remarks</span></span>  
 <span data-ttu-id="4028a-123">El `remove` elemento quita el módulo de solicitud Web registrado para el prefijo URI especificado.</span><span class="sxs-lookup"><span data-stu-id="4028a-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="4028a-124">El valor `prefix` del atributo debe ser los caracteres principales`http`de un`http://www.contoso.com`URI válido, por ejemplo, " ", o ".</span><span class="sxs-lookup"><span data-stu-id="4028a-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4028a-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4028a-125">Configuration Files</span></span>  
 <span data-ttu-id="4028a-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4028a-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4028a-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4028a-127">Example</span></span>  

<span data-ttu-id="4028a-128">En el ejemplo siguiente se quita el módulo de solicitud web existente para HTTP `www.contoso.com`y, a continuación, se registra un nuevo módulo de solicitud web personalizado para las solicitudes HTTP en .</span><span class="sxs-lookup"><span data-stu-id="4028a-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="4028a-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4028a-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="4028a-130">Esquema de configuración de red</span><span class="sxs-lookup"><span data-stu-id="4028a-130">Network Settings Schema</span></span>](index.md)

---
title: '&lt;quitar&gt; elemento para webRequestModules (configuración de red)'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e20d414b3be41fc175037c6691518adf6a424b69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="f897b-102">&lt;quitar&gt; elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="f897b-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="f897b-103">Quita un módulo de solicitud Web personalizado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f897b-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="f897b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f897b-104">\<configuration></span></span>  
<span data-ttu-id="f897b-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="f897b-105">\<system.net></span></span>  
<span data-ttu-id="f897b-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="f897b-106">\<webRequestModules></span></span>  
<span data-ttu-id="f897b-107">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="f897b-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f897b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f897b-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f897b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f897b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f897b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f897b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f897b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f897b-111">Attributes</span></span>  
  
|<span data-ttu-id="f897b-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="f897b-112">**Attribute**</span></span>|<span data-ttu-id="f897b-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f897b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="f897b-114">El prefijo URI para las solicitudes administradas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="f897b-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f897b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f897b-115">Child Elements</span></span>  
 <span data-ttu-id="f897b-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f897b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f897b-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f897b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f897b-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="f897b-118">**Element**</span></span>|<span data-ttu-id="f897b-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f897b-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f897b-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f897b-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="f897b-121">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="f897b-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f897b-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f897b-122">Remarks</span></span>  
 <span data-ttu-id="f897b-123">El `remove` elemento quita el módulo de solicitud Web registrado para el prefijo URI especificado.</span><span class="sxs-lookup"><span data-stu-id="f897b-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="f897b-124">El valor de la `prefix` atributo debe ser los primeros caracteres de un URI válido, por ejemplo, "http", o "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="f897b-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f897b-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f897b-125">Configuration Files</span></span>  
 <span data-ttu-id="f897b-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f897b-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f897b-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f897b-127">Example</span></span>  
 <span data-ttu-id="f897b-128">En el ejemplo siguiente se quita el módulo de solicitud Web existente para HTTP y, a continuación, registra un nuevo módulo de solicitud Web personalizado para solicitudes HTTP en www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f897b-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f897b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f897b-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="f897b-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="f897b-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

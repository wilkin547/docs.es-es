---
title: "&lt;agregar&gt; elemento para webRequestModules (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fd407f77e75bce4bdbc37acd5f28bbe39f92d564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="54238-102">&lt;agregar&gt; elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="54238-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="54238-103">Agrega un módulo de solicitud Web personalizado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54238-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="54238-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="54238-104">\<configuration></span></span>  
<span data-ttu-id="54238-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="54238-105">\<system.net></span></span>  
<span data-ttu-id="54238-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="54238-106">\<webRequestModules></span></span>  
<span data-ttu-id="54238-107">\<add></span><span class="sxs-lookup"><span data-stu-id="54238-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54238-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54238-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54238-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="54238-109">Attributes and Elements</span></span>  
 <span data-ttu-id="54238-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="54238-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54238-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="54238-111">Attributes</span></span>  
  
|<span data-ttu-id="54238-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="54238-112">**Attribute**</span></span>|<span data-ttu-id="54238-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="54238-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="54238-114">El prefijo URI para las solicitudes administradas por este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="54238-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="54238-115">El nombre de tipo completo (indicado por la <xref:System.Type.FullName%2A> propiedad) y el nombre del ensamblado (indicado por el <xref:System.Reflection.Assembly.FullName%2A> propiedad), separados por comas, que implementa este módulo de solicitud Web.</span><span class="sxs-lookup"><span data-stu-id="54238-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54238-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="54238-116">Child Elements</span></span>  
 <span data-ttu-id="54238-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="54238-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54238-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="54238-118">Parent Elements</span></span>  
  
|<span data-ttu-id="54238-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="54238-119">**Element**</span></span>|<span data-ttu-id="54238-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="54238-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="54238-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="54238-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="54238-122">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="54238-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54238-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54238-123">Remarks</span></span>  
 <span data-ttu-id="54238-124">El `prefix` atributo define el prefijo URI que utiliza el módulo de solicitud Web especificado.</span><span class="sxs-lookup"><span data-stu-id="54238-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="54238-125">Módulos de solicitud Web suelen registrarse para controlar un protocolo específico, como HTTP o FTP, pero se pueden registrar para controlar una solicitud a un servidor específico o una ruta de acceso en un servidor.</span><span class="sxs-lookup"><span data-stu-id="54238-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="54238-126">El módulo de solicitud Web se crea cuando se pasa a la <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="54238-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="54238-127">El valor de la `prefix` atributo debe ser los primeros caracteres de un URI válido, por ejemplo, "http" o "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="54238-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="54238-128">El valor de la `type` atributo debe ser un nombre de tipo válido y el nombre de ensamblado correspondiente, separados por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="54238-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="54238-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="54238-129">Configuration Files</span></span>  
 <span data-ttu-id="54238-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="54238-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54238-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54238-131">Example</span></span>  
 <span data-ttu-id="54238-132">En el ejemplo siguiente se registra un módulo de solicitud Web personalizado para HTTP.</span><span class="sxs-lookup"><span data-stu-id="54238-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="54238-133">Debe reemplazar los valores de Version y PublicKeyToken con los valores correctos para el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="54238-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54238-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="54238-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="54238-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="54238-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

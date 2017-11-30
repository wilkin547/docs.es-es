---
title: "&lt;Borrar&gt; elemento para webRequestModules (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c88792663b07ace7250b6ee4065e60d6cfb90afd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="86fe1-102">&lt;Borrar&gt; elemento para webRequestModules (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="86fe1-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="86fe1-103">Quita todos los módulos de solicitud Web registrados de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86fe1-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="86fe1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="86fe1-104">\<configuration></span></span>  
<span data-ttu-id="86fe1-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="86fe1-105">\<system.net></span></span>  
<span data-ttu-id="86fe1-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="86fe1-106">\<webRequestModules></span></span>  
<span data-ttu-id="86fe1-107">\<Borrar ></span><span class="sxs-lookup"><span data-stu-id="86fe1-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fe1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86fe1-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86fe1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="86fe1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="86fe1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="86fe1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86fe1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="86fe1-111">Attributes</span></span>  
 <span data-ttu-id="86fe1-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="86fe1-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86fe1-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="86fe1-113">Child Elements</span></span>  
 <span data-ttu-id="86fe1-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="86fe1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86fe1-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="86fe1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="86fe1-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="86fe1-116">**Element**</span></span>|<span data-ttu-id="86fe1-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="86fe1-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="86fe1-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="86fe1-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="86fe1-119">Especifica los módulos que se utilizan para solicitar información de hosts de la red.</span><span class="sxs-lookup"><span data-stu-id="86fe1-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86fe1-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86fe1-120">Remarks</span></span>  
 <span data-ttu-id="86fe1-121">El `clear` elemento quita todos los módulos de solicitud Web que se definieron anteriormente en el archivo de configuración o en un nivel superior en la jerarquía de configuración.</span><span class="sxs-lookup"><span data-stu-id="86fe1-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="86fe1-122">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="86fe1-122">Configuration Files</span></span>  
 <span data-ttu-id="86fe1-123">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="86fe1-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="86fe1-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86fe1-124">Example</span></span>  
 <span data-ttu-id="86fe1-125">En el ejemplo siguiente se borra todos los módulos de solicitud Web y, a continuación, se registra un módulo de solicitud Web para HTTP.</span><span class="sxs-lookup"><span data-stu-id="86fe1-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86fe1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="86fe1-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="86fe1-127">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="86fe1-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

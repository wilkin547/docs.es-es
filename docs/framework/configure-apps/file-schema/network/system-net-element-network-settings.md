---
title: "&lt;system.Net&gt; elemento (configuración de red)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d2eb903b8a84410aa08504c12e78a016d2368923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="137fc-102">&lt;system.Net&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="137fc-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="137fc-103">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="137fc-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="137fc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="137fc-104">\<configuration></span></span>  
<span data-ttu-id="137fc-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="137fc-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="137fc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="137fc-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="137fc-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="137fc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="137fc-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="137fc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="137fc-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="137fc-109">Attributes</span></span>  
 <span data-ttu-id="137fc-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="137fc-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="137fc-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="137fc-111">Child Elements</span></span>  
  
|<span data-ttu-id="137fc-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="137fc-112">**Element**</span></span>|<span data-ttu-id="137fc-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="137fc-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="137fc-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="137fc-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="137fc-115">Especifica los módulos utilizados para autenticar las solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="137fc-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="137fc-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="137fc-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="137fc-117">Especifica el número máximo de conexiones a un host de Internet.</span><span class="sxs-lookup"><span data-stu-id="137fc-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="137fc-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="137fc-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="137fc-119">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="137fc-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="137fc-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="137fc-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="137fc-121">Configura opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="137fc-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="137fc-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="137fc-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="137fc-123">Controla el mecanismo de almacenamiento en caché las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="137fc-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="137fc-124">Configuración</span><span class="sxs-lookup"><span data-stu-id="137fc-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="137fc-125">Configura opciones de red básica para las clases en el <xref:System.Net> y espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="137fc-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="137fc-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="137fc-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="137fc-127">Especifica los módulos que se utilizan para solicitar información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="137fc-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="137fc-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="137fc-128">Parent Elements</span></span>  
  
|<span data-ttu-id="137fc-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="137fc-129">**Element**</span></span>|<span data-ttu-id="137fc-130">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="137fc-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="137fc-131">configuración</span><span class="sxs-lookup"><span data-stu-id="137fc-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="137fc-132">Contiene valores para todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="137fc-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="137fc-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="137fc-133">Remarks</span></span>  
 <span data-ttu-id="137fc-134">El [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) elemento contiene los valores de las clases de la <xref:System.Net> y espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="137fc-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="137fc-135">La configuración de módulos de autenticación, administración de conexiones, configuración de correo electrónico, el servidor proxy y módulos de solicitud de Internet para recibir información de hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="137fc-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="137fc-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="137fc-136">Example</span></span>  
 <span data-ttu-id="137fc-137">En el ejemplo siguiente se muestra una configuración típica utilizada por <xref:System.Net> clases.</span><span class="sxs-lookup"><span data-stu-id="137fc-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="137fc-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="137fc-138">See Also</span></span>  
 [<span data-ttu-id="137fc-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="137fc-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

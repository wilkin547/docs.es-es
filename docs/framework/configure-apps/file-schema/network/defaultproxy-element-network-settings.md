---
title: '&lt;defaultProxy&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
caps.latest.revision: "21"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d0b09f5c845fc9a18c2a1dd919272c2924478eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultproxygt-element-network-settings"></a><span data-ttu-id="73694-102">&lt;defaultProxy&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="73694-102">&lt;defaultProxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="73694-103">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="73694-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="73694-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73694-104">\<configuration></span></span>  
<span data-ttu-id="73694-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="73694-105">\<system.net></span></span>  
<span data-ttu-id="73694-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="73694-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73694-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73694-107">Syntax</span></span>  
  
```xml  
      <defaultProxy  
        enabled="true|false"  
        useDefaultCredentials="true|false">  
           <bypasslist> … </bypasslist>  
           <proxy> … </proxy>  
           <module> … </module>  
      </defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73694-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73694-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73694-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73694-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73694-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="73694-110">Attributes</span></span>  
  
|<span data-ttu-id="73694-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="73694-111">**Element**</span></span>|<span data-ttu-id="73694-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73694-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="73694-113">Especifica si se usa un proxy web.</span><span class="sxs-lookup"><span data-stu-id="73694-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="73694-114">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="73694-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="73694-115">Especifica si se usan las credenciales predeterminadas de este host para tener acceso al proxy web.</span><span class="sxs-lookup"><span data-stu-id="73694-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="73694-116">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="73694-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73694-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73694-117">Child Elements</span></span>  
  
|<span data-ttu-id="73694-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="73694-118">**Element**</span></span>|<span data-ttu-id="73694-119">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73694-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73694-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="73694-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="73694-121">Proporciona un conjunto de expresiones regulares que describen direcciones que no usan el proxy.</span><span class="sxs-lookup"><span data-stu-id="73694-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="73694-122">módulo</span><span class="sxs-lookup"><span data-stu-id="73694-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="73694-123">Agrega un nuevo módulo proxy a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73694-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="73694-124">proxy</span><span class="sxs-lookup"><span data-stu-id="73694-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="73694-125">Define un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="73694-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73694-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73694-126">Parent Elements</span></span>  
  
|<span data-ttu-id="73694-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="73694-127">**Element**</span></span>|<span data-ttu-id="73694-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="73694-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73694-129">System.NET</span><span class="sxs-lookup"><span data-stu-id="73694-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="73694-130">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="73694-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73694-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73694-131">Remarks</span></span>  
 <span data-ttu-id="73694-132">Si el elemento defaultProxy está vacío, se usará la configuración de proxy de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="73694-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="73694-133">Este comportamiento es diferente de la versión 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73694-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="73694-134">Se produce una excepción si el [módulo](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) elemento especifica un tipo no público, el tipo no deriva de la <xref:System.Net.IWebProxy> (clase), se produjo una excepción desde el constructor predeterminado de este objeto o se produjo una excepción mientras recuperar al proxy predeterminado especificado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="73694-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="73694-135">La propiedad <xref:System.Exception.InnerException%2A> en la excepción debería tener más información acerca de la causa del error.</span><span class="sxs-lookup"><span data-stu-id="73694-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73694-136">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="73694-136">Configuration Files</span></span>  
 <span data-ttu-id="73694-137">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="73694-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73694-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73694-138">Example</span></span>  
 <span data-ttu-id="73694-139">En el siguiente ejemplo utiliza los valores predeterminados del proxy de Internet Explorer, especifica la dirección del proxy y omite al proxy para el acceso local y contoso.com.</span><span class="sxs-lookup"><span data-stu-id="73694-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73694-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="73694-140">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="73694-141">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="73694-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)

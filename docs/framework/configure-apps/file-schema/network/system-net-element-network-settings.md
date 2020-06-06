---
title: Elemento <system.Net> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154561"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="bc6b0-102">Elemento \<system.Net> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="bc6b0-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="bc6b0-103">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="bc6b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc6b0-104">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc6b0-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bc6b0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bc6b0-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc6b0-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="bc6b0-107">Attributes</span></span>  
 <span data-ttu-id="bc6b0-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bc6b0-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bc6b0-109">Child Elements</span></span>  
  
|<span data-ttu-id="bc6b0-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="bc6b0-110">**Element**</span></span>|<span data-ttu-id="bc6b0-111">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc6b0-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bc6b0-112">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="bc6b0-112">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="bc6b0-113">Especifica los módulos que se usan para autenticar las solicitudes de Internet.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-113">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="bc6b0-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="bc6b0-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="bc6b0-115">Especifica el número máximo de conexiones a un host de Internet.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-115">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="bc6b0-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="bc6b0-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="bc6b0-117">Configura el servidor proxy de Protocolo de transferencia de hipertexto (HTTP).</span><span class="sxs-lookup"><span data-stu-id="bc6b0-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="bc6b0-118">mailSettings</span><span class="sxs-lookup"><span data-stu-id="bc6b0-118">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="bc6b0-119">Configura las opciones de envío de correo del Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="bc6b0-119">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="bc6b0-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="bc6b0-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="bc6b0-121">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-121">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="bc6b0-122">settings</span><span class="sxs-lookup"><span data-stu-id="bc6b0-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="bc6b0-123">Configura las opciones de red básicas para las clases de <xref:System.Net> y los espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-123">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="bc6b0-124">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="bc6b0-124">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="bc6b0-125">Especifica los módulos que se van a usar para solicitar información de los hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-125">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc6b0-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bc6b0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="bc6b0-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="bc6b0-127">**Element**</span></span>|<span data-ttu-id="bc6b0-128">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="bc6b0-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="bc6b0-129">configuration</span><span class="sxs-lookup"><span data-stu-id="bc6b0-129">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="bc6b0-130">Contiene la configuración de todos los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-130">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc6b0-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc6b0-131">Remarks</span></span>  
 <span data-ttu-id="bc6b0-132">El [\<system.net>](system-net-element-network-settings.md) elemento contiene la configuración para las clases en <xref:System.Net> y los espacios de nombres secundarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-132">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="bc6b0-133">La configuración configura los módulos de autenticación, la administración de conexiones, la configuración de correo, el servidor proxy y los módulos de solicitud de Internet para recibir información de los hosts de Internet.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-133">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc6b0-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc6b0-134">Example</span></span>  
 <span data-ttu-id="bc6b0-135">En el ejemplo siguiente se muestra una configuración típica utilizada por <xref:System.Net> las clases.</span><span class="sxs-lookup"><span data-stu-id="bc6b0-135">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc6b0-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc6b0-136">See also</span></span>

- [<span data-ttu-id="bc6b0-137">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="bc6b0-137">Network Settings Schema</span></span>](index.md)

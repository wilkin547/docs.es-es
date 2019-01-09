---
title: '&lt;transport&gt; de &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: fe015fa308821519419a97a26bb5f57a6b4ab0cd
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148622"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="70a98-102">&lt;transport&gt; de &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="70a98-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="70a98-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="70a98-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="70a98-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="70a98-104">\<system.serviceModel></span></span>  
<span data-ttu-id="70a98-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="70a98-105">\<bindings></span></span>  
<span data-ttu-id="70a98-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="70a98-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="70a98-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="70a98-107">\<binding></span></span>  
<span data-ttu-id="70a98-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="70a98-108">\<security></span></span>  
<span data-ttu-id="70a98-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="70a98-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70a98-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70a98-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="70a98-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="70a98-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70a98-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70a98-112">Attributes and Elements</span></span>  
 <span data-ttu-id="70a98-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70a98-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70a98-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="70a98-114">Attributes</span></span>  
  
|<span data-ttu-id="70a98-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="70a98-115">Attribute</span></span>|<span data-ttu-id="70a98-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a98-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="70a98-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="70a98-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="70a98-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="70a98-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="70a98-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="70a98-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="70a98-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="70a98-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="70a98-121">El dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="70a98-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="70a98-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="70a98-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="70a98-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="70a98-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="70a98-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="70a98-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="70a98-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="70a98-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="70a98-126">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="70a98-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="70a98-127">Valor</span><span class="sxs-lookup"><span data-stu-id="70a98-127">Value</span></span>|<span data-ttu-id="70a98-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a98-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70a98-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="70a98-129">None</span></span>|<span data-ttu-id="70a98-130">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="70a98-130">Security is disabled.</span></span>|  
|<span data-ttu-id="70a98-131">Básico</span><span class="sxs-lookup"><span data-stu-id="70a98-131">Basic</span></span>|<span data-ttu-id="70a98-132">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="70a98-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="70a98-133">Implícita</span><span class="sxs-lookup"><span data-stu-id="70a98-133">Digest</span></span>|<span data-ttu-id="70a98-134">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="70a98-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="70a98-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="70a98-135">Ntlm</span></span>|<span data-ttu-id="70a98-136">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="70a98-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="70a98-137">Windows</span><span class="sxs-lookup"><span data-stu-id="70a98-137">Windows</span></span>|<span data-ttu-id="70a98-138">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="70a98-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="70a98-139">Certificado</span><span class="sxs-lookup"><span data-stu-id="70a98-139">Certificate</span></span>|<span data-ttu-id="70a98-140">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="70a98-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="70a98-141">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="70a98-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="70a98-142">Valor</span><span class="sxs-lookup"><span data-stu-id="70a98-142">Value</span></span>|<span data-ttu-id="70a98-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a98-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70a98-144">Ninguna</span><span class="sxs-lookup"><span data-stu-id="70a98-144">None</span></span>|<span data-ttu-id="70a98-145">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="70a98-145">Security is disabled.</span></span>|  
|<span data-ttu-id="70a98-146">Básico</span><span class="sxs-lookup"><span data-stu-id="70a98-146">Basic</span></span>|<span data-ttu-id="70a98-147">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="70a98-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="70a98-148">Implícita</span><span class="sxs-lookup"><span data-stu-id="70a98-148">Digest</span></span>|<span data-ttu-id="70a98-149">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="70a98-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="70a98-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="70a98-150">Ntlm</span></span>|<span data-ttu-id="70a98-151">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="70a98-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="70a98-152">Windows</span><span class="sxs-lookup"><span data-stu-id="70a98-152">Windows</span></span>|<span data-ttu-id="70a98-153">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="70a98-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="70a98-154">Certificado</span><span class="sxs-lookup"><span data-stu-id="70a98-154">Certificate</span></span>|<span data-ttu-id="70a98-155">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="70a98-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70a98-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70a98-156">Child Elements</span></span>  
 <span data-ttu-id="70a98-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="70a98-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70a98-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70a98-158">Parent Elements</span></span>  
  
|<span data-ttu-id="70a98-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="70a98-159">Element</span></span>|<span data-ttu-id="70a98-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a98-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70a98-161">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="70a98-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="70a98-162">Representa las funciones de seguridad de la [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="70a98-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70a98-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="70a98-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="70a98-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="70a98-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="70a98-165">Enlaces</span><span class="sxs-lookup"><span data-stu-id="70a98-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="70a98-166">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="70a98-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="70a98-167">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="70a98-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="70a98-168">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="70a98-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

---
title: '&lt;transport&gt; de &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 3be9d4e64e63b32156cb64257f5bed8230cee3aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350953"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="59336-102">&lt;transport&gt; de &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="59336-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="59336-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="59336-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="59336-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="59336-104">\<system.serviceModel></span></span>  
<span data-ttu-id="59336-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="59336-105">\<bindings></span></span>  
<span data-ttu-id="59336-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="59336-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="59336-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="59336-107">\<binding></span></span>  
<span data-ttu-id="59336-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="59336-108">\<security></span></span>  
<span data-ttu-id="59336-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="59336-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59336-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59336-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="59336-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="59336-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59336-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59336-112">Attributes and Elements</span></span>  
 <span data-ttu-id="59336-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59336-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59336-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="59336-114">Attributes</span></span>  
  
|<span data-ttu-id="59336-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="59336-115">Attribute</span></span>|<span data-ttu-id="59336-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="59336-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="59336-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="59336-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="59336-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="59336-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="59336-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="59336-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="59336-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="59336-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="59336-121">El dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="59336-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="59336-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="59336-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="59336-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="59336-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="59336-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="59336-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="59336-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="59336-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="59336-126">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="59336-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="59336-127">Valor</span><span class="sxs-lookup"><span data-stu-id="59336-127">Value</span></span>|<span data-ttu-id="59336-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="59336-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59336-129">Ninguna</span><span class="sxs-lookup"><span data-stu-id="59336-129">None</span></span>|<span data-ttu-id="59336-130">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="59336-130">Security is disabled.</span></span>|  
|<span data-ttu-id="59336-131">Básico</span><span class="sxs-lookup"><span data-stu-id="59336-131">Basic</span></span>|<span data-ttu-id="59336-132">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="59336-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="59336-133">Implícita</span><span class="sxs-lookup"><span data-stu-id="59336-133">Digest</span></span>|<span data-ttu-id="59336-134">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="59336-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="59336-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="59336-135">Ntlm</span></span>|<span data-ttu-id="59336-136">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="59336-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="59336-137">Windows</span><span class="sxs-lookup"><span data-stu-id="59336-137">Windows</span></span>|<span data-ttu-id="59336-138">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="59336-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="59336-139">Certificado</span><span class="sxs-lookup"><span data-stu-id="59336-139">Certificate</span></span>|<span data-ttu-id="59336-140">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="59336-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="59336-141">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="59336-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="59336-142">Valor</span><span class="sxs-lookup"><span data-stu-id="59336-142">Value</span></span>|<span data-ttu-id="59336-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="59336-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="59336-144">Ninguna</span><span class="sxs-lookup"><span data-stu-id="59336-144">None</span></span>|<span data-ttu-id="59336-145">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="59336-145">Security is disabled.</span></span>|  
|<span data-ttu-id="59336-146">Básico</span><span class="sxs-lookup"><span data-stu-id="59336-146">Basic</span></span>|<span data-ttu-id="59336-147">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="59336-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="59336-148">Implícita</span><span class="sxs-lookup"><span data-stu-id="59336-148">Digest</span></span>|<span data-ttu-id="59336-149">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="59336-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="59336-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="59336-150">Ntlm</span></span>|<span data-ttu-id="59336-151">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="59336-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="59336-152">Windows</span><span class="sxs-lookup"><span data-stu-id="59336-152">Windows</span></span>|<span data-ttu-id="59336-153">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="59336-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="59336-154">Certificado</span><span class="sxs-lookup"><span data-stu-id="59336-154">Certificate</span></span>|<span data-ttu-id="59336-155">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="59336-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59336-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59336-156">Child Elements</span></span>  
 <span data-ttu-id="59336-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="59336-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59336-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59336-158">Parent Elements</span></span>  
  
|<span data-ttu-id="59336-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="59336-159">Element</span></span>|<span data-ttu-id="59336-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="59336-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59336-161">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="59336-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="59336-162">Representa las funciones de seguridad de la [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="59336-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59336-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="59336-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="59336-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="59336-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="59336-165">Enlaces</span><span class="sxs-lookup"><span data-stu-id="59336-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="59336-166">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="59336-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="59336-167">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="59336-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="59336-168">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="59336-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

---
title: <transport> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732762"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="6323b-102">\<> de transporte de \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="6323b-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="6323b-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="6323b-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="6323b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6323b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6323b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6323b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6323b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="6323b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6323b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ws2007HttpBinding**](ws2007httpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="6323b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="6323b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="6323b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6323b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-ws2007httpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="6323b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="6323b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="6323b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6323b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6323b-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="6323b-112">Type</span><span class="sxs-lookup"><span data-stu-id="6323b-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6323b-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6323b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6323b-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6323b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6323b-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="6323b-115">Attributes</span></span>  
  
|<span data-ttu-id="6323b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="6323b-116">Attribute</span></span>|<span data-ttu-id="6323b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6323b-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="6323b-118">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="6323b-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="6323b-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6323b-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="6323b-120">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="6323b-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="6323b-121">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6323b-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="6323b-122">El dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="6323b-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="6323b-123">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="6323b-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="6323b-124">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="6323b-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="6323b-125">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="6323b-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="6323b-126">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="6323b-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6323b-127">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6323b-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6323b-128">Valor</span><span class="sxs-lookup"><span data-stu-id="6323b-128">Value</span></span>|<span data-ttu-id="6323b-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="6323b-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6323b-130">Ninguno</span><span class="sxs-lookup"><span data-stu-id="6323b-130">None</span></span>|<span data-ttu-id="6323b-131">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6323b-131">Security is disabled.</span></span>|  
|<span data-ttu-id="6323b-132">Básico</span><span class="sxs-lookup"><span data-stu-id="6323b-132">Basic</span></span>|<span data-ttu-id="6323b-133">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="6323b-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="6323b-134">Implícita</span><span class="sxs-lookup"><span data-stu-id="6323b-134">Digest</span></span>|<span data-ttu-id="6323b-135">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="6323b-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="6323b-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="6323b-136">Ntlm</span></span>|<span data-ttu-id="6323b-137">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="6323b-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="6323b-138">Windows</span><span class="sxs-lookup"><span data-stu-id="6323b-138">Windows</span></span>|<span data-ttu-id="6323b-139">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="6323b-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="6323b-140">Certificado</span><span class="sxs-lookup"><span data-stu-id="6323b-140">Certificate</span></span>|<span data-ttu-id="6323b-141">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6323b-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="6323b-142">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="6323b-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6323b-143">Valor</span><span class="sxs-lookup"><span data-stu-id="6323b-143">Value</span></span>|<span data-ttu-id="6323b-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="6323b-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6323b-145">Ninguno</span><span class="sxs-lookup"><span data-stu-id="6323b-145">None</span></span>|<span data-ttu-id="6323b-146">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="6323b-146">Security is disabled.</span></span>|  
|<span data-ttu-id="6323b-147">Básico</span><span class="sxs-lookup"><span data-stu-id="6323b-147">Basic</span></span>|<span data-ttu-id="6323b-148">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="6323b-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="6323b-149">Implícita</span><span class="sxs-lookup"><span data-stu-id="6323b-149">Digest</span></span>|<span data-ttu-id="6323b-150">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="6323b-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="6323b-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="6323b-151">Ntlm</span></span>|<span data-ttu-id="6323b-152">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="6323b-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="6323b-153">Windows</span><span class="sxs-lookup"><span data-stu-id="6323b-153">Windows</span></span>|<span data-ttu-id="6323b-154">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="6323b-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="6323b-155">Certificado</span><span class="sxs-lookup"><span data-stu-id="6323b-155">Certificate</span></span>|<span data-ttu-id="6323b-156">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="6323b-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6323b-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6323b-157">Child Elements</span></span>  
 <span data-ttu-id="6323b-158">Ninguno</span><span class="sxs-lookup"><span data-stu-id="6323b-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6323b-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6323b-159">Parent Elements</span></span>  
  
|<span data-ttu-id="6323b-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="6323b-160">Element</span></span>|<span data-ttu-id="6323b-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="6323b-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6323b-162">\<La ></span><span class="sxs-lookup"><span data-stu-id="6323b-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="6323b-163">Representa las funciones de seguridad del elemento [\<> ws2007HttpBinding](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6323b-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6323b-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="6323b-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="6323b-165">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6323b-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6323b-166">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6323b-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6323b-167">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6323b-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6323b-168">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6323b-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6323b-169">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="6323b-169">\<binding></span></span>](bindings.md)

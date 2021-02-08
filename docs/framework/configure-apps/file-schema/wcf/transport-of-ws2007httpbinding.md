---
description: 'Más información sobre: <transport> de <ws2007HttpBinding>'
title: <transport> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 8c6890bc291458ba0849ab7a206487431b279576
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773438"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="32d6d-103">\<transport> de \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="32d6d-103">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="32d6d-104">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="32d6d-104">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="32d6d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32d6d-105">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="32d6d-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="32d6d-106">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32d6d-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32d6d-107">Attributes and Elements</span></span>  

 <span data-ttu-id="32d6d-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32d6d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32d6d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="32d6d-109">Attributes</span></span>  
  
|<span data-ttu-id="32d6d-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="32d6d-110">Attribute</span></span>|<span data-ttu-id="32d6d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="32d6d-111">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="32d6d-112">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="32d6d-112">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="32d6d-113">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="32d6d-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="32d6d-114">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="32d6d-114">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="32d6d-115">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="32d6d-115">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="32d6d-116">El dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="32d6d-116">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="32d6d-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="32d6d-117">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="32d6d-118">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="32d6d-118">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="32d6d-119">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="32d6d-119">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="32d6d-120">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="32d6d-120">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="32d6d-121">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="32d6d-121">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="32d6d-122">Value</span><span class="sxs-lookup"><span data-stu-id="32d6d-122">Value</span></span>|<span data-ttu-id="32d6d-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="32d6d-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32d6d-124">None</span><span class="sxs-lookup"><span data-stu-id="32d6d-124">None</span></span>|<span data-ttu-id="32d6d-125">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="32d6d-125">Security is disabled.</span></span>|  
|<span data-ttu-id="32d6d-126">Básico</span><span class="sxs-lookup"><span data-stu-id="32d6d-126">Basic</span></span>|<span data-ttu-id="32d6d-127">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="32d6d-127">Uses basic authentication.</span></span>|  
|<span data-ttu-id="32d6d-128">Digest</span><span class="sxs-lookup"><span data-stu-id="32d6d-128">Digest</span></span>|<span data-ttu-id="32d6d-129">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="32d6d-129">Uses digest authentication.</span></span>|  
|<span data-ttu-id="32d6d-130">Ntlm</span><span class="sxs-lookup"><span data-stu-id="32d6d-130">Ntlm</span></span>|<span data-ttu-id="32d6d-131">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="32d6d-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="32d6d-132">Windows</span><span class="sxs-lookup"><span data-stu-id="32d6d-132">Windows</span></span>|<span data-ttu-id="32d6d-133">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="32d6d-133">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="32d6d-134">Certificado</span><span class="sxs-lookup"><span data-stu-id="32d6d-134">Certificate</span></span>|<span data-ttu-id="32d6d-135">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="32d6d-135">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="32d6d-136">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="32d6d-136">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="32d6d-137">Value</span><span class="sxs-lookup"><span data-stu-id="32d6d-137">Value</span></span>|<span data-ttu-id="32d6d-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="32d6d-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="32d6d-139">None</span><span class="sxs-lookup"><span data-stu-id="32d6d-139">None</span></span>|<span data-ttu-id="32d6d-140">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="32d6d-140">Security is disabled.</span></span>|  
|<span data-ttu-id="32d6d-141">Básico</span><span class="sxs-lookup"><span data-stu-id="32d6d-141">Basic</span></span>|<span data-ttu-id="32d6d-142">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="32d6d-142">Uses basic authentication.</span></span>|  
|<span data-ttu-id="32d6d-143">Digest</span><span class="sxs-lookup"><span data-stu-id="32d6d-143">Digest</span></span>|<span data-ttu-id="32d6d-144">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="32d6d-144">Uses digest authentication.</span></span>|  
|<span data-ttu-id="32d6d-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="32d6d-145">Ntlm</span></span>|<span data-ttu-id="32d6d-146">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="32d6d-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="32d6d-147">Windows</span><span class="sxs-lookup"><span data-stu-id="32d6d-147">Windows</span></span>|<span data-ttu-id="32d6d-148">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="32d6d-148">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="32d6d-149">Certificado</span><span class="sxs-lookup"><span data-stu-id="32d6d-149">Certificate</span></span>|<span data-ttu-id="32d6d-150">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="32d6d-150">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32d6d-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32d6d-151">Child Elements</span></span>  

 <span data-ttu-id="32d6d-152">None</span><span class="sxs-lookup"><span data-stu-id="32d6d-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32d6d-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32d6d-153">Parent Elements</span></span>  
  
|<span data-ttu-id="32d6d-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="32d6d-154">Element</span></span>|<span data-ttu-id="32d6d-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="32d6d-155">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="32d6d-156">Representa las funciones de seguridad del [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="32d6d-156">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32d6d-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d6d-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="32d6d-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="32d6d-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="32d6d-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="32d6d-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="32d6d-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="32d6d-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="32d6d-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="32d6d-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

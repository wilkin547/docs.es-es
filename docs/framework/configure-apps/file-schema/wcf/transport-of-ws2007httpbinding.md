---
title: <transport> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732762"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="3cd65-102">\<transport> de \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="3cd65-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="3cd65-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="3cd65-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3cd65-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cd65-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="3cd65-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="3cd65-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cd65-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3cd65-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3cd65-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3cd65-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cd65-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3cd65-108">Attributes</span></span>  
  
|<span data-ttu-id="3cd65-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="3cd65-109">Attribute</span></span>|<span data-ttu-id="3cd65-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cd65-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="3cd65-111">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="3cd65-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="3cd65-112">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3cd65-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="3cd65-113">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="3cd65-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="3cd65-114">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3cd65-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="3cd65-115">El dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="3cd65-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="3cd65-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3cd65-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="3cd65-117">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3cd65-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="3cd65-118">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="3cd65-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="3cd65-119">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="3cd65-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3cd65-120">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3cd65-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3cd65-121">Value</span><span class="sxs-lookup"><span data-stu-id="3cd65-121">Value</span></span>|<span data-ttu-id="3cd65-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cd65-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cd65-123">None</span><span class="sxs-lookup"><span data-stu-id="3cd65-123">None</span></span>|<span data-ttu-id="3cd65-124">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="3cd65-124">Security is disabled.</span></span>|  
|<span data-ttu-id="3cd65-125">Básico</span><span class="sxs-lookup"><span data-stu-id="3cd65-125">Basic</span></span>|<span data-ttu-id="3cd65-126">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="3cd65-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3cd65-127">Digest</span><span class="sxs-lookup"><span data-stu-id="3cd65-127">Digest</span></span>|<span data-ttu-id="3cd65-128">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="3cd65-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3cd65-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3cd65-129">Ntlm</span></span>|<span data-ttu-id="3cd65-130">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd65-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3cd65-131">Windows</span><span class="sxs-lookup"><span data-stu-id="3cd65-131">Windows</span></span>|<span data-ttu-id="3cd65-132">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="3cd65-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3cd65-133">Certificado</span><span class="sxs-lookup"><span data-stu-id="3cd65-133">Certificate</span></span>|<span data-ttu-id="3cd65-134">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="3cd65-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="3cd65-135">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="3cd65-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3cd65-136">Value</span><span class="sxs-lookup"><span data-stu-id="3cd65-136">Value</span></span>|<span data-ttu-id="3cd65-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cd65-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cd65-138">None</span><span class="sxs-lookup"><span data-stu-id="3cd65-138">None</span></span>|<span data-ttu-id="3cd65-139">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="3cd65-139">Security is disabled.</span></span>|  
|<span data-ttu-id="3cd65-140">Básico</span><span class="sxs-lookup"><span data-stu-id="3cd65-140">Basic</span></span>|<span data-ttu-id="3cd65-141">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="3cd65-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3cd65-142">Digest</span><span class="sxs-lookup"><span data-stu-id="3cd65-142">Digest</span></span>|<span data-ttu-id="3cd65-143">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="3cd65-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3cd65-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3cd65-144">Ntlm</span></span>|<span data-ttu-id="3cd65-145">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="3cd65-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3cd65-146">Windows</span><span class="sxs-lookup"><span data-stu-id="3cd65-146">Windows</span></span>|<span data-ttu-id="3cd65-147">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="3cd65-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3cd65-148">Certificado</span><span class="sxs-lookup"><span data-stu-id="3cd65-148">Certificate</span></span>|<span data-ttu-id="3cd65-149">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="3cd65-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cd65-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3cd65-150">Child Elements</span></span>  
 <span data-ttu-id="3cd65-151">None</span><span class="sxs-lookup"><span data-stu-id="3cd65-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cd65-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3cd65-152">Parent Elements</span></span>  
  
|<span data-ttu-id="3cd65-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cd65-153">Element</span></span>|<span data-ttu-id="3cd65-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cd65-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="3cd65-155">Representa las funciones de seguridad del [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3cd65-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cd65-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cd65-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="3cd65-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3cd65-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3cd65-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3cd65-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3cd65-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3cd65-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3cd65-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3cd65-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

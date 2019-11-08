---
title: <transport> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732790"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="60355-102">\<> de transporte de \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="60355-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="60355-103">Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="60355-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="60355-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60355-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60355-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="60355-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="60355-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="60355-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="60355-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**webHttpBinding**](webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="60355-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="60355-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="60355-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="60355-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="60355-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="60355-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="60355-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60355-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60355-111">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="60355-112">Type</span><span class="sxs-lookup"><span data-stu-id="60355-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60355-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60355-113">Attributes and Elements</span></span>  
 <span data-ttu-id="60355-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="60355-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60355-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="60355-115">Attributes</span></span>  
  
|<span data-ttu-id="60355-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="60355-116">Attribute</span></span>|<span data-ttu-id="60355-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="60355-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="60355-118">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="60355-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="60355-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="60355-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="60355-120">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="60355-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="60355-121">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="60355-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="60355-122">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="60355-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="60355-123">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="60355-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="60355-124">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="60355-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="60355-125">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="60355-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="60355-126">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="60355-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="60355-127">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="60355-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="60355-128">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="60355-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="60355-129">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="60355-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="60355-130">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="60355-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="60355-131">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="60355-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="60355-132">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="60355-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="60355-133">Valor</span><span class="sxs-lookup"><span data-stu-id="60355-133">Value</span></span>|<span data-ttu-id="60355-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="60355-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="60355-135">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="60355-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="60355-136">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="60355-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="60355-137">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="60355-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="60355-138">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="60355-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="60355-139">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="60355-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="60355-140">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="60355-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="60355-141">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="60355-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="60355-142">Valor</span><span class="sxs-lookup"><span data-stu-id="60355-142">Value</span></span>|<span data-ttu-id="60355-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="60355-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="60355-144">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="60355-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="60355-145">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="60355-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="60355-146">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="60355-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="60355-147">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="60355-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="60355-148">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="60355-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60355-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60355-149">Child Elements</span></span>  
 <span data-ttu-id="60355-150">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60355-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60355-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60355-151">Parent Elements</span></span>  
  
|<span data-ttu-id="60355-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="60355-152">Element</span></span>|<span data-ttu-id="60355-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="60355-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60355-154">\<La ></span><span class="sxs-lookup"><span data-stu-id="60355-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="60355-155">Representa las funciones de seguridad del elemento [\<wsHttpBinding >](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="60355-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60355-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="60355-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="60355-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="60355-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="60355-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="60355-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="60355-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="60355-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="60355-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="60355-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="60355-161">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="60355-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="60355-162">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="60355-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)

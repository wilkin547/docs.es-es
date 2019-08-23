---
title: <transport> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: f78add5397644dc40bfd22f10bd84aa5c5eb29e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923209"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="9f477-102">\<> de transporte \<de webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9f477-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="9f477-103">Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f477-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="9f477-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9f477-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9f477-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9f477-105">\<bindings></span></span>  
<span data-ttu-id="9f477-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9f477-106">\<webHttpBinding></span></span>  
<span data-ttu-id="9f477-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9f477-107">\<binding></span></span>  
<span data-ttu-id="9f477-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="9f477-108">\<security></span></span>  
<span data-ttu-id="9f477-109">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="9f477-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f477-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f477-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="9f477-111">Type</span><span class="sxs-lookup"><span data-stu-id="9f477-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f477-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9f477-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9f477-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9f477-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f477-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f477-114">Attributes</span></span>  
  
|<span data-ttu-id="9f477-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="9f477-115">Attribute</span></span>|<span data-ttu-id="9f477-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9f477-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9f477-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="9f477-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9f477-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9f477-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9f477-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="9f477-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9f477-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9f477-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9f477-121">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="9f477-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9f477-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="9f477-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9f477-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9f477-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9f477-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="9f477-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="9f477-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="9f477-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="9f477-126">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="9f477-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="9f477-127">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="9f477-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="9f477-128">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="9f477-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="9f477-129">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="9f477-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="9f477-130">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="9f477-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9f477-131">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9f477-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9f477-132">Value</span><span class="sxs-lookup"><span data-stu-id="9f477-132">Value</span></span>|<span data-ttu-id="9f477-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9f477-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="9f477-134">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9f477-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="9f477-135">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="9f477-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="9f477-136">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="9f477-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="9f477-137">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="9f477-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="9f477-138">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="9f477-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="9f477-139">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="9f477-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9f477-140">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="9f477-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9f477-141">Valor</span><span class="sxs-lookup"><span data-stu-id="9f477-141">Value</span></span>|<span data-ttu-id="9f477-142">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9f477-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="9f477-143">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="9f477-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="9f477-144">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="9f477-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="9f477-145">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="9f477-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="9f477-146">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="9f477-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="9f477-147">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="9f477-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f477-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9f477-148">Child Elements</span></span>  
 <span data-ttu-id="9f477-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9f477-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f477-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9f477-150">Parent Elements</span></span>  
  
|<span data-ttu-id="9f477-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f477-151">Element</span></span>|<span data-ttu-id="9f477-152">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9f477-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f477-153">\<security></span><span class="sxs-lookup"><span data-stu-id="9f477-153">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="9f477-154">Representa las funciones de seguridad del [ \<elemento > wsHttpBinding](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9f477-154">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f477-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f477-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="9f477-156">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9f477-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9f477-157">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9f477-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9f477-158">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9f477-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9f477-159">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9f477-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9f477-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="9f477-160">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="9f477-161">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="9f477-161">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)

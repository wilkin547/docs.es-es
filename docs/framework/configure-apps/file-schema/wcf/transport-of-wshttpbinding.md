---
title: Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: a759f74e923c9d81391abf82fa08491f3b31c990
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517960"
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a><span data-ttu-id="fa2d9-102">Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="fa2d9-102">&lt;transport&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="fa2d9-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="fa2d9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fa2d9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fa2d9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fa2d9-105">\<bindings></span></span>  
<span data-ttu-id="fa2d9-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="fa2d9-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="fa2d9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa2d9-107">\<binding></span></span>  
<span data-ttu-id="fa2d9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="fa2d9-108">\<security></span></span>  
<span data-ttu-id="fa2d9-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="fa2d9-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2d9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa2d9-110">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtecutionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="fa2d9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="fa2d9-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa2d9-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa2d9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fa2d9-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa2d9-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa2d9-114">Attributes</span></span>  
  
|<span data-ttu-id="fa2d9-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="fa2d9-115">Attribute</span></span>|<span data-ttu-id="fa2d9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa2d9-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="fa2d9-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="fa2d9-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="fa2d9-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="fa2d9-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="fa2d9-121">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="fa2d9-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="fa2d9-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="fa2d9-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="fa2d9-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="fa2d9-126">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="fa2d9-127">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="fa2d9-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="fa2d9-128">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="fa2d9-129">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="fa2d9-130">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="fa2d9-131">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="fa2d9-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="fa2d9-132">Valor</span><span class="sxs-lookup"><span data-stu-id="fa2d9-132">Value</span></span>|<span data-ttu-id="fa2d9-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa2d9-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="fa2d9-134">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="fa2d9-135">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="fa2d9-136">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="fa2d9-137">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="fa2d9-138">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="fa2d9-139">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="fa2d9-140">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="fa2d9-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="fa2d9-141">Valor</span><span class="sxs-lookup"><span data-stu-id="fa2d9-141">Value</span></span>|<span data-ttu-id="fa2d9-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa2d9-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="fa2d9-143">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="fa2d9-144">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="fa2d9-145">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="fa2d9-146">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="fa2d9-147">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="fa2d9-148">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa2d9-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa2d9-149">Child Elements</span></span>  
 <span data-ttu-id="fa2d9-150">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa2d9-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa2d9-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa2d9-151">Parent Elements</span></span>  
  
|<span data-ttu-id="fa2d9-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa2d9-152">Element</span></span>|<span data-ttu-id="fa2d9-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa2d9-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa2d9-154">\<security></span><span class="sxs-lookup"><span data-stu-id="fa2d9-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="fa2d9-155">Representa las funciones de seguridad de la [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fa2d9-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa2d9-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa2d9-156">See also</span></span>
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="fa2d9-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fa2d9-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fa2d9-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fa2d9-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fa2d9-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="fa2d9-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fa2d9-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fa2d9-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fa2d9-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa2d9-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

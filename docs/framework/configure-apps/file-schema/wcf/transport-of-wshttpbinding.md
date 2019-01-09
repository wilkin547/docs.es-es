---
title: Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 4bd385e8c4fee1ea340e1d9df9816e25760efb02
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148635"
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a><span data-ttu-id="eabb4-102">Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="eabb4-102">&lt;transport&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="eabb4-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="eabb4-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="eabb4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="eabb4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="eabb4-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="eabb4-105">\<bindings></span></span>  
<span data-ttu-id="eabb4-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="eabb4-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="eabb4-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="eabb4-107">\<binding></span></span>  
<span data-ttu-id="eabb4-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="eabb4-108">\<security></span></span>  
<span data-ttu-id="eabb4-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="eabb4-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eabb4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eabb4-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="eabb4-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="eabb4-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eabb4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eabb4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="eabb4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eabb4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eabb4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="eabb4-114">Attributes</span></span>  
  
|<span data-ttu-id="eabb4-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="eabb4-115">Attribute</span></span>|<span data-ttu-id="eabb4-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="eabb4-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="eabb4-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="eabb4-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="eabb4-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="eabb4-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="eabb4-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="eabb4-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="eabb4-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="eabb4-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="eabb4-121">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="eabb4-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="eabb4-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="eabb4-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="eabb4-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="eabb4-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="eabb4-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="eabb4-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="eabb4-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="eabb4-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="eabb4-126">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="eabb4-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="eabb4-127">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="eabb4-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="eabb4-128">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="eabb4-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="eabb4-129">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="eabb4-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="eabb4-130">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="eabb4-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="eabb4-131">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="eabb4-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="eabb4-132">Valor</span><span class="sxs-lookup"><span data-stu-id="eabb4-132">Value</span></span>|<span data-ttu-id="eabb4-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="eabb4-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="eabb4-134">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="eabb4-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="eabb4-135">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="eabb4-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="eabb4-136">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="eabb4-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="eabb4-137">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="eabb4-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="eabb4-138">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="eabb4-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="eabb4-139">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="eabb4-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="eabb4-140">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="eabb4-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="eabb4-141">Valor</span><span class="sxs-lookup"><span data-stu-id="eabb4-141">Value</span></span>|<span data-ttu-id="eabb4-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="eabb4-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="eabb4-143">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="eabb4-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="eabb4-144">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="eabb4-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="eabb4-145">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="eabb4-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="eabb4-146">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="eabb4-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="eabb4-147">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="eabb4-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="eabb4-148">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="eabb4-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eabb4-149">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eabb4-149">Child Elements</span></span>  
 <span data-ttu-id="eabb4-150">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eabb4-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eabb4-151">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eabb4-151">Parent Elements</span></span>  
  
|<span data-ttu-id="eabb4-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="eabb4-152">Element</span></span>|<span data-ttu-id="eabb4-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="eabb4-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eabb4-154">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="eabb4-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="eabb4-155">Representa las funciones de seguridad de la [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="eabb4-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eabb4-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="eabb4-156">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="eabb4-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="eabb4-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="eabb4-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="eabb4-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="eabb4-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="eabb4-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="eabb4-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="eabb4-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="eabb4-161">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="eabb4-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

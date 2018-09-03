---
title: '&lt;transport&gt; de &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: bbbd459e5717722359fe010a27e548d21ff074db
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482682"
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="02630-102">&lt;transport&gt; de &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="02630-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="02630-103">Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="02630-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="02630-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02630-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02630-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="02630-105">\<bindings></span></span>  
<span data-ttu-id="02630-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="02630-106">\<webHttpBinding></span></span>  
<span data-ttu-id="02630-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="02630-107">\<binding></span></span>  
<span data-ttu-id="02630-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="02630-108">\<security></span></span>  
<span data-ttu-id="02630-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="02630-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02630-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02630-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</WebHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="02630-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="02630-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02630-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02630-112">Attributes and Elements</span></span>  
 <span data-ttu-id="02630-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02630-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02630-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="02630-114">Attributes</span></span>  
  
|<span data-ttu-id="02630-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="02630-115">Attribute</span></span>|<span data-ttu-id="02630-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="02630-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="02630-117">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="02630-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="02630-118">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="02630-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="02630-119">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="02630-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="02630-120">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="02630-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="02630-121">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="02630-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="02630-122">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="02630-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="02630-123">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="02630-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="02630-124">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="02630-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="02630-125">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="02630-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="02630-126">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="02630-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="02630-127">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="02630-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="02630-128">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="02630-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="02630-129">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="02630-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="02630-130">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="02630-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="02630-131">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="02630-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="02630-132">Valor</span><span class="sxs-lookup"><span data-stu-id="02630-132">Value</span></span>|<span data-ttu-id="02630-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="02630-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="02630-134">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="02630-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="02630-135">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="02630-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="02630-136">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="02630-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="02630-137">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="02630-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="02630-138">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="02630-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="02630-139">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="02630-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="02630-140">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="02630-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="02630-141">Valor</span><span class="sxs-lookup"><span data-stu-id="02630-141">Value</span></span>|<span data-ttu-id="02630-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="02630-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="02630-143">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="02630-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="02630-144">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="02630-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="02630-145">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="02630-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="02630-146">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="02630-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="02630-147">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="02630-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02630-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02630-148">Child Elements</span></span>  
 <span data-ttu-id="02630-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02630-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02630-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02630-150">Parent Elements</span></span>  
  
|<span data-ttu-id="02630-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="02630-151">Element</span></span>|<span data-ttu-id="02630-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="02630-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02630-153">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="02630-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="02630-154">Representa las funciones de seguridad de la [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="02630-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02630-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="02630-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="02630-156">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="02630-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="02630-157">Enlaces</span><span class="sxs-lookup"><span data-stu-id="02630-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="02630-158">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="02630-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="02630-159">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="02630-159">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="02630-160">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="02630-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="02630-161">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="02630-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)

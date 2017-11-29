---
title: '&lt;transport&gt; de &lt;netHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67bacedb9a2e46903b97ea0747880bbb1af24a68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a><span data-ttu-id="8bcfe-102">&lt;transport&gt; de &lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8bcfe-102">&lt;transport&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="8bcfe-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="8bcfe-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8bcfe-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-105">\<bindings></span></span>  
<span data-ttu-id="8bcfe-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-106">\<netHttpBinding></span></span>  
<span data-ttu-id="8bcfe-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-107">\<binding></span></span>  
<span data-ttu-id="8bcfe-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-108">\<security></span></span>  
<span data-ttu-id="8bcfe-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcfe-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bcfe-110">Syntax</span></span>  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bcfe-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8bcfe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8bcfe-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bcfe-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8bcfe-113">Attributes</span></span>  
  
|<span data-ttu-id="8bcfe-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="8bcfe-114">Attribute</span></span>|<span data-ttu-id="8bcfe-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bcfe-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bcfe-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bcfe-116">clientCredentialType</span></span>|<span data-ttu-id="8bcfe-117">: Especifica el tipo de credencial que se utilizará al realizar la autenticación de cliente mediante la autenticación de HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="8bcfe-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-118">The default is `None`.</span></span> <span data-ttu-id="8bcfe-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8bcfe-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bcfe-120">proxyCredentialType</span></span>|<span data-ttu-id="8bcfe-121">: Especifica el tipo de credencial que se utilizará al realizar la autenticación de cliente desde dentro de un dominio con un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="8bcfe-122">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="8bcfe-123">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="8bcfe-124">realm</span><span class="sxs-lookup"><span data-stu-id="8bcfe-124">realm</span></span>|<span data-ttu-id="8bcfe-125">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="8bcfe-126">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="8bcfe-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8bcfe-127">policyEnforcement</span></span>|<span data-ttu-id="8bcfe-128">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8bcfe-129">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="8bcfe-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8bcfe-130">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8bcfe-131">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8bcfe-132">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="8bcfe-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="8bcfe-133">protectionScenario</span></span>|<span data-ttu-id="8bcfe-134">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8bcfe-135">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bcfe-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8bcfe-136">Valor</span><span class="sxs-lookup"><span data-stu-id="8bcfe-136">Value</span></span>|<span data-ttu-id="8bcfe-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bcfe-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bcfe-138">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8bcfe-138">None</span></span>|<span data-ttu-id="8bcfe-139">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8bcfe-140">Básico</span><span class="sxs-lookup"><span data-stu-id="8bcfe-140">Basic</span></span>|<span data-ttu-id="8bcfe-141">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="8bcfe-142">Implícita</span><span class="sxs-lookup"><span data-stu-id="8bcfe-142">Digest</span></span>|<span data-ttu-id="8bcfe-143">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="8bcfe-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8bcfe-144">Ntlm</span></span>|<span data-ttu-id="8bcfe-145">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8bcfe-146">Windows</span><span class="sxs-lookup"><span data-stu-id="8bcfe-146">Windows</span></span>|<span data-ttu-id="8bcfe-147">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="8bcfe-148">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8bcfe-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8bcfe-149">Valor</span><span class="sxs-lookup"><span data-stu-id="8bcfe-149">Value</span></span>|<span data-ttu-id="8bcfe-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bcfe-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8bcfe-151">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8bcfe-151">None</span></span>|<span data-ttu-id="8bcfe-152">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8bcfe-153">Básico</span><span class="sxs-lookup"><span data-stu-id="8bcfe-153">Basic</span></span>|<span data-ttu-id="8bcfe-154">Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8bcfe-155">Implícita</span><span class="sxs-lookup"><span data-stu-id="8bcfe-155">Digest</span></span>|<span data-ttu-id="8bcfe-156">Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="8bcfe-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8bcfe-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8bcfe-157">Ntlm</span></span>|<span data-ttu-id="8bcfe-158">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8bcfe-159">Windows</span><span class="sxs-lookup"><span data-stu-id="8bcfe-159">Windows</span></span>|<span data-ttu-id="8bcfe-160">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="8bcfe-161">Certificado</span><span class="sxs-lookup"><span data-stu-id="8bcfe-161">Certificate</span></span>|<span data-ttu-id="8bcfe-162">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="8bcfe-163">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bcfe-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8bcfe-164">Child Elements</span></span>  
 <span data-ttu-id="8bcfe-165">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8bcfe-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8bcfe-166">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8bcfe-166">Parent Elements</span></span>  
  
|<span data-ttu-id="8bcfe-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bcfe-167">Element</span></span>|<span data-ttu-id="8bcfe-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bcfe-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bcfe-169">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="8bcfe-170">Define las funciones de seguridad para la [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8bcfe-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8bcfe-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bcfe-171">Example</span></span>  
 <span data-ttu-id="8bcfe-172">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="8bcfe-173">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="8bcfe-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml
<system.serviceModel>  
  <services>  
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <endpoint address=""  
                binding="netHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  <bindings>  
    <netHttpBinding>  
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bcfe-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bcfe-174">See Also</span></span>  
 <span data-ttu-id="8bcfe-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span><span class="sxs-lookup"><span data-stu-id="8bcfe-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="8bcfe-176">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8bcfe-176">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8bcfe-177">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8bcfe-177">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8bcfe-178">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8bcfe-178">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8bcfe-179">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8bcfe-179">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8bcfe-180">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="8bcfe-180">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

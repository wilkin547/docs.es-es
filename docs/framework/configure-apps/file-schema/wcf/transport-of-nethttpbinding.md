---
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 44e334c3313f93a23ca7df15ba377c5568a92397
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188804"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="dfa3b-102">\<transporte > de \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dfa3b-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="dfa3b-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="dfa3b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dfa3b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dfa3b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="dfa3b-105">\<bindings></span></span>  
<span data-ttu-id="dfa3b-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="dfa3b-106">\<netHttpBinding></span></span>  
<span data-ttu-id="dfa3b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="dfa3b-107">\<binding></span></span>  
<span data-ttu-id="dfa3b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="dfa3b-108">\<security></span></span>  
<span data-ttu-id="dfa3b-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="dfa3b-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfa3b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfa3b-110">Syntax</span></span>  
  
```xml  
<netHttpBinding>
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
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dfa3b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dfa3b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dfa3b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dfa3b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="dfa3b-113">Attributes</span></span>  
  
|<span data-ttu-id="dfa3b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="dfa3b-114">Attribute</span></span>|<span data-ttu-id="dfa3b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfa3b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dfa3b-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfa3b-116">clientCredentialType</span></span>|<span data-ttu-id="dfa3b-117">: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="dfa3b-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-118">The default is `None`.</span></span> <span data-ttu-id="dfa3b-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="dfa3b-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfa3b-120">proxyCredentialType</span></span>|<span data-ttu-id="dfa3b-121">: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="dfa3b-122">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="dfa3b-123">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="dfa3b-124">realm</span><span class="sxs-lookup"><span data-stu-id="dfa3b-124">realm</span></span>|<span data-ttu-id="dfa3b-125">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="dfa3b-126">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="dfa3b-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="dfa3b-127">policyEnforcement</span></span>|<span data-ttu-id="dfa3b-128">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="dfa3b-129">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="dfa3b-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="dfa3b-130">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="dfa3b-131">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="dfa3b-132">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="dfa3b-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="dfa3b-133">protectionScenario</span></span>|<span data-ttu-id="dfa3b-134">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="dfa3b-135">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfa3b-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="dfa3b-136">Valor</span><span class="sxs-lookup"><span data-stu-id="dfa3b-136">Value</span></span>|<span data-ttu-id="dfa3b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfa3b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dfa3b-138">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dfa3b-138">None</span></span>|<span data-ttu-id="dfa3b-139">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="dfa3b-140">Básico</span><span class="sxs-lookup"><span data-stu-id="dfa3b-140">Basic</span></span>|<span data-ttu-id="dfa3b-141">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="dfa3b-142">Implícita</span><span class="sxs-lookup"><span data-stu-id="dfa3b-142">Digest</span></span>|<span data-ttu-id="dfa3b-143">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="dfa3b-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="dfa3b-144">Ntlm</span></span>|<span data-ttu-id="dfa3b-145">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="dfa3b-146">Windows</span><span class="sxs-lookup"><span data-stu-id="dfa3b-146">Windows</span></span>|<span data-ttu-id="dfa3b-147">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="dfa3b-148">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfa3b-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="dfa3b-149">Valor</span><span class="sxs-lookup"><span data-stu-id="dfa3b-149">Value</span></span>|<span data-ttu-id="dfa3b-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfa3b-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dfa3b-151">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dfa3b-151">None</span></span>|<span data-ttu-id="dfa3b-152">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="dfa3b-153">Básico</span><span class="sxs-lookup"><span data-stu-id="dfa3b-153">Basic</span></span>|<span data-ttu-id="dfa3b-154">Especifica la autenticación básica como se define en RFC 2617 – HTTP Authentication: Básica y autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="dfa3b-155">Implícita</span><span class="sxs-lookup"><span data-stu-id="dfa3b-155">Digest</span></span>|<span data-ttu-id="dfa3b-156">Especifica la autenticación implícita, como se define en RFC 2617 – HTTP Authentication: Básica y autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="dfa3b-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="dfa3b-157">Ntlm</span></span>|<span data-ttu-id="dfa3b-158">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="dfa3b-159">Windows</span><span class="sxs-lookup"><span data-stu-id="dfa3b-159">Windows</span></span>|<span data-ttu-id="dfa3b-160">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="dfa3b-161">Certificado</span><span class="sxs-lookup"><span data-stu-id="dfa3b-161">Certificate</span></span>|<span data-ttu-id="dfa3b-162">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="dfa3b-163">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dfa3b-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dfa3b-164">Child Elements</span></span>  
 <span data-ttu-id="dfa3b-165">Ninguna</span><span class="sxs-lookup"><span data-stu-id="dfa3b-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dfa3b-166">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dfa3b-166">Parent Elements</span></span>  
  
|<span data-ttu-id="dfa3b-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfa3b-167">Element</span></span>|<span data-ttu-id="dfa3b-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfa3b-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dfa3b-169">\<security></span><span class="sxs-lookup"><span data-stu-id="dfa3b-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="dfa3b-170">Define las funciones de seguridad para el [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dfa3b-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dfa3b-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfa3b-171">Example</span></span>  
 <span data-ttu-id="dfa3b-172">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="dfa3b-173">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfa3b-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="dfa3b-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfa3b-174">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="dfa3b-175">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dfa3b-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dfa3b-176">Enlaces</span><span class="sxs-lookup"><span data-stu-id="dfa3b-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="dfa3b-177">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="dfa3b-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dfa3b-178">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dfa3b-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dfa3b-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="dfa3b-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

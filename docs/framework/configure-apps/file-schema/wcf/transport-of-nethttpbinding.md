---
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: f9f784329081f6a18560991378a4527c731f4d31
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934716"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="045c9-102">\<> de transporte \<de > netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="045c9-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="045c9-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="045c9-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="045c9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="045c9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="045c9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="045c9-105">\<bindings></span></span>  
<span data-ttu-id="045c9-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="045c9-106">\<netHttpBinding></span></span>  
<span data-ttu-id="045c9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="045c9-107">\<binding></span></span>  
<span data-ttu-id="045c9-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="045c9-108">\<security></span></span>  
<span data-ttu-id="045c9-109">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="045c9-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="045c9-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="045c9-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="045c9-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="045c9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="045c9-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="045c9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="045c9-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="045c9-113">Attributes</span></span>  
  
|<span data-ttu-id="045c9-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="045c9-114">Attribute</span></span>|<span data-ttu-id="045c9-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="045c9-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="045c9-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="045c9-116">clientCredentialType</span></span>|<span data-ttu-id="045c9-117">: Especifica el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="045c9-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="045c9-118">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="045c9-118">The default is `None`.</span></span> <span data-ttu-id="045c9-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="045c9-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="045c9-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="045c9-120">proxyCredentialType</span></span>|<span data-ttu-id="045c9-121">: Especifica el tipo de credencial que se va a usar al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="045c9-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="045c9-122">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="045c9-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="045c9-123">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="045c9-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="045c9-124">realm</span><span class="sxs-lookup"><span data-stu-id="045c9-124">realm</span></span>|<span data-ttu-id="045c9-125">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="045c9-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="045c9-126">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="045c9-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="045c9-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="045c9-127">policyEnforcement</span></span>|<span data-ttu-id="045c9-128">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="045c9-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="045c9-129">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="045c9-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="045c9-130">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="045c9-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="045c9-131">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="045c9-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="045c9-132">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="045c9-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="045c9-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="045c9-133">protectionScenario</span></span>|<span data-ttu-id="045c9-134">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="045c9-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="045c9-135">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="045c9-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="045c9-136">Value</span><span class="sxs-lookup"><span data-stu-id="045c9-136">Value</span></span>|<span data-ttu-id="045c9-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="045c9-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="045c9-138">None</span><span class="sxs-lookup"><span data-stu-id="045c9-138">None</span></span>|<span data-ttu-id="045c9-139">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="045c9-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="045c9-140">Básica</span><span class="sxs-lookup"><span data-stu-id="045c9-140">Basic</span></span>|<span data-ttu-id="045c9-141">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="045c9-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="045c9-142">Implícita</span><span class="sxs-lookup"><span data-stu-id="045c9-142">Digest</span></span>|<span data-ttu-id="045c9-143">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="045c9-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="045c9-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="045c9-144">Ntlm</span></span>|<span data-ttu-id="045c9-145">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="045c9-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="045c9-146">Windows</span><span class="sxs-lookup"><span data-stu-id="045c9-146">Windows</span></span>|<span data-ttu-id="045c9-147">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="045c9-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="045c9-148">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="045c9-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="045c9-149">Value</span><span class="sxs-lookup"><span data-stu-id="045c9-149">Value</span></span>|<span data-ttu-id="045c9-150">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="045c9-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="045c9-151">None</span><span class="sxs-lookup"><span data-stu-id="045c9-151">None</span></span>|<span data-ttu-id="045c9-152">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="045c9-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="045c9-153">Básica</span><span class="sxs-lookup"><span data-stu-id="045c9-153">Basic</span></span>|<span data-ttu-id="045c9-154">Especifica la autenticación básica tal y como se define en RFC 2617: autenticación HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="045c9-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="045c9-155">Implícita</span><span class="sxs-lookup"><span data-stu-id="045c9-155">Digest</span></span>|<span data-ttu-id="045c9-156">Especifica la autenticación implícita tal y como se define en RFC 2617: autenticación HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="045c9-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="045c9-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="045c9-157">Ntlm</span></span>|<span data-ttu-id="045c9-158">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="045c9-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="045c9-159">Windows</span><span class="sxs-lookup"><span data-stu-id="045c9-159">Windows</span></span>|<span data-ttu-id="045c9-160">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="045c9-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="045c9-161">Certificate</span><span class="sxs-lookup"><span data-stu-id="045c9-161">Certificate</span></span>|<span data-ttu-id="045c9-162">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="045c9-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="045c9-163">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="045c9-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="045c9-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="045c9-164">Child Elements</span></span>  
 <span data-ttu-id="045c9-165">None</span><span class="sxs-lookup"><span data-stu-id="045c9-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="045c9-166">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="045c9-166">Parent Elements</span></span>  
  
|<span data-ttu-id="045c9-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="045c9-167">Element</span></span>|<span data-ttu-id="045c9-168">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="045c9-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="045c9-169">\<security></span><span class="sxs-lookup"><span data-stu-id="045c9-169">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="045c9-170">Define las funciones de seguridad para el [ \<> netHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="045c9-170">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="045c9-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="045c9-171">Example</span></span>  
 <span data-ttu-id="045c9-172">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="045c9-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="045c9-173">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="045c9-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="045c9-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="045c9-174">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="045c9-175">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="045c9-175">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="045c9-176">Enlaces</span><span class="sxs-lookup"><span data-stu-id="045c9-176">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="045c9-177">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="045c9-177">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="045c9-178">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="045c9-178">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="045c9-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="045c9-179">\<binding></span></span>](../../../misc/binding.md)

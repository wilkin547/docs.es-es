---
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 521aaf3913a1d30d10a674b71d4d98affcabc296
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399342"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="f310b-102">\<> de transporte \<de > netHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f310b-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="f310b-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="f310b-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="f310b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f310b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f310b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f310b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f310b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f310b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f310b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netHttpBinding**](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f310b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="f310b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="f310b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f310b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f310b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="f310b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de transporte**</span><span class="sxs-lookup"><span data-stu-id="f310b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f310b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f310b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f310b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f310b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f310b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f310b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f310b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="f310b-114">Attributes</span></span>  
  
|<span data-ttu-id="f310b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="f310b-115">Attribute</span></span>|<span data-ttu-id="f310b-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f310b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f310b-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f310b-117">clientCredentialType</span></span>|<span data-ttu-id="f310b-118">: Especifica el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="f310b-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="f310b-119">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="f310b-119">The default is `None`.</span></span> <span data-ttu-id="f310b-120">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f310b-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="f310b-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f310b-121">proxyCredentialType</span></span>|<span data-ttu-id="f310b-122">: Especifica el tipo de credencial que se va a usar al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="f310b-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="f310b-123">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="f310b-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="f310b-124">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f310b-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="f310b-125">realm</span><span class="sxs-lookup"><span data-stu-id="f310b-125">realm</span></span>|<span data-ttu-id="f310b-126">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="f310b-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="f310b-127">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f310b-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="f310b-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="f310b-128">policyEnforcement</span></span>|<span data-ttu-id="f310b-129">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f310b-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f310b-130">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="f310b-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f310b-131">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="f310b-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f310b-132">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="f310b-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f310b-133">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="f310b-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="f310b-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="f310b-134">protectionScenario</span></span>|<span data-ttu-id="f310b-135">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="f310b-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f310b-136">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f310b-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f310b-137">Value</span><span class="sxs-lookup"><span data-stu-id="f310b-137">Value</span></span>|<span data-ttu-id="f310b-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f310b-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f310b-139">None</span><span class="sxs-lookup"><span data-stu-id="f310b-139">None</span></span>|<span data-ttu-id="f310b-140">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="f310b-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="f310b-141">Básica</span><span class="sxs-lookup"><span data-stu-id="f310b-141">Basic</span></span>|<span data-ttu-id="f310b-142">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="f310b-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="f310b-143">Implícita</span><span class="sxs-lookup"><span data-stu-id="f310b-143">Digest</span></span>|<span data-ttu-id="f310b-144">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="f310b-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="f310b-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f310b-145">Ntlm</span></span>|<span data-ttu-id="f310b-146">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="f310b-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="f310b-147">Windows</span><span class="sxs-lookup"><span data-stu-id="f310b-147">Windows</span></span>|<span data-ttu-id="f310b-148">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="f310b-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="f310b-149">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f310b-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f310b-150">Value</span><span class="sxs-lookup"><span data-stu-id="f310b-150">Value</span></span>|<span data-ttu-id="f310b-151">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f310b-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f310b-152">None</span><span class="sxs-lookup"><span data-stu-id="f310b-152">None</span></span>|<span data-ttu-id="f310b-153">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="f310b-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="f310b-154">Básica</span><span class="sxs-lookup"><span data-stu-id="f310b-154">Basic</span></span>|<span data-ttu-id="f310b-155">Especifica la autenticación básica tal y como se define en RFC 2617: autenticación HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="f310b-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="f310b-156">Implícita</span><span class="sxs-lookup"><span data-stu-id="f310b-156">Digest</span></span>|<span data-ttu-id="f310b-157">Especifica la autenticación implícita tal y como se define en RFC 2617: autenticación HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="f310b-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="f310b-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f310b-158">Ntlm</span></span>|<span data-ttu-id="f310b-159">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="f310b-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="f310b-160">Windows</span><span class="sxs-lookup"><span data-stu-id="f310b-160">Windows</span></span>|<span data-ttu-id="f310b-161">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="f310b-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="f310b-162">Certificate</span><span class="sxs-lookup"><span data-stu-id="f310b-162">Certificate</span></span>|<span data-ttu-id="f310b-163">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="f310b-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="f310b-164">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="f310b-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f310b-165">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f310b-165">Child Elements</span></span>  
 <span data-ttu-id="f310b-166">None</span><span class="sxs-lookup"><span data-stu-id="f310b-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f310b-167">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f310b-167">Parent Elements</span></span>  
  
|<span data-ttu-id="f310b-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="f310b-168">Element</span></span>|<span data-ttu-id="f310b-169">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f310b-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f310b-170">\<security></span><span class="sxs-lookup"><span data-stu-id="f310b-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="f310b-171">Define las funciones de seguridad para el [ \<> netHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f310b-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f310b-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f310b-172">Example</span></span>  
 <span data-ttu-id="f310b-173">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="f310b-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="f310b-174">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="f310b-174">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f310b-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="f310b-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="f310b-176">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f310b-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f310b-177">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f310b-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f310b-178">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f310b-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f310b-179">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f310b-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f310b-180">\<binding></span><span class="sxs-lookup"><span data-stu-id="f310b-180">\<binding></span></span>](../../../misc/binding.md)

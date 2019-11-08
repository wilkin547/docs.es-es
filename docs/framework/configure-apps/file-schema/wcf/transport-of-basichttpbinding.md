---
title: <transport> de <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: c563339e4f854cc4e60f92dd5b8c0b39112dc000
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736123"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="36a83-102">\<> de transporte de \<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="36a83-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="36a83-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="36a83-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="36a83-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36a83-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36a83-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36a83-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36a83-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="36a83-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="36a83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**basicHttpBinding**](basichttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="36a83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="36a83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="36a83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="36a83-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-basichttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="36a83-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="36a83-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="36a83-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a83-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36a83-111">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36a83-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="36a83-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36a83-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="36a83-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36a83-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="36a83-114">Attributes</span></span>  
  
|<span data-ttu-id="36a83-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="36a83-115">Attribute</span></span>|<span data-ttu-id="36a83-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="36a83-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36a83-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="36a83-117">clientCredentialType</span></span>|<span data-ttu-id="36a83-118">: Especifica el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="36a83-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="36a83-119">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="36a83-119">The default is `None`.</span></span> <span data-ttu-id="36a83-120">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="36a83-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="36a83-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="36a83-121">proxyCredentialType</span></span>|<span data-ttu-id="36a83-122">: Especifica el tipo de credencial que se va a usar al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="36a83-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="36a83-123">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="36a83-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="36a83-124">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="36a83-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="36a83-125">realm</span><span class="sxs-lookup"><span data-stu-id="36a83-125">realm</span></span>|<span data-ttu-id="36a83-126">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="36a83-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="36a83-127">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="36a83-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="36a83-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="36a83-128">policyEnforcement</span></span>|<span data-ttu-id="36a83-129">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="36a83-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="36a83-130">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="36a83-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="36a83-131">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="36a83-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="36a83-132">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="36a83-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="36a83-133">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="36a83-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="36a83-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="36a83-134">protectionScenario</span></span>|<span data-ttu-id="36a83-135">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="36a83-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="36a83-136">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="36a83-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="36a83-137">Valor</span><span class="sxs-lookup"><span data-stu-id="36a83-137">Value</span></span>|<span data-ttu-id="36a83-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="36a83-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="36a83-139">Ninguno</span><span class="sxs-lookup"><span data-stu-id="36a83-139">None</span></span>|<span data-ttu-id="36a83-140">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="36a83-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="36a83-141">Básico</span><span class="sxs-lookup"><span data-stu-id="36a83-141">Basic</span></span>|<span data-ttu-id="36a83-142">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="36a83-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="36a83-143">Implícita</span><span class="sxs-lookup"><span data-stu-id="36a83-143">Digest</span></span>|<span data-ttu-id="36a83-144">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="36a83-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="36a83-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="36a83-145">Ntlm</span></span>|<span data-ttu-id="36a83-146">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="36a83-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="36a83-147">Windows</span><span class="sxs-lookup"><span data-stu-id="36a83-147">Windows</span></span>|<span data-ttu-id="36a83-148">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="36a83-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="36a83-149">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="36a83-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="36a83-150">Valor</span><span class="sxs-lookup"><span data-stu-id="36a83-150">Value</span></span>|<span data-ttu-id="36a83-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="36a83-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="36a83-152">Ninguno</span><span class="sxs-lookup"><span data-stu-id="36a83-152">None</span></span>|<span data-ttu-id="36a83-153">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="36a83-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="36a83-154">Básico</span><span class="sxs-lookup"><span data-stu-id="36a83-154">Basic</span></span>|<span data-ttu-id="36a83-155">Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="36a83-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="36a83-156">Implícita</span><span class="sxs-lookup"><span data-stu-id="36a83-156">Digest</span></span>|<span data-ttu-id="36a83-157">Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="36a83-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="36a83-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="36a83-158">Ntlm</span></span>|<span data-ttu-id="36a83-159">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="36a83-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="36a83-160">Windows</span><span class="sxs-lookup"><span data-stu-id="36a83-160">Windows</span></span>|<span data-ttu-id="36a83-161">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="36a83-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="36a83-162">Certificado</span><span class="sxs-lookup"><span data-stu-id="36a83-162">Certificate</span></span>|<span data-ttu-id="36a83-163">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="36a83-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="36a83-164">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="36a83-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36a83-165">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="36a83-165">Child Elements</span></span>  
 <span data-ttu-id="36a83-166">Ninguno</span><span class="sxs-lookup"><span data-stu-id="36a83-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36a83-167">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="36a83-167">Parent Elements</span></span>  
  
|<span data-ttu-id="36a83-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="36a83-168">Element</span></span>|<span data-ttu-id="36a83-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="36a83-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36a83-170">\<La ></span><span class="sxs-lookup"><span data-stu-id="36a83-170">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="36a83-171">Define las capacidades de seguridad para el [\<basicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="36a83-171">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="36a83-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36a83-172">Example</span></span>  
 <span data-ttu-id="36a83-173">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="36a83-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="36a83-174">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="36a83-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="36a83-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="36a83-175">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="36a83-176">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="36a83-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="36a83-177">Enlaces</span><span class="sxs-lookup"><span data-stu-id="36a83-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="36a83-178">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="36a83-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="36a83-179">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="36a83-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="36a83-180">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="36a83-180">\<binding></span></span>](bindings.md)

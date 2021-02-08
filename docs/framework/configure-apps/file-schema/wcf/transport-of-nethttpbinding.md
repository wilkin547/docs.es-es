---
description: 'Más información sobre: <transport> de <netHttpBinding>'
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 1c2029fcbc57632b828fa180ba0ffbbf6b974775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773516"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="ae44b-103">\<transport> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ae44b-103">\<transport> of \<netHttpBinding></span></span>

<span data-ttu-id="ae44b-104">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae44b-104">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="ae44b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae44b-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae44b-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ae44b-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ae44b-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ae44b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae44b-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ae44b-108">Attributes</span></span>  
  
|<span data-ttu-id="ae44b-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="ae44b-109">Attribute</span></span>|<span data-ttu-id="ae44b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae44b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae44b-111">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="ae44b-111">clientCredentialType</span></span>|<span data-ttu-id="ae44b-112">: Especifica el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae44b-112">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="ae44b-113">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="ae44b-113">The default is `None`.</span></span> <span data-ttu-id="ae44b-114">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ae44b-114">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="ae44b-115">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="ae44b-115">proxyCredentialType</span></span>|<span data-ttu-id="ae44b-116">: Especifica el tipo de credencial que se va a usar al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae44b-116">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="ae44b-117">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="ae44b-117">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="ae44b-118">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ae44b-118">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="ae44b-119">realm</span><span class="sxs-lookup"><span data-stu-id="ae44b-119">realm</span></span>|<span data-ttu-id="ae44b-120">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="ae44b-120">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="ae44b-121">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="ae44b-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="ae44b-122">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="ae44b-122">policyEnforcement</span></span>|<span data-ttu-id="ae44b-123">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="ae44b-123">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="ae44b-124">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="ae44b-124">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="ae44b-125">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="ae44b-125">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="ae44b-126">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae44b-126">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="ae44b-127">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="ae44b-127">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="ae44b-128">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="ae44b-128">protectionScenario</span></span>|<span data-ttu-id="ae44b-129">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="ae44b-129">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="ae44b-130">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="ae44b-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ae44b-131">Value</span><span class="sxs-lookup"><span data-stu-id="ae44b-131">Value</span></span>|<span data-ttu-id="ae44b-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae44b-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae44b-133">None</span><span class="sxs-lookup"><span data-stu-id="ae44b-133">None</span></span>|<span data-ttu-id="ae44b-134">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="ae44b-134">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="ae44b-135">Básico</span><span class="sxs-lookup"><span data-stu-id="ae44b-135">Basic</span></span>|<span data-ttu-id="ae44b-136">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="ae44b-136">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="ae44b-137">Digest</span><span class="sxs-lookup"><span data-stu-id="ae44b-137">Digest</span></span>|<span data-ttu-id="ae44b-138">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="ae44b-138">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="ae44b-139">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ae44b-139">Ntlm</span></span>|<span data-ttu-id="ae44b-140">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="ae44b-140">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="ae44b-141">Windows</span><span class="sxs-lookup"><span data-stu-id="ae44b-141">Windows</span></span>|<span data-ttu-id="ae44b-142">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="ae44b-142">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="ae44b-143">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="ae44b-143">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ae44b-144">Value</span><span class="sxs-lookup"><span data-stu-id="ae44b-144">Value</span></span>|<span data-ttu-id="ae44b-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae44b-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae44b-146">None</span><span class="sxs-lookup"><span data-stu-id="ae44b-146">None</span></span>|<span data-ttu-id="ae44b-147">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="ae44b-147">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="ae44b-148">Básico</span><span class="sxs-lookup"><span data-stu-id="ae44b-148">Basic</span></span>|<span data-ttu-id="ae44b-149">Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="ae44b-149">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="ae44b-150">Digest</span><span class="sxs-lookup"><span data-stu-id="ae44b-150">Digest</span></span>|<span data-ttu-id="ae44b-151">Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="ae44b-151">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="ae44b-152">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ae44b-152">Ntlm</span></span>|<span data-ttu-id="ae44b-153">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="ae44b-153">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="ae44b-154">Windows</span><span class="sxs-lookup"><span data-stu-id="ae44b-154">Windows</span></span>|<span data-ttu-id="ae44b-155">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="ae44b-155">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="ae44b-156">Certificado</span><span class="sxs-lookup"><span data-stu-id="ae44b-156">Certificate</span></span>|<span data-ttu-id="ae44b-157">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="ae44b-157">Performs client authentication using a certificate.</span></span> <span data-ttu-id="ae44b-158">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="ae44b-158">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae44b-159">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ae44b-159">Child Elements</span></span>  

 <span data-ttu-id="ae44b-160">None</span><span class="sxs-lookup"><span data-stu-id="ae44b-160">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae44b-161">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ae44b-161">Parent Elements</span></span>  
  
|<span data-ttu-id="ae44b-162">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae44b-162">Element</span></span>|<span data-ttu-id="ae44b-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae44b-163">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="ae44b-164">Define las funciones de seguridad para [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ae44b-164">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ae44b-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae44b-165">Example</span></span>  

 <span data-ttu-id="ae44b-166">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="ae44b-166">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="ae44b-167">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae44b-167">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae44b-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae44b-168">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="ae44b-169">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ae44b-169">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ae44b-170">Enlaces</span><span class="sxs-lookup"><span data-stu-id="ae44b-170">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ae44b-171">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ae44b-171">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ae44b-172">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ae44b-172">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

---
title: <transport> de <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732810"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="8a828-102">\<transport> de \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="8a828-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="8a828-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a828-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="8a828-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a828-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a828-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a828-105">Attributes and Elements</span></span>  
 <span data-ttu-id="8a828-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a828-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a828-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a828-107">Attributes</span></span>  
  
|<span data-ttu-id="8a828-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a828-108">Attribute</span></span>|<span data-ttu-id="8a828-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a828-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a828-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a828-110">clientCredentialType</span></span>|<span data-ttu-id="8a828-111">: Especifica el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a828-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="8a828-112">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="8a828-112">The default is `None`.</span></span> <span data-ttu-id="8a828-113">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8a828-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8a828-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a828-114">proxyCredentialType</span></span>|<span data-ttu-id="8a828-115">: Especifica el tipo de credencial que se va a usar al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a828-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="8a828-116">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="8a828-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="8a828-117">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8a828-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="8a828-118">realm</span><span class="sxs-lookup"><span data-stu-id="8a828-118">realm</span></span>|<span data-ttu-id="8a828-119">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="8a828-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="8a828-120">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="8a828-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="8a828-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8a828-121">policyEnforcement</span></span>|<span data-ttu-id="8a828-122">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8a828-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8a828-123">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="8a828-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8a828-124">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="8a828-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8a828-125">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="8a828-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8a828-126">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="8a828-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="8a828-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="8a828-127">protectionScenario</span></span>|<span data-ttu-id="8a828-128">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="8a828-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8a828-129">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a828-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8a828-130">Value</span><span class="sxs-lookup"><span data-stu-id="8a828-130">Value</span></span>|<span data-ttu-id="8a828-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a828-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a828-132">None</span><span class="sxs-lookup"><span data-stu-id="8a828-132">None</span></span>|<span data-ttu-id="8a828-133">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="8a828-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8a828-134">Básico</span><span class="sxs-lookup"><span data-stu-id="8a828-134">Basic</span></span>|<span data-ttu-id="8a828-135">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="8a828-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="8a828-136">Digest</span><span class="sxs-lookup"><span data-stu-id="8a828-136">Digest</span></span>|<span data-ttu-id="8a828-137">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="8a828-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="8a828-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8a828-138">Ntlm</span></span>|<span data-ttu-id="8a828-139">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="8a828-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8a828-140">Windows</span><span class="sxs-lookup"><span data-stu-id="8a828-140">Windows</span></span>|<span data-ttu-id="8a828-141">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="8a828-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="8a828-142">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a828-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8a828-143">Value</span><span class="sxs-lookup"><span data-stu-id="8a828-143">Value</span></span>|<span data-ttu-id="8a828-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a828-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a828-145">None</span><span class="sxs-lookup"><span data-stu-id="8a828-145">None</span></span>|<span data-ttu-id="8a828-146">: Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="8a828-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8a828-147">Básico</span><span class="sxs-lookup"><span data-stu-id="8a828-147">Basic</span></span>|<span data-ttu-id="8a828-148">Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="8a828-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8a828-149">Digest</span><span class="sxs-lookup"><span data-stu-id="8a828-149">Digest</span></span>|<span data-ttu-id="8a828-150">Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="8a828-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8a828-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8a828-151">Ntlm</span></span>|<span data-ttu-id="8a828-152">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="8a828-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8a828-153">Windows</span><span class="sxs-lookup"><span data-stu-id="8a828-153">Windows</span></span>|<span data-ttu-id="8a828-154">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="8a828-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="8a828-155">Certificado</span><span class="sxs-lookup"><span data-stu-id="8a828-155">Certificate</span></span>|<span data-ttu-id="8a828-156">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="8a828-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="8a828-157">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="8a828-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a828-158">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a828-158">Child Elements</span></span>  
 <span data-ttu-id="8a828-159">None</span><span class="sxs-lookup"><span data-stu-id="8a828-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a828-160">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a828-160">Parent Elements</span></span>  
  
|<span data-ttu-id="8a828-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a828-161">Element</span></span>|<span data-ttu-id="8a828-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a828-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="8a828-163">Define las funciones de seguridad para [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8a828-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a828-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a828-164">Example</span></span>  
 <span data-ttu-id="8a828-165">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="8a828-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="8a828-166">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a828-166">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8a828-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a828-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="8a828-168">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a828-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8a828-169">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8a828-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8a828-170">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8a828-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8a828-171">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a828-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

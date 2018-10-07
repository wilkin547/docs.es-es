---
title: Elemento &lt;transport&gt; de &lt;basicHttpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: f4e37281539106fef93dc4ab566d94d781c39d29
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845682"
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a><span data-ttu-id="e3cac-102">Elemento &lt;transport&gt; de &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e3cac-102">&lt;transport&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="e3cac-103">Define las propiedades que controlan los parámetros de autenticación para el transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3cac-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="e3cac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e3cac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3cac-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="e3cac-105">\<bindings></span></span>  
<span data-ttu-id="e3cac-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e3cac-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="e3cac-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e3cac-107">\<binding></span></span>  
<span data-ttu-id="e3cac-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e3cac-108">\<security></span></span>  
<span data-ttu-id="e3cac-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="e3cac-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cac-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3cac-110">Syntax</span></span>  
  
```xml  
<basicHttpBinding>  
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
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3cac-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e3cac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e3cac-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e3cac-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3cac-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e3cac-113">Attributes</span></span>  
  
|<span data-ttu-id="e3cac-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e3cac-114">Attribute</span></span>|<span data-ttu-id="e3cac-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cac-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3cac-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3cac-116">clientCredentialType</span></span>|<span data-ttu-id="e3cac-117">: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente mediante la autenticación HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3cac-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="e3cac-118">De manera predeterminada, es `None`.</span><span class="sxs-lookup"><span data-stu-id="e3cac-118">The default is `None`.</span></span> <span data-ttu-id="e3cac-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3cac-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="e3cac-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3cac-120">proxyCredentialType</span></span>|<span data-ttu-id="e3cac-121">: Especifica el tipo de credencial que se usará al realizar la autenticación de cliente desde dentro de un dominio mediante un proxy a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3cac-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="e3cac-122">Este atributo solo es aplicable cuando el atributo `mode` del elemento `security` primario es `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="e3cac-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="e3cac-123">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3cac-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="e3cac-124">realm</span><span class="sxs-lookup"><span data-stu-id="e3cac-124">realm</span></span>|<span data-ttu-id="e3cac-125">Una cadena que especifica el dominio kerberos utilizado por el esquema de autenticación de HTTP para la autenticación básica o implícita.</span><span class="sxs-lookup"><span data-stu-id="e3cac-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="e3cac-126">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="e3cac-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="e3cac-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="e3cac-127">policyEnforcement</span></span>|<span data-ttu-id="e3cac-128">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="e3cac-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e3cac-129">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="e3cac-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e3cac-130">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="e3cac-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e3cac-131">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="e3cac-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e3cac-132">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="e3cac-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="e3cac-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="e3cac-133">protectionScenario</span></span>|<span data-ttu-id="e3cac-134">Esta enumeración especifica el escenario de protección que exige la directiva.</span><span class="sxs-lookup"><span data-stu-id="e3cac-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e3cac-135">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3cac-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e3cac-136">Valor</span><span class="sxs-lookup"><span data-stu-id="e3cac-136">Value</span></span>|<span data-ttu-id="e3cac-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cac-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3cac-138">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e3cac-138">None</span></span>|<span data-ttu-id="e3cac-139">Los mensajes no se protegen durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="e3cac-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e3cac-140">Básico</span><span class="sxs-lookup"><span data-stu-id="e3cac-140">Basic</span></span>|<span data-ttu-id="e3cac-141">Especifica la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="e3cac-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="e3cac-142">Implícita</span><span class="sxs-lookup"><span data-stu-id="e3cac-142">Digest</span></span>|<span data-ttu-id="e3cac-143">Especifica la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="e3cac-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="e3cac-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e3cac-144">Ntlm</span></span>|<span data-ttu-id="e3cac-145">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="e3cac-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e3cac-146">Windows</span><span class="sxs-lookup"><span data-stu-id="e3cac-146">Windows</span></span>|<span data-ttu-id="e3cac-147">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="e3cac-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e3cac-148">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3cac-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e3cac-149">Valor</span><span class="sxs-lookup"><span data-stu-id="e3cac-149">Value</span></span>|<span data-ttu-id="e3cac-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cac-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e3cac-151">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e3cac-151">None</span></span>|<span data-ttu-id="e3cac-152">-Los mensajes no están protegidos durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="e3cac-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e3cac-153">Básico</span><span class="sxs-lookup"><span data-stu-id="e3cac-153">Basic</span></span>|<span data-ttu-id="e3cac-154">Especifica la autenticación básica como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita.</span><span class="sxs-lookup"><span data-stu-id="e3cac-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e3cac-155">Implícita</span><span class="sxs-lookup"><span data-stu-id="e3cac-155">Digest</span></span>|<span data-ttu-id="e3cac-156">Especifica la autenticación implícita como se define en la autenticación RFC 2617 de HTTP: Autenticación básica e implícita</span><span class="sxs-lookup"><span data-stu-id="e3cac-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e3cac-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e3cac-157">Ntlm</span></span>|<span data-ttu-id="e3cac-158">Especifica la autenticación NTLM cuando sea posible y si la autenticación de Windows falla.</span><span class="sxs-lookup"><span data-stu-id="e3cac-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e3cac-159">Windows</span><span class="sxs-lookup"><span data-stu-id="e3cac-159">Windows</span></span>|<span data-ttu-id="e3cac-160">Especifica la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="e3cac-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="e3cac-161">Certificado</span><span class="sxs-lookup"><span data-stu-id="e3cac-161">Certificate</span></span>|<span data-ttu-id="e3cac-162">Realiza la autenticación del cliente mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="e3cac-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="e3cac-163">Esta opción solo funciona si el atributo `Mode` del elemento `security` primario se establece como Transport, y no funciona si está establecido como TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="e3cac-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3cac-164">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e3cac-164">Child Elements</span></span>  
 <span data-ttu-id="e3cac-165">Ninguna</span><span class="sxs-lookup"><span data-stu-id="e3cac-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3cac-166">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e3cac-166">Parent Elements</span></span>  
  
|<span data-ttu-id="e3cac-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3cac-167">Element</span></span>|<span data-ttu-id="e3cac-168">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3cac-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3cac-169">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="e3cac-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="e3cac-170">Define las funciones de seguridad para el [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e3cac-170">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3cac-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3cac-171">Example</span></span>  
 <span data-ttu-id="e3cac-172">El ejemplo siguiente muestra el uso de seguridad de transporte de SSL con el enlace básico.</span><span class="sxs-lookup"><span data-stu-id="e3cac-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="e3cac-173">De forma predeterminada, el enlace básico soporta la comunicación HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3cac-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3cac-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3cac-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="e3cac-175">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e3cac-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e3cac-176">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e3cac-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e3cac-177">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e3cac-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e3cac-178">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e3cac-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="e3cac-179">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="e3cac-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

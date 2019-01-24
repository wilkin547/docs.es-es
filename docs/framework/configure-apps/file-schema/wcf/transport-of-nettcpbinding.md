---
title: Elemento &lt;transport&gt; de &lt;netTcpBinding&gt;
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 7372b94bde8325ec00116ee7022739f1b17a1ac9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555497"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="7f21c-102">Elemento &lt;transport&gt; de &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="7f21c-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="7f21c-103">Define el tipo de requisitos de seguridad de nivel de mensaje para un extremo configurado con el [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7f21c-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="7f21c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7f21c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7f21c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7f21c-105">\<bindings></span></span>  
<span data-ttu-id="7f21c-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="7f21c-106">\<netTcpBinding></span></span>  
<span data-ttu-id="7f21c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7f21c-107">\<binding></span></span>  
<span data-ttu-id="7f21c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="7f21c-108">\<security></span></span>  
<span data-ttu-id="7f21c-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="7f21c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f21c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f21c-110">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f21c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f21c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7f21c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f21c-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f21c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f21c-113">Attributes</span></span>  
  
|<span data-ttu-id="7f21c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f21c-114">Attribute</span></span>|<span data-ttu-id="7f21c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f21c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f21c-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7f21c-116">clientCredentialType</span></span>|<span data-ttu-id="7f21c-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7f21c-117">Optional.</span></span> <span data-ttu-id="7f21c-118">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="7f21c-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="7f21c-119">-El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="7f21c-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="7f21c-120">: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7f21c-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="7f21c-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7f21c-121">protectionLevel</span></span>|<span data-ttu-id="7f21c-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7f21c-122">Optional.</span></span> <span data-ttu-id="7f21c-123">Define la seguridad en el nivel del transporte del TCP.</span><span class="sxs-lookup"><span data-stu-id="7f21c-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="7f21c-124">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="7f21c-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="7f21c-125">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="7f21c-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="7f21c-126">El valor predeterminado es `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="7f21c-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="7f21c-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="7f21c-127">sslProtocols</span></span>|<span data-ttu-id="7f21c-128">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="7f21c-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="7f21c-129">El valor predeterminado es Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="7f21c-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="7f21c-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="7f21c-130">policyEnforcement</span></span>|<span data-ttu-id="7f21c-131">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="7f21c-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="7f21c-132">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="7f21c-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="7f21c-133">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="7f21c-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="7f21c-134">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="7f21c-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="7f21c-135">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="7f21c-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="7f21c-136">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7f21c-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="7f21c-137">Valor</span><span class="sxs-lookup"><span data-stu-id="7f21c-137">Value</span></span>|<span data-ttu-id="7f21c-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f21c-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7f21c-139">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7f21c-139">None</span></span>|<span data-ttu-id="7f21c-140">El cliente es anónimo.</span><span class="sxs-lookup"><span data-stu-id="7f21c-140">The client is anonymous.</span></span> <span data-ttu-id="7f21c-141">Esto requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="7f21c-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="7f21c-142">Windows</span><span class="sxs-lookup"><span data-stu-id="7f21c-142">Windows</span></span>|<span data-ttu-id="7f21c-143">Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="7f21c-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="7f21c-144">Certificado</span><span class="sxs-lookup"><span data-stu-id="7f21c-144">Certificate</span></span>|<span data-ttu-id="7f21c-145">El cliente se autentica utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="7f21c-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="7f21c-146">Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="7f21c-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="7f21c-147">Atributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="7f21c-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="7f21c-148">Valor</span><span class="sxs-lookup"><span data-stu-id="7f21c-148">Value</span></span>|<span data-ttu-id="7f21c-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f21c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7f21c-150">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7f21c-150">None</span></span>|<span data-ttu-id="7f21c-151">Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="7f21c-151">No protection.</span></span>|  
|<span data-ttu-id="7f21c-152">Signo</span><span class="sxs-lookup"><span data-stu-id="7f21c-152">Sign</span></span>|<span data-ttu-id="7f21c-153">Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7f21c-153">Messages are signed.</span></span>|  
|<span data-ttu-id="7f21c-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="7f21c-154">EncryptAndSign</span></span>|<span data-ttu-id="7f21c-155">-Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="7f21c-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f21c-156">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f21c-156">Child Elements</span></span>  
 <span data-ttu-id="7f21c-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="7f21c-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f21c-158">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f21c-158">Parent Elements</span></span>  
  
|<span data-ttu-id="7f21c-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f21c-159">Element</span></span>|<span data-ttu-id="7f21c-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f21c-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f21c-161">\<security></span><span class="sxs-lookup"><span data-stu-id="7f21c-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="7f21c-162">Especifica las capacidades de seguridad de la [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7f21c-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f21c-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f21c-163">Remarks</span></span>  
 <span data-ttu-id="7f21c-164">Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="7f21c-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="7f21c-165">Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows (Negotiate) o SSL sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="7f21c-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f21c-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f21c-166">See also</span></span>
- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="7f21c-167">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7f21c-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7f21c-168">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7f21c-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7f21c-169">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7f21c-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7f21c-170">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7f21c-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7f21c-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="7f21c-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

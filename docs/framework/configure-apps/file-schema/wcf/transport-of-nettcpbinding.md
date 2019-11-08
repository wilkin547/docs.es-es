---
title: <transport> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735932"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="17c0b-102">\<transport> de \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="17c0b-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="17c0b-103">Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con el [\<netTcpBinding](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="17c0b-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="17c0b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="17c0b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="17c0b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="17c0b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="17c0b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="17c0b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="17c0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**netTcpBinding**](nettcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="17c0b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="17c0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="17c0b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="17c0b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-nettcpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="17c0b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="17c0b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="17c0b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c0b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17c0b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17c0b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="17c0b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="17c0b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="17c0b-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17c0b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="17c0b-114">Attributes</span></span>  
  
|<span data-ttu-id="17c0b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="17c0b-115">Attribute</span></span>|<span data-ttu-id="17c0b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="17c0b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17c0b-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="17c0b-117">clientCredentialType</span></span>|<span data-ttu-id="17c0b-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="17c0b-118">Optional.</span></span> <span data-ttu-id="17c0b-119">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="17c0b-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="17c0b-120">-El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="17c0b-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="17c0b-121">: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="17c0b-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="17c0b-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="17c0b-122">protectionLevel</span></span>|<span data-ttu-id="17c0b-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="17c0b-123">Optional.</span></span> <span data-ttu-id="17c0b-124">Define la seguridad en el nivel del transporte del TCP.</span><span class="sxs-lookup"><span data-stu-id="17c0b-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="17c0b-125">Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.</span><span class="sxs-lookup"><span data-stu-id="17c0b-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="17c0b-126">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="17c0b-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="17c0b-127">El valor predeterminado es `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="17c0b-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="17c0b-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="17c0b-128">sslProtocols</span></span>|<span data-ttu-id="17c0b-129">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="17c0b-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="17c0b-130">El valor predeterminado es&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="17c0b-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="17c0b-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="17c0b-131">policyEnforcement</span></span>|<span data-ttu-id="17c0b-132">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="17c0b-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="17c0b-133">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="17c0b-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="17c0b-134">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="17c0b-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="17c0b-135">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="17c0b-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="17c0b-136">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="17c0b-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="17c0b-137">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="17c0b-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="17c0b-138">Valor</span><span class="sxs-lookup"><span data-stu-id="17c0b-138">Value</span></span>|<span data-ttu-id="17c0b-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="17c0b-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="17c0b-140">Ninguno</span><span class="sxs-lookup"><span data-stu-id="17c0b-140">None</span></span>|<span data-ttu-id="17c0b-141">El cliente es anónimo.</span><span class="sxs-lookup"><span data-stu-id="17c0b-141">The client is anonymous.</span></span> <span data-ttu-id="17c0b-142">Esto requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="17c0b-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="17c0b-143">Windows</span><span class="sxs-lookup"><span data-stu-id="17c0b-143">Windows</span></span>|<span data-ttu-id="17c0b-144">Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="17c0b-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="17c0b-145">Certificado</span><span class="sxs-lookup"><span data-stu-id="17c0b-145">Certificate</span></span>|<span data-ttu-id="17c0b-146">El cliente se autentica utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="17c0b-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="17c0b-147">Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="17c0b-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="17c0b-148">Atributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="17c0b-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="17c0b-149">Valor</span><span class="sxs-lookup"><span data-stu-id="17c0b-149">Value</span></span>|<span data-ttu-id="17c0b-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="17c0b-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="17c0b-151">Ninguno</span><span class="sxs-lookup"><span data-stu-id="17c0b-151">None</span></span>|<span data-ttu-id="17c0b-152">Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="17c0b-152">No protection.</span></span>|  
|<span data-ttu-id="17c0b-153">Signo</span><span class="sxs-lookup"><span data-stu-id="17c0b-153">Sign</span></span>|<span data-ttu-id="17c0b-154">Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="17c0b-154">Messages are signed.</span></span>|  
|<span data-ttu-id="17c0b-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="17c0b-155">EncryptAndSign</span></span>|<span data-ttu-id="17c0b-156">-Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="17c0b-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17c0b-157">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="17c0b-157">Child Elements</span></span>  
 <span data-ttu-id="17c0b-158">Ninguno</span><span class="sxs-lookup"><span data-stu-id="17c0b-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17c0b-159">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="17c0b-159">Parent Elements</span></span>  
  
|<span data-ttu-id="17c0b-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="17c0b-160">Element</span></span>|<span data-ttu-id="17c0b-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="17c0b-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17c0b-162">\<La ></span><span class="sxs-lookup"><span data-stu-id="17c0b-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="17c0b-163">Especifica las capacidades de seguridad del [> de\<netTcpBinding](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="17c0b-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17c0b-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17c0b-164">Remarks</span></span>  
 <span data-ttu-id="17c0b-165">Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="17c0b-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="17c0b-166">Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows (Negotiate) o SSL sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="17c0b-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c0b-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="17c0b-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="17c0b-168">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="17c0b-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="17c0b-169">Enlaces</span><span class="sxs-lookup"><span data-stu-id="17c0b-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="17c0b-170">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="17c0b-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="17c0b-171">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="17c0b-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="17c0b-172">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="17c0b-172">\<binding></span></span>](bindings.md)

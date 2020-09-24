---
title: <transport> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 8f752373c51992c51b747f5f4dc4a63910a387c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162197"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="8e9d4-102">\<transport> de \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="8e9d4-102">\<transport> of \<netTcpBinding></span></span>

<span data-ttu-id="8e9d4-103">Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8e9d4-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="8e9d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e9d4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e9d4-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e9d4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8e9d4-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e9d4-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e9d4-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e9d4-107">Attributes</span></span>  
  
|<span data-ttu-id="8e9d4-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e9d4-108">Attribute</span></span>|<span data-ttu-id="8e9d4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e9d4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e9d4-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8e9d4-110">clientCredentialType</span></span>|<span data-ttu-id="8e9d4-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-111">Optional.</span></span> <span data-ttu-id="8e9d4-112">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-112">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="8e9d4-113">-El valor predeterminado es `Windows` .</span><span class="sxs-lookup"><span data-stu-id="8e9d4-113">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="8e9d4-114">: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="8e9d4-114">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8e9d4-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8e9d4-115">protectionLevel</span></span>|<span data-ttu-id="8e9d4-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-116">Optional.</span></span> <span data-ttu-id="8e9d4-117">Define la seguridad en el nivel del transporte del TCP.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-117">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="8e9d4-118">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="8e9d4-119">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-119">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="8e9d4-120">El valor predeterminado es `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-120">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="8e9d4-121">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="8e9d4-121">sslProtocols</span></span>|<span data-ttu-id="8e9d4-122">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-122">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="8e9d4-123">El valor predeterminado es TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-123">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="8e9d4-124">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8e9d4-124">policyEnforcement</span></span>|<span data-ttu-id="8e9d4-125">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-125">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8e9d4-126">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="8e9d4-126">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8e9d4-127">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-127">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8e9d4-128">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-128">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8e9d4-129">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-129">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8e9d4-130">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8e9d4-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8e9d4-131">Valor</span><span class="sxs-lookup"><span data-stu-id="8e9d4-131">Value</span></span>|<span data-ttu-id="8e9d4-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e9d4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e9d4-133">None</span><span class="sxs-lookup"><span data-stu-id="8e9d4-133">None</span></span>|<span data-ttu-id="8e9d4-134">El cliente es anónimo.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-134">The client is anonymous.</span></span> <span data-ttu-id="8e9d4-135">Esto requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-135">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="8e9d4-136">Windows</span><span class="sxs-lookup"><span data-stu-id="8e9d4-136">Windows</span></span>|<span data-ttu-id="8e9d4-137">Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="8e9d4-137">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="8e9d4-138">Certificado</span><span class="sxs-lookup"><span data-stu-id="8e9d4-138">Certificate</span></span>|<span data-ttu-id="8e9d4-139">El cliente se autentica utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-139">The client is authenticated using a certificate.</span></span> <span data-ttu-id="8e9d4-140">Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-140">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="8e9d4-141">Atributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8e9d4-141">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="8e9d4-142">Valor</span><span class="sxs-lookup"><span data-stu-id="8e9d4-142">Value</span></span>|<span data-ttu-id="8e9d4-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e9d4-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e9d4-144">None</span><span class="sxs-lookup"><span data-stu-id="8e9d4-144">None</span></span>|<span data-ttu-id="8e9d4-145">Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="8e9d4-145">No protection.</span></span>|  
|<span data-ttu-id="8e9d4-146">Firma</span><span class="sxs-lookup"><span data-stu-id="8e9d4-146">Sign</span></span>|<span data-ttu-id="8e9d4-147">Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-147">Messages are signed.</span></span>|  
|<span data-ttu-id="8e9d4-148">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="8e9d4-148">EncryptAndSign</span></span>|<span data-ttu-id="8e9d4-149">-Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-149">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e9d4-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e9d4-150">Child Elements</span></span>  

 <span data-ttu-id="8e9d4-151">None</span><span class="sxs-lookup"><span data-stu-id="8e9d4-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e9d4-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e9d4-152">Parent Elements</span></span>  
  
|<span data-ttu-id="8e9d4-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e9d4-153">Element</span></span>|<span data-ttu-id="8e9d4-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e9d4-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="8e9d4-155">Especifica las capacidades de seguridad de [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8e9d4-155">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e9d4-156">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e9d4-156">Remarks</span></span>  

 <span data-ttu-id="8e9d4-157">Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-157">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="8e9d4-158">Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows (Negotiate) o SSL sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="8e9d4-158">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9d4-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e9d4-159">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="8e9d4-160">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8e9d4-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8e9d4-161">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8e9d4-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8e9d4-162">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8e9d4-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8e9d4-163">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8e9d4-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

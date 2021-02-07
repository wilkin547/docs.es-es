---
description: 'Más información sobre: <transport> de <netTcpBinding>'
title: <transport> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 9005de300b41c9f53c62875ee185d0f8a3ee8d7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664553"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="8700c-103">\<transport> de \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="8700c-103">\<transport> of \<netTcpBinding></span></span>

<span data-ttu-id="8700c-104">Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8700c-104">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="8700c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8700c-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8700c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8700c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8700c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8700c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8700c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8700c-108">Attributes</span></span>  
  
|<span data-ttu-id="8700c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8700c-109">Attribute</span></span>|<span data-ttu-id="8700c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8700c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8700c-111">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8700c-111">clientCredentialType</span></span>|<span data-ttu-id="8700c-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8700c-112">Optional.</span></span> <span data-ttu-id="8700c-113">Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="8700c-113">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="8700c-114">-El valor predeterminado es `Windows` .</span><span class="sxs-lookup"><span data-stu-id="8700c-114">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="8700c-115">: Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="8700c-115">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8700c-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8700c-116">protectionLevel</span></span>|<span data-ttu-id="8700c-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8700c-117">Optional.</span></span> <span data-ttu-id="8700c-118">Define la seguridad en el nivel del transporte del TCP.</span><span class="sxs-lookup"><span data-stu-id="8700c-118">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="8700c-119">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="8700c-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="8700c-120">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="8700c-120">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="8700c-121">El valor predeterminado es `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="8700c-121">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="8700c-122">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="8700c-122">sslProtocols</span></span>|<span data-ttu-id="8700c-123">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="8700c-123">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="8700c-124">El valor predeterminado es TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="8700c-124">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="8700c-125">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8700c-125">policyEnforcement</span></span>|<span data-ttu-id="8700c-126">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8700c-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8700c-127">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="8700c-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8700c-128">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="8700c-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8700c-129">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="8700c-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8700c-130">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="8700c-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8700c-131">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8700c-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8700c-132">Value</span><span class="sxs-lookup"><span data-stu-id="8700c-132">Value</span></span>|<span data-ttu-id="8700c-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="8700c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8700c-134">None</span><span class="sxs-lookup"><span data-stu-id="8700c-134">None</span></span>|<span data-ttu-id="8700c-135">El cliente es anónimo.</span><span class="sxs-lookup"><span data-stu-id="8700c-135">The client is anonymous.</span></span> <span data-ttu-id="8700c-136">Esto requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="8700c-136">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="8700c-137">Windows</span><span class="sxs-lookup"><span data-stu-id="8700c-137">Windows</span></span>|<span data-ttu-id="8700c-138">Especifica la autenticación de Windows del cliente utilizando Negotiation de SP (negociación de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="8700c-138">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="8700c-139">Certificado</span><span class="sxs-lookup"><span data-stu-id="8700c-139">Certificate</span></span>|<span data-ttu-id="8700c-140">El cliente se autentica utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="8700c-140">The client is authenticated using a certificate.</span></span> <span data-ttu-id="8700c-141">Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="8700c-141">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="8700c-142">Atributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="8700c-142">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="8700c-143">Value</span><span class="sxs-lookup"><span data-stu-id="8700c-143">Value</span></span>|<span data-ttu-id="8700c-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="8700c-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8700c-145">None</span><span class="sxs-lookup"><span data-stu-id="8700c-145">None</span></span>|<span data-ttu-id="8700c-146">Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="8700c-146">No protection.</span></span>|  
|<span data-ttu-id="8700c-147">Signo</span><span class="sxs-lookup"><span data-stu-id="8700c-147">Sign</span></span>|<span data-ttu-id="8700c-148">Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8700c-148">Messages are signed.</span></span>|  
|<span data-ttu-id="8700c-149">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="8700c-149">EncryptAndSign</span></span>|<span data-ttu-id="8700c-150">-Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="8700c-150">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8700c-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8700c-151">Child Elements</span></span>  

 <span data-ttu-id="8700c-152">None</span><span class="sxs-lookup"><span data-stu-id="8700c-152">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8700c-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8700c-153">Parent Elements</span></span>  
  
|<span data-ttu-id="8700c-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="8700c-154">Element</span></span>|<span data-ttu-id="8700c-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="8700c-155">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="8700c-156">Especifica las capacidades de seguridad de [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="8700c-156">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8700c-157">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8700c-157">Remarks</span></span>  

 <span data-ttu-id="8700c-158">Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="8700c-158">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="8700c-159">Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows (Negotiate) o SSL sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="8700c-159">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8700c-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="8700c-160">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="8700c-161">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8700c-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8700c-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8700c-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8700c-163">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8700c-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8700c-164">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8700c-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

---
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ede4103f9c8f2f73ac34036fe7a58242e32350e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934690"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="21e45-102">\<> de transporte \<de netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="21e45-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="21e45-103">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="21e45-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="21e45-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="21e45-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="21e45-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="21e45-105">\<bindings></span></span>  
<span data-ttu-id="21e45-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="21e45-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="21e45-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="21e45-107">\<binding></span></span>  
<span data-ttu-id="21e45-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="21e45-108">\<security></span></span>  
<span data-ttu-id="21e45-109">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="21e45-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e45-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21e45-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21e45-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21e45-111">Attributes and Elements</span></span>  
 <span data-ttu-id="21e45-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21e45-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21e45-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="21e45-113">Attributes</span></span>  
  
|<span data-ttu-id="21e45-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="21e45-114">Attribute</span></span>|<span data-ttu-id="21e45-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21e45-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21e45-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="21e45-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="21e45-117">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="21e45-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="21e45-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="21e45-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="21e45-119">Ninguna Sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="21e45-119">-   None: No authentication.</span></span><br /><span data-ttu-id="21e45-120">-   WindowsDomain: El mecanismo de autenticación utiliza Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="21e45-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="21e45-121">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="21e45-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="21e45-122">Certificado El canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="21e45-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="21e45-123">El valor predeterminado es `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="21e45-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="21e45-124">Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`.</span><span class="sxs-lookup"><span data-stu-id="21e45-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="21e45-125">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="21e45-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="21e45-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="21e45-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="21e45-127">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="21e45-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="21e45-128">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="21e45-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="21e45-129">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="21e45-129">-   RC4Stream</span></span><br /><span data-ttu-id="21e45-130">-AES</span><span class="sxs-lookup"><span data-stu-id="21e45-130">-   AES</span></span><br /><span data-ttu-id="21e45-131">-El valor predeterminado es `RC4Stream`.</span><span class="sxs-lookup"><span data-stu-id="21e45-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="21e45-132">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="21e45-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="21e45-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="21e45-133">msmqProtectionLevel</span></span>|<span data-ttu-id="21e45-134">Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="21e45-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="21e45-135">El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio.</span><span class="sxs-lookup"><span data-stu-id="21e45-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="21e45-136">Es decir, el mensaje procedió del remitente y el remitente es quien dice ser.</span><span class="sxs-lookup"><span data-stu-id="21e45-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="21e45-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="21e45-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="21e45-138">Ninguna Ninguna protección</span><span class="sxs-lookup"><span data-stu-id="21e45-138">-   None: No protection.</span></span><br /><span data-ttu-id="21e45-139">Sesión Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="21e45-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="21e45-140">-   EncryptAndSign: Los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="21e45-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="21e45-141">-El valor predeterminado `Sign`es.</span><span class="sxs-lookup"><span data-stu-id="21e45-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="21e45-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="21e45-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="21e45-143">Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje.</span><span class="sxs-lookup"><span data-stu-id="21e45-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="21e45-144">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="21e45-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="21e45-145">-MD5</span><span class="sxs-lookup"><span data-stu-id="21e45-145">-   MD5</span></span><br /><span data-ttu-id="21e45-146">-SHA1</span><span class="sxs-lookup"><span data-stu-id="21e45-146">-   SHA1</span></span><br /><span data-ttu-id="21e45-147">-SHA256</span><span class="sxs-lookup"><span data-stu-id="21e45-147">-   SHA256</span></span><br /><span data-ttu-id="21e45-148">-SHA512</span><span class="sxs-lookup"><span data-stu-id="21e45-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="21e45-149">El valor predeterminado es `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="21e45-149">The default is `SHA1`.</span></span> <span data-ttu-id="21e45-150">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="21e45-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="21e45-151">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="21e45-151">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21e45-152">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21e45-152">Child Elements</span></span>  
 <span data-ttu-id="21e45-153">None</span><span class="sxs-lookup"><span data-stu-id="21e45-153">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21e45-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21e45-154">Parent Elements</span></span>  
  
|<span data-ttu-id="21e45-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="21e45-155">Element</span></span>|<span data-ttu-id="21e45-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21e45-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21e45-157">\<security></span><span class="sxs-lookup"><span data-stu-id="21e45-157">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="21e45-158">Define los valores de seguridad de transporte para transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="21e45-158">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21e45-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="21e45-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="21e45-160">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="21e45-160">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="21e45-161">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="21e45-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="21e45-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="21e45-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="21e45-163">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="21e45-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="21e45-164">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="21e45-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="21e45-165">\<binding></span><span class="sxs-lookup"><span data-stu-id="21e45-165">\<binding></span></span>](../../../misc/binding.md)

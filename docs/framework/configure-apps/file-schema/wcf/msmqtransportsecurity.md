---
title: '&lt;msmqTransportSecurity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: eee2cb916d79bf3b79e882cd757b10344121f6b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmsmqtransportsecuritygt"></a><span data-ttu-id="f09a7-102">&lt;msmqTransportSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="f09a7-102">&lt;msmqTransportSecurity&gt;</span></span>
<span data-ttu-id="f09a7-103">Especifica la configuración de seguridad de transporte MSMQ para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f09a7-103">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="f09a7-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f09a7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f09a7-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="f09a7-105">\<bindings></span></span>  
<span data-ttu-id="f09a7-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f09a7-106">\<customBinding></span></span>  
<span data-ttu-id="f09a7-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="f09a7-107">\<binding></span></span>  
<span data-ttu-id="f09a7-108">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="f09a7-108">\<msmqIntegration></span></span>  
<span data-ttu-id="f09a7-109">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="f09a7-109">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f09a7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f09a7-110">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f09a7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f09a7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f09a7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f09a7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f09a7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f09a7-113">Attributes</span></span>  
  
|<span data-ttu-id="f09a7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="f09a7-114">Attribute</span></span>|<span data-ttu-id="f09a7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f09a7-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="f09a7-116">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f09a7-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="f09a7-117">Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="f09a7-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="f09a7-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f09a7-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f09a7-119">-None: Sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="f09a7-119">-   None: No authentication.</span></span><br /><span data-ttu-id="f09a7-120">-Windows: El mecanismo de autenticación usa Active Directory para obtener el certificado X.509 para el SID asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="f09a7-120">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="f09a7-121">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="f09a7-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="f09a7-122">-Certificate: El canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="f09a7-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="f09a7-123">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="f09a7-123">The default value is Windows.</span></span> <span data-ttu-id="f09a7-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="f09a7-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="f09a7-125">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f09a7-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="f09a7-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f09a7-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f09a7-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="f09a7-127">-   RC4Stream</span></span><br /><span data-ttu-id="f09a7-128">-AES</span><span class="sxs-lookup"><span data-stu-id="f09a7-128">-   AES</span></span><br /><br /> <span data-ttu-id="f09a7-129">El valor predeterminado RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="f09a7-129">The default value is RC4Stream.</span></span> <span data-ttu-id="f09a7-130">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="f09a7-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="f09a7-131">Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="f09a7-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="f09a7-132">El cifrado asegura la integridad del mensaje mientras EncryptAndSign asegura la integridad del mensaje y el no repudio; es decir, el mensaje procede de hecho del remitente y el remitente es quien dice que es.</span><span class="sxs-lookup"><span data-stu-id="f09a7-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="f09a7-133">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f09a7-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f09a7-134">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="f09a7-134">-   None: No protection.</span></span><br /><span data-ttu-id="f09a7-135">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f09a7-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="f09a7-136">-EncryptAndSign: Los mensajes se cifrarán y firmarán.</span><span class="sxs-lookup"><span data-stu-id="f09a7-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="f09a7-137">El valor predeterminado es Sign.</span><span class="sxs-lookup"><span data-stu-id="f09a7-137">The default value is Sign.</span></span> <span data-ttu-id="f09a7-138">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="f09a7-138">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="f09a7-139">Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas.</span><span class="sxs-lookup"><span data-stu-id="f09a7-139">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="f09a7-140">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f09a7-140">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f09a7-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="f09a7-141">-   MD5</span></span><br /><span data-ttu-id="f09a7-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="f09a7-142">-   SHA1</span></span><br /><span data-ttu-id="f09a7-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="f09a7-143">-   SHA256</span></span><br /><span data-ttu-id="f09a7-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="f09a7-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="f09a7-145">El valor predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="f09a7-145">The default value is SHA1.</span></span> <span data-ttu-id="f09a7-146">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="f09a7-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f09a7-147">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f09a7-147">Child Elements</span></span>  
 <span data-ttu-id="f09a7-148">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f09a7-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f09a7-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f09a7-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f09a7-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="f09a7-150">Element</span></span>|<span data-ttu-id="f09a7-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="f09a7-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f09a7-152">\<msmqIntegration ></span><span class="sxs-lookup"><span data-stu-id="f09a7-152">\<msmqIntegration></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|<span data-ttu-id="f09a7-153">Especifica valores requeridos para la interacción con un remitente o receptor de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="f09a7-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="f09a7-154">\<msmqTransport ></span><span class="sxs-lookup"><span data-stu-id="f09a7-154">\<msmqTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|<span data-ttu-id="f09a7-155">Especifica las propiedades de comunicación de uso de colas de un servicio Windows Communication Foundation (WCF) que usa el protocolo MSMQ nativo.</span><span class="sxs-lookup"><span data-stu-id="f09a7-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f09a7-156">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f09a7-156">Remarks</span></span>  
 <span data-ttu-id="f09a7-157">Para obtener más información sobre la seguridad de transporte, consulte [seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="f09a7-157">For more information on transport security, see [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f09a7-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="f09a7-158">See Also</span></span>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="f09a7-159">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="f09a7-159">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="f09a7-160">Transportes</span><span class="sxs-lookup"><span data-stu-id="f09a7-160">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="f09a7-161">Elegir un transporte</span><span class="sxs-lookup"><span data-stu-id="f09a7-161">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="f09a7-162">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f09a7-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f09a7-163">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f09a7-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f09a7-164">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f09a7-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f09a7-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f09a7-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="f09a7-166">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="f09a7-166">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)

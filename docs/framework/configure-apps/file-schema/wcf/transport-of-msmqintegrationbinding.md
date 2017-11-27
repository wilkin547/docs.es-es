---
title: Elemento &lt;transport&gt; de &lt;msmqIntegrationBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9def7fbd0082cc7fa9d9f18388604383cb71f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="99372-102">Elemento &lt;transport&gt; de &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="99372-102">&lt;transport&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="99372-103">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="99372-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="99372-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="99372-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="99372-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="99372-105">\<bindings></span></span>  
<span data-ttu-id="99372-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="99372-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="99372-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="99372-107">\<binding></span></span>  
<span data-ttu-id="99372-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="99372-108">\<security></span></span>  
<span data-ttu-id="99372-109">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="99372-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99372-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99372-110">Syntax</span></span>  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99372-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99372-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99372-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99372-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99372-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="99372-113">Attributes</span></span>  
  
|<span data-ttu-id="99372-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="99372-114">Attribute</span></span>|<span data-ttu-id="99372-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="99372-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="99372-116">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="99372-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="99372-117">Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="99372-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="99372-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="99372-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99372-119">-None: Sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="99372-119">-   None: No authentication.</span></span><br /><span data-ttu-id="99372-120">-WindowsDomain: El mecanismo de autenticación utiliza Active Directory para obtener el certificado X.509 para el SID asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="99372-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="99372-121">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="99372-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="99372-122">-Certificate: El canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="99372-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="99372-123">El valor predeterminado es WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="99372-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="99372-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="99372-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="99372-125">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="99372-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="99372-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="99372-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="99372-127">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="99372-127">-   RC4Stream</span></span><br /><span data-ttu-id="99372-128">-AES</span><span class="sxs-lookup"><span data-stu-id="99372-128">-   AES</span></span><br /><br /> <span data-ttu-id="99372-129">El valor predeterminado RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="99372-129">The default value is RC4Stream.</span></span> <span data-ttu-id="99372-130">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="99372-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="99372-131">Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="99372-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="99372-132">El cifrado asegura la integridad del mensaje mientras EncryptAndSign asegura la integridad del mensaje y el no repudio; es decir, el mensaje procede de hecho del remitente y el remitente es quien dice que es.</span><span class="sxs-lookup"><span data-stu-id="99372-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="99372-133">-Valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="99372-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="99372-134">-None: Sin protección.</span><span class="sxs-lookup"><span data-stu-id="99372-134">-   None: No protection.</span></span><br /><span data-ttu-id="99372-135">-Sign: Se firman los mensajes.</span><span class="sxs-lookup"><span data-stu-id="99372-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="99372-136">-EncryptAndSign: Los mensajes se cifrarán y firmarán.</span><span class="sxs-lookup"><span data-stu-id="99372-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="99372-137">El valor predeterminado es Sign.</span><span class="sxs-lookup"><span data-stu-id="99372-137">The default value is Sign.</span></span> <span data-ttu-id="99372-138">Este atributo es del tipo ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="99372-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="99372-139">: Especifica el algoritmo que se usará para calcular el resumen como parte de las firmas.</span><span class="sxs-lookup"><span data-stu-id="99372-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="99372-140">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="99372-140">Valid values include the following:</span></span><br /><span data-ttu-id="99372-141">-MD5</span><span class="sxs-lookup"><span data-stu-id="99372-141">-   MD5</span></span><br /><span data-ttu-id="99372-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="99372-142">-   SHA1</span></span><br /><span data-ttu-id="99372-143">-SHA256</span><span class="sxs-lookup"><span data-stu-id="99372-143">-   SHA256</span></span><br /><span data-ttu-id="99372-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="99372-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="99372-145">El valor predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="99372-145">The default value is SHA1.</span></span> <span data-ttu-id="99372-146">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="99372-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99372-147">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99372-147">Child Elements</span></span>  
 <span data-ttu-id="99372-148">Ninguna</span><span class="sxs-lookup"><span data-stu-id="99372-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99372-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99372-149">Parent Elements</span></span>  
  
|<span data-ttu-id="99372-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="99372-150">Element</span></span>|<span data-ttu-id="99372-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="99372-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99372-152">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="99372-152">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="99372-153">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="99372-153">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99372-154">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99372-154">Remarks</span></span>  
 <span data-ttu-id="99372-155">Este elemento encapsula la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="99372-155">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="99372-156">La configuración es la misma para la integración de Message Queuing y los transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="99372-156">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="99372-157">Le permite establecer el Modo de autenticación, Algoritmo de cifrado, Algoritmo hash seguro y Nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="99372-157">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99372-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="99372-158">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [<span data-ttu-id="99372-159">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="99372-159">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="99372-160">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="99372-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="99372-161">Enlaces</span><span class="sxs-lookup"><span data-stu-id="99372-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99372-162">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="99372-162">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="99372-163">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="99372-163">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="99372-164">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="99372-164">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

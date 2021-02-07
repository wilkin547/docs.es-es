---
description: 'Más información acerca de: <msmqTransportSecurity>'
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: d5a681c287749598c8c80470ea6d800f1687a80d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684170"
---
# \<msmqTransportSecurity>

<span data-ttu-id="3813d-102">Especifica la configuración de seguridad de transporte MSMQ para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="3813d-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="3813d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3813d-103">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3813d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3813d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3813d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3813d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3813d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="3813d-106">Attributes</span></span>  
  
|<span data-ttu-id="3813d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="3813d-107">Attribute</span></span>|<span data-ttu-id="3813d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3813d-108">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="3813d-109">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3813d-109">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="3813d-110">Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="3813d-110">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="3813d-111">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3813d-111">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3813d-112">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="3813d-112">-   None: No authentication.</span></span><br /><span data-ttu-id="3813d-113">-Windows: el mecanismo de autenticación usa Active Directory para obtener el certificado X. 509 para el SID asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="3813d-113">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="3813d-114">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="3813d-114">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="3813d-115">-Certificate: el canal obtiene el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="3813d-115">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="3813d-116">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="3813d-116">The default value is Windows.</span></span> <span data-ttu-id="3813d-117">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="3813d-117">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="3813d-118">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3813d-118">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="3813d-119">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3813d-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3813d-120">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="3813d-120">-   RC4Stream</span></span><br /><span data-ttu-id="3813d-121">-AES</span><span class="sxs-lookup"><span data-stu-id="3813d-121">-   AES</span></span><br /><br /> <span data-ttu-id="3813d-122">El valor predeterminado RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="3813d-122">The default value is RC4Stream.</span></span> <span data-ttu-id="3813d-123">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="3813d-123">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="3813d-124">Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3813d-124">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="3813d-125">El cifrado asegura la integridad del mensaje, mientras que EncryptAndSign garantiza la integridad del mensaje y el no rechazo; es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="3813d-125">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="3813d-126">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3813d-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3813d-127">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="3813d-127">-   None: No protection.</span></span><br /><span data-ttu-id="3813d-128">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="3813d-128">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="3813d-129">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="3813d-129">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="3813d-130">El valor predeterminado es Sign.</span><span class="sxs-lookup"><span data-stu-id="3813d-130">The default value is Sign.</span></span> <span data-ttu-id="3813d-131">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="3813d-131">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="3813d-132">Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas.</span><span class="sxs-lookup"><span data-stu-id="3813d-132">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="3813d-133">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3813d-133">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3813d-134">-MD5</span><span class="sxs-lookup"><span data-stu-id="3813d-134">-   MD5</span></span><br /><span data-ttu-id="3813d-135">-SHA1</span><span class="sxs-lookup"><span data-stu-id="3813d-135">-   SHA1</span></span><br /><span data-ttu-id="3813d-136">-SHA256</span><span class="sxs-lookup"><span data-stu-id="3813d-136">-   SHA256</span></span><br /><span data-ttu-id="3813d-137">-SHA512</span><span class="sxs-lookup"><span data-stu-id="3813d-137">-   SHA512</span></span><br /><br /> <span data-ttu-id="3813d-138">El valor predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="3813d-138">The default value is SHA1.</span></span> <span data-ttu-id="3813d-139">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="3813d-139">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="3813d-140">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="3813d-140">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3813d-141">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3813d-141">Child Elements</span></span>  

 <span data-ttu-id="3813d-142">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3813d-142">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3813d-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3813d-143">Parent Elements</span></span>  
  
|<span data-ttu-id="3813d-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="3813d-144">Element</span></span>|<span data-ttu-id="3813d-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="3813d-145">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="3813d-146">Especifica valores requeridos para la interacción con un remitente o receptor de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="3813d-146">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="3813d-147">Especifica las propiedades de comunicación de uso de colas de un servicio Windows Communication Foundation (WCF) que usa el protocolo MSMQ nativo.</span><span class="sxs-lookup"><span data-stu-id="3813d-147">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3813d-148">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3813d-148">Remarks</span></span>  

 <span data-ttu-id="3813d-149">Para obtener más información sobre la seguridad de transporte, vea [seguridad de transporte](../../../wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="3813d-149">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3813d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="3813d-150">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3813d-151">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="3813d-151">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="3813d-152">Transportes</span><span class="sxs-lookup"><span data-stu-id="3813d-152">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3813d-153">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="3813d-153">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3813d-154">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3813d-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3813d-155">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="3813d-155">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3813d-156">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3813d-156">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="3813d-157">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="3813d-157">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)

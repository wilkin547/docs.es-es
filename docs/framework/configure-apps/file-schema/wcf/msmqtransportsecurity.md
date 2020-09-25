---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 9d28f3f08e9c3984c055567df03f2839709a1522
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204650"
---
# \<msmqTransportSecurity>

<span data-ttu-id="b4855-101">Especifica la configuración de seguridad de transporte MSMQ para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b4855-101">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="b4855-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4855-102">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4855-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b4855-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b4855-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b4855-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4855-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="b4855-105">Attributes</span></span>  
  
|<span data-ttu-id="b4855-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="b4855-106">Attribute</span></span>|<span data-ttu-id="b4855-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4855-107">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="b4855-108">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b4855-108">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="b4855-109">Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="b4855-109">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="b4855-110">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4855-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4855-111">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="b4855-111">-   None: No authentication.</span></span><br /><span data-ttu-id="b4855-112">-Windows: el mecanismo de autenticación usa Active Directory para obtener el certificado X. 509 para el SID asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="b4855-112">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="b4855-113">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="b4855-113">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="b4855-114">-Certificate: el canal obtiene el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="b4855-114">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="b4855-115">El valor predeterminado es Windows.</span><span class="sxs-lookup"><span data-stu-id="b4855-115">The default value is Windows.</span></span> <span data-ttu-id="b4855-116">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="b4855-116">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="b4855-117">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b4855-117">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="b4855-118">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4855-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4855-119">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="b4855-119">-   RC4Stream</span></span><br /><span data-ttu-id="b4855-120">-AES</span><span class="sxs-lookup"><span data-stu-id="b4855-120">-   AES</span></span><br /><br /> <span data-ttu-id="b4855-121">El valor predeterminado RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="b4855-121">The default value is RC4Stream.</span></span> <span data-ttu-id="b4855-122">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="b4855-122">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="b4855-123">Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="b4855-123">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="b4855-124">El cifrado asegura la integridad del mensaje, mientras que EncryptAndSign garantiza la integridad del mensaje y el no rechazo; es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="b4855-124">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="b4855-125">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4855-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4855-126">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="b4855-126">-   None: No protection.</span></span><br /><span data-ttu-id="b4855-127">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="b4855-127">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="b4855-128">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="b4855-128">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="b4855-129">El valor predeterminado es Sign.</span><span class="sxs-lookup"><span data-stu-id="b4855-129">The default value is Sign.</span></span> <span data-ttu-id="b4855-130">Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="b4855-130">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="b4855-131">Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas.</span><span class="sxs-lookup"><span data-stu-id="b4855-131">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="b4855-132">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b4855-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4855-133">-MD5</span><span class="sxs-lookup"><span data-stu-id="b4855-133">-   MD5</span></span><br /><span data-ttu-id="b4855-134">-SHA1</span><span class="sxs-lookup"><span data-stu-id="b4855-134">-   SHA1</span></span><br /><span data-ttu-id="b4855-135">-SHA256</span><span class="sxs-lookup"><span data-stu-id="b4855-135">-   SHA256</span></span><br /><span data-ttu-id="b4855-136">-SHA512</span><span class="sxs-lookup"><span data-stu-id="b4855-136">-   SHA512</span></span><br /><br /> <span data-ttu-id="b4855-137">El valor predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="b4855-137">The default value is SHA1.</span></span> <span data-ttu-id="b4855-138">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="b4855-138">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="b4855-139">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="b4855-139">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4855-140">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b4855-140">Child Elements</span></span>  

 <span data-ttu-id="b4855-141">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b4855-141">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4855-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b4855-142">Parent Elements</span></span>  
  
|<span data-ttu-id="b4855-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4855-143">Element</span></span>|<span data-ttu-id="b4855-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4855-144">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="b4855-145">Especifica valores requeridos para la interacción con un remitente o receptor de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b4855-145">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="b4855-146">Especifica las propiedades de comunicación de uso de colas de un servicio Windows Communication Foundation (WCF) que usa el protocolo MSMQ nativo.</span><span class="sxs-lookup"><span data-stu-id="b4855-146">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4855-147">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4855-147">Remarks</span></span>  

 <span data-ttu-id="b4855-148">Para obtener más información sobre la seguridad de transporte, vea [seguridad de transporte](../../../wcf/feature-details/transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="b4855-148">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4855-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4855-149">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b4855-150">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="b4855-150">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="b4855-151">Transportes</span><span class="sxs-lookup"><span data-stu-id="b4855-151">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b4855-152">Elección del transporte</span><span class="sxs-lookup"><span data-stu-id="b4855-152">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b4855-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b4855-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b4855-154">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="b4855-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b4855-155">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="b4855-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="b4855-156">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="b4855-156">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)

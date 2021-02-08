---
description: 'Más información sobre: <transport> de <msmqIntegrationBinding>'
title: <transport> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: bcca714320f333a16d518248531efe8039ff566e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773529"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="cb6b0-103">\<transport> de \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="cb6b0-103">\<transport> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="cb6b0-104">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-104">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="cb6b0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb6b0-105">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb6b0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cb6b0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="cb6b0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb6b0-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb6b0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb6b0-108">Attributes</span></span>  
  
|<span data-ttu-id="cb6b0-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb6b0-109">Attribute</span></span>|<span data-ttu-id="cb6b0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb6b0-110">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="cb6b0-111">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="cb6b0-112">Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-112">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="cb6b0-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb6b0-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb6b0-114">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-114">-   None: No authentication.</span></span><br /><span data-ttu-id="cb6b0-115">-WindowsDomain: el mecanismo de autenticación usa Active Directory para obtener el certificado X. 509 para el SID asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-115">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="cb6b0-116">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-116">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="cb6b0-117">-Certificate: el canal obtiene el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-117">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="cb6b0-118">El valor predeterminado es WindowsDomain.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-118">The default value is WindowsDomain.</span></span> <span data-ttu-id="cb6b0-119">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="cb6b0-120">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-120">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="cb6b0-121">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb6b0-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cb6b0-122">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="cb6b0-122">-   RC4Stream</span></span><br /><span data-ttu-id="cb6b0-123">-AES</span><span class="sxs-lookup"><span data-stu-id="cb6b0-123">-   AES</span></span><br /><br /> <span data-ttu-id="cb6b0-124">El valor predeterminado RC4Stream.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-124">The default value is RC4Stream.</span></span> <span data-ttu-id="cb6b0-125">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-125">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="cb6b0-126">Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-126">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="cb6b0-127">El cifrado asegura la integridad del mensaje, mientras que EncryptAndSign garantiza la integridad del mensaje y el no rechazo; es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-127">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span><br /><br /> <span data-ttu-id="cb6b0-128">-Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb6b0-128">-   Valid values include the following:</span></span><br /><span data-ttu-id="cb6b0-129">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-129">-   None: No protection.</span></span><br /><span data-ttu-id="cb6b0-130">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-130">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="cb6b0-131">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-131">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="cb6b0-132">El valor predeterminado es Sign.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-132">The default value is Sign.</span></span> <span data-ttu-id="cb6b0-133">Este atributo es del tipo ProtectionLevel.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-133">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="cb6b0-134">: Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-134">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="cb6b0-135">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb6b0-135">Valid values include the following:</span></span><br /><span data-ttu-id="cb6b0-136">-MD5</span><span class="sxs-lookup"><span data-stu-id="cb6b0-136">-   MD5</span></span><br /><span data-ttu-id="cb6b0-137">-SHA1</span><span class="sxs-lookup"><span data-stu-id="cb6b0-137">-   SHA1</span></span><br /><span data-ttu-id="cb6b0-138">-SHA256</span><span class="sxs-lookup"><span data-stu-id="cb6b0-138">-   SHA256</span></span><br /><span data-ttu-id="cb6b0-139">-SHA512</span><span class="sxs-lookup"><span data-stu-id="cb6b0-139">-   SHA512</span></span><br /><br /> <span data-ttu-id="cb6b0-140">El valor predeterminado es SHA1.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-140">The default value is SHA1.</span></span> <span data-ttu-id="cb6b0-141">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-141">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="cb6b0-142">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-142">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb6b0-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cb6b0-143">Child Elements</span></span>  

 <span data-ttu-id="cb6b0-144">None</span><span class="sxs-lookup"><span data-stu-id="cb6b0-144">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb6b0-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb6b0-145">Parent Elements</span></span>  
  
|<span data-ttu-id="cb6b0-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb6b0-146">Element</span></span>|<span data-ttu-id="cb6b0-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb6b0-147">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="cb6b0-148">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-148">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb6b0-149">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb6b0-149">Remarks</span></span>  

 <span data-ttu-id="cb6b0-150">Este elemento encapsula la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-150">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="cb6b0-151">La configuración es la misma para la integración de Message Queuing y los transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-151">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="cb6b0-152">Le permite establecer el Modo de autenticación, Algoritmo de cifrado, Algoritmo hash seguro y Nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="cb6b0-152">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6b0-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb6b0-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="cb6b0-154">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cb6b0-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cb6b0-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="cb6b0-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cb6b0-156">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="cb6b0-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cb6b0-157">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cb6b0-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

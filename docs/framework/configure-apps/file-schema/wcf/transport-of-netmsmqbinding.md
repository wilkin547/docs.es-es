---
description: 'Más información sobre: <transport> de <netMsmqBinding>'
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 04768f259629277abd758d102f3873bb28f16514
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773503"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="08591-103">\<transport> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="08591-103">\<transport> of \<netMsmqBinding></span></span>

<span data-ttu-id="08591-104">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="08591-104">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="08591-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08591-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08591-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="08591-106">Attributes and Elements</span></span>  

 <span data-ttu-id="08591-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="08591-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08591-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="08591-108">Attributes</span></span>  
  
|<span data-ttu-id="08591-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="08591-109">Attribute</span></span>|<span data-ttu-id="08591-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="08591-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08591-111">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="08591-111">msmqAuthenticationMode</span></span>|<span data-ttu-id="08591-112">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="08591-112">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="08591-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="08591-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08591-114">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="08591-114">-   None: No authentication.</span></span><br /><span data-ttu-id="08591-115">-WindowsDomain: el mecanismo de autenticación usa Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="08591-115">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="08591-116">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="08591-116">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="08591-117">-Certificate: el canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="08591-117">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="08591-118">De manera predeterminada, es `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="08591-118">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="08591-119">Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`.</span><span class="sxs-lookup"><span data-stu-id="08591-119">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="08591-120">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="08591-120">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="08591-121">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="08591-121">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="08591-122">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="08591-122">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="08591-123">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="08591-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08591-124">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="08591-124">-   RC4Stream</span></span><br /><span data-ttu-id="08591-125">-AES</span><span class="sxs-lookup"><span data-stu-id="08591-125">-   AES</span></span><br /><span data-ttu-id="08591-126">-El valor predeterminado es `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="08591-126">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="08591-127">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="08591-127">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="08591-128">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="08591-128">msmqProtectionLevel</span></span>|<span data-ttu-id="08591-129">Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="08591-129">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="08591-130">El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio.</span><span class="sxs-lookup"><span data-stu-id="08591-130">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="08591-131">Es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="08591-131">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="08591-132">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="08591-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08591-133">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="08591-133">-   None: No protection.</span></span><br /><span data-ttu-id="08591-134">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="08591-134">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="08591-135">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="08591-135">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="08591-136">-El valor predeterminado es `Sign` .</span><span class="sxs-lookup"><span data-stu-id="08591-136">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="08591-137">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="08591-137">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="08591-138">Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje.</span><span class="sxs-lookup"><span data-stu-id="08591-138">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="08591-139">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="08591-139">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08591-140">-MD5</span><span class="sxs-lookup"><span data-stu-id="08591-140">-   MD5</span></span><br /><span data-ttu-id="08591-141">-SHA1</span><span class="sxs-lookup"><span data-stu-id="08591-141">-   SHA1</span></span><br /><span data-ttu-id="08591-142">-SHA256</span><span class="sxs-lookup"><span data-stu-id="08591-142">-   SHA256</span></span><br /><span data-ttu-id="08591-143">-SHA512</span><span class="sxs-lookup"><span data-stu-id="08591-143">-   SHA512</span></span><br /><br /> <span data-ttu-id="08591-144">De manera predeterminada, es `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="08591-144">The default is `SHA1`.</span></span> <span data-ttu-id="08591-145">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="08591-145">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="08591-146">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="08591-146">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08591-147">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="08591-147">Child Elements</span></span>  

 <span data-ttu-id="08591-148">None</span><span class="sxs-lookup"><span data-stu-id="08591-148">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08591-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="08591-149">Parent Elements</span></span>  
  
|<span data-ttu-id="08591-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="08591-150">Element</span></span>|<span data-ttu-id="08591-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="08591-151">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="08591-152">Define los valores de seguridad de transporte para transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="08591-152">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08591-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="08591-153">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="08591-154">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="08591-154">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="08591-155">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="08591-155">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="08591-156">Enlaces</span><span class="sxs-lookup"><span data-stu-id="08591-156">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="08591-157">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="08591-157">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="08591-158">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="08591-158">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

---
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152936"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="95c23-102">\<transport> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="95c23-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="95c23-103">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="95c23-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="95c23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95c23-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95c23-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95c23-105">Attributes and Elements</span></span>  
 <span data-ttu-id="95c23-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95c23-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95c23-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="95c23-107">Attributes</span></span>  
  
|<span data-ttu-id="95c23-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="95c23-108">Attribute</span></span>|<span data-ttu-id="95c23-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="95c23-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95c23-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="95c23-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="95c23-111">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c23-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="95c23-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95c23-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="95c23-113">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="95c23-113">-   None: No authentication.</span></span><br /><span data-ttu-id="95c23-114">-WindowsDomain: el mecanismo de autenticación usa Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c23-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="95c23-115">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="95c23-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="95c23-116">-Certificate: el canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="95c23-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="95c23-117">De manera predeterminada, es `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="95c23-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="95c23-118">Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`.</span><span class="sxs-lookup"><span data-stu-id="95c23-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="95c23-119">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="95c23-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="95c23-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="95c23-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="95c23-121">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="95c23-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="95c23-122">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95c23-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="95c23-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="95c23-123">-   RC4Stream</span></span><br /><span data-ttu-id="95c23-124">-AES</span><span class="sxs-lookup"><span data-stu-id="95c23-124">-   AES</span></span><br /><span data-ttu-id="95c23-125">-El valor predeterminado es `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="95c23-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="95c23-126">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="95c23-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="95c23-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="95c23-127">msmqProtectionLevel</span></span>|<span data-ttu-id="95c23-128">Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="95c23-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="95c23-129">El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio.</span><span class="sxs-lookup"><span data-stu-id="95c23-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="95c23-130">Es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="95c23-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="95c23-131">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95c23-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="95c23-132">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="95c23-132">-   None: No protection.</span></span><br /><span data-ttu-id="95c23-133">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="95c23-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="95c23-134">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="95c23-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="95c23-135">-El valor predeterminado es `Sign` .</span><span class="sxs-lookup"><span data-stu-id="95c23-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="95c23-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="95c23-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="95c23-137">Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje.</span><span class="sxs-lookup"><span data-stu-id="95c23-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="95c23-138">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95c23-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="95c23-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="95c23-139">-   MD5</span></span><br /><span data-ttu-id="95c23-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="95c23-140">-   SHA1</span></span><br /><span data-ttu-id="95c23-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="95c23-141">-   SHA256</span></span><br /><span data-ttu-id="95c23-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="95c23-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="95c23-143">De manera predeterminada, es `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="95c23-143">The default is `SHA1`.</span></span> <span data-ttu-id="95c23-144">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="95c23-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="95c23-145">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="95c23-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95c23-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95c23-146">Child Elements</span></span>  
 <span data-ttu-id="95c23-147">None</span><span class="sxs-lookup"><span data-stu-id="95c23-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95c23-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95c23-148">Parent Elements</span></span>  
  
|<span data-ttu-id="95c23-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="95c23-149">Element</span></span>|<span data-ttu-id="95c23-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="95c23-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="95c23-151">Define los valores de seguridad de transporte para transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="95c23-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95c23-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95c23-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="95c23-153">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="95c23-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="95c23-154">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="95c23-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="95c23-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="95c23-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="95c23-156">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="95c23-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="95c23-157">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="95c23-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

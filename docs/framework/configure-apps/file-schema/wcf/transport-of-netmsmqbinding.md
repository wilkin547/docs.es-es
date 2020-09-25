---
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 84a5437de851ecdb96d0463ec574186ba5f91d9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203883"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="126de-102">\<transport> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="126de-102">\<transport> of \<netMsmqBinding></span></span>

<span data-ttu-id="126de-103">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="126de-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="126de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="126de-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="126de-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="126de-105">Attributes and Elements</span></span>  

 <span data-ttu-id="126de-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="126de-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="126de-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="126de-107">Attributes</span></span>  
  
|<span data-ttu-id="126de-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="126de-108">Attribute</span></span>|<span data-ttu-id="126de-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="126de-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="126de-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="126de-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="126de-111">Especifica cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="126de-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="126de-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="126de-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="126de-113">-None: sin autenticación.</span><span class="sxs-lookup"><span data-stu-id="126de-113">-   None: No authentication.</span></span><br /><span data-ttu-id="126de-114">-WindowsDomain: el mecanismo de autenticación usa Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje.</span><span class="sxs-lookup"><span data-stu-id="126de-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="126de-115">Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.</span><span class="sxs-lookup"><span data-stu-id="126de-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="126de-116">-Certificate: el canal recupera el certificado del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="126de-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="126de-117">El valor predeterminado es `WindowsDomain`.</span><span class="sxs-lookup"><span data-stu-id="126de-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="126de-118">Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`.</span><span class="sxs-lookup"><span data-stu-id="126de-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="126de-119">Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.</span><span class="sxs-lookup"><span data-stu-id="126de-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="126de-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="126de-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="126de-121">Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="126de-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="126de-122">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="126de-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="126de-123">-RC4Stream</span><span class="sxs-lookup"><span data-stu-id="126de-123">-   RC4Stream</span></span><br /><span data-ttu-id="126de-124">-AES</span><span class="sxs-lookup"><span data-stu-id="126de-124">-   AES</span></span><br /><span data-ttu-id="126de-125">-El valor predeterminado es `RC4Stream` .</span><span class="sxs-lookup"><span data-stu-id="126de-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="126de-126">Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="126de-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="126de-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="126de-127">msmqProtectionLevel</span></span>|<span data-ttu-id="126de-128">Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="126de-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="126de-129">El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio.</span><span class="sxs-lookup"><span data-stu-id="126de-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="126de-130">Es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser.</span><span class="sxs-lookup"><span data-stu-id="126de-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="126de-131">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="126de-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="126de-132">-None: sin protección.</span><span class="sxs-lookup"><span data-stu-id="126de-132">-   None: No protection.</span></span><br /><span data-ttu-id="126de-133">-Sign: los mensajes se firman.</span><span class="sxs-lookup"><span data-stu-id="126de-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="126de-134">-EncryptAndSign: los mensajes se cifran y firman.</span><span class="sxs-lookup"><span data-stu-id="126de-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="126de-135">-El valor predeterminado es `Sign` .</span><span class="sxs-lookup"><span data-stu-id="126de-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="126de-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="126de-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="126de-137">Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje.</span><span class="sxs-lookup"><span data-stu-id="126de-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="126de-138">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="126de-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="126de-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="126de-139">-   MD5</span></span><br /><span data-ttu-id="126de-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="126de-140">-   SHA1</span></span><br /><span data-ttu-id="126de-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="126de-141">-   SHA256</span></span><br /><span data-ttu-id="126de-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="126de-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="126de-143">El valor predeterminado es `SHA1`.</span><span class="sxs-lookup"><span data-stu-id="126de-143">The default is `SHA1`.</span></span> <span data-ttu-id="126de-144">Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="126de-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="126de-145">Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="126de-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="126de-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="126de-146">Child Elements</span></span>  

 <span data-ttu-id="126de-147">None</span><span class="sxs-lookup"><span data-stu-id="126de-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="126de-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="126de-148">Parent Elements</span></span>  
  
|<span data-ttu-id="126de-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="126de-149">Element</span></span>|<span data-ttu-id="126de-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="126de-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="126de-151">Define los valores de seguridad de transporte para transportes en cola.</span><span class="sxs-lookup"><span data-stu-id="126de-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="126de-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="126de-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="126de-153">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="126de-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="126de-154">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="126de-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="126de-155">Enlaces</span><span class="sxs-lookup"><span data-stu-id="126de-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="126de-156">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="126de-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="126de-157">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="126de-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

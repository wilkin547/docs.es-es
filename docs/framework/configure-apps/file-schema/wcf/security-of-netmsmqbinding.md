---
title: Elemento &lt;security&gt; de &lt;netMsmqBinding&gt;
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 71f0c10c336a9682971bc774141cb0c3bd37c092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696391"
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="0f635-102">Elemento &lt;security&gt; de &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="0f635-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="0f635-103">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0f635-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="0f635-104">Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.</span><span class="sxs-lookup"><span data-stu-id="0f635-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="0f635-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0f635-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f635-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0f635-106">\<bindings></span></span>  
<span data-ttu-id="0f635-107">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="0f635-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="0f635-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="0f635-108">\<binding></span></span>  
<span data-ttu-id="0f635-109">\<security></span><span class="sxs-lookup"><span data-stu-id="0f635-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f635-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f635-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f635-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0f635-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f635-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0f635-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f635-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0f635-113">Attributes</span></span>  
  
|<span data-ttu-id="0f635-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0f635-114">Attribute</span></span>|<span data-ttu-id="0f635-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f635-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f635-116">modo</span><span class="sxs-lookup"><span data-stu-id="0f635-116">mode</span></span>|<span data-ttu-id="0f635-117">Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0f635-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="0f635-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0f635-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0f635-119">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="0f635-119">-   None: This disables security.</span></span><br /><span data-ttu-id="0f635-120">-Transporte: El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="0f635-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="0f635-121">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="0f635-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="0f635-122">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="0f635-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="0f635-123">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0f635-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="0f635-124">-Mensaje: Especifica la seguridad de la aplicación de extremo.</span><span class="sxs-lookup"><span data-stu-id="0f635-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="0f635-125">No se proporciona seguridad en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="0f635-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="0f635-126">Esto es similar a la seguridad proporcionada por otros enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="0f635-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="0f635-127">-Ambos: Ofrece seguridad en transporte y capa de mensajería de SOAP.</span><span class="sxs-lookup"><span data-stu-id="0f635-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="0f635-128">Se requiere la misma credencial en ambos niveles.</span><span class="sxs-lookup"><span data-stu-id="0f635-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="0f635-129">El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="0f635-129">The default value is Transport.</span></span> <span data-ttu-id="0f635-130">Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="0f635-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f635-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0f635-131">Child Elements</span></span>  
  
|<span data-ttu-id="0f635-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f635-132">Element</span></span>|<span data-ttu-id="0f635-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f635-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f635-134">\<message></span><span class="sxs-lookup"><span data-stu-id="0f635-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="0f635-135">Define la configuración de seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="0f635-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="0f635-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="0f635-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="0f635-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="0f635-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="0f635-138">Define la configuración de seguridad del transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0f635-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="0f635-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="0f635-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f635-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0f635-140">Parent Elements</span></span>  
  
|<span data-ttu-id="0f635-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f635-141">Element</span></span>|<span data-ttu-id="0f635-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f635-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f635-143">enlace</span><span class="sxs-lookup"><span data-stu-id="0f635-143">binding</span></span>|<span data-ttu-id="0f635-144">El elemento de enlace de la [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="0f635-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f635-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f635-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="0f635-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0f635-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0f635-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0f635-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0f635-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="0f635-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0f635-149">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="0f635-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0f635-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="0f635-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="0f635-151">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="0f635-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)

---
title: Elemento &lt;security&gt; de &lt;netMsmqBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 15ebbd1f0f139ef0d66ed802b990876735074485
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a><span data-ttu-id="3a63e-102">Elemento &lt;security&gt; de &lt;netMsmqBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="3a63e-102">&lt;security&gt; of &lt;netMsmqBinding&gt;</span></span>
<span data-ttu-id="3a63e-103">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3a63e-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="3a63e-104">Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.</span><span class="sxs-lookup"><span data-stu-id="3a63e-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
 <span data-ttu-id="3a63e-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3a63e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a63e-106">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="3a63e-106">\<bindings></span></span>  
<span data-ttu-id="3a63e-107">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="3a63e-107">\<netMsmqBinding></span></span>  
<span data-ttu-id="3a63e-108">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="3a63e-108">\<binding></span></span>  
<span data-ttu-id="3a63e-109">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="3a63e-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a63e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a63e-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a63e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a63e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3a63e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a63e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a63e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a63e-113">Attributes</span></span>  
  
|<span data-ttu-id="3a63e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3a63e-114">Attribute</span></span>|<span data-ttu-id="3a63e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a63e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a63e-116">modo</span><span class="sxs-lookup"><span data-stu-id="3a63e-116">mode</span></span>|<span data-ttu-id="3a63e-117">Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3a63e-117">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="3a63e-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a63e-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3a63e-119">-Ninguno: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="3a63e-119">-   None: This disables security.</span></span><br /><span data-ttu-id="3a63e-120">-Transport: Protección y autenticación proporcionadas por el transporte.</span><span class="sxs-lookup"><span data-stu-id="3a63e-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="3a63e-121">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="3a63e-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="3a63e-122">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="3a63e-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="3a63e-123">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3a63e-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="3a63e-124">-Message: Especifica la seguridad de la aplicación de extremo.</span><span class="sxs-lookup"><span data-stu-id="3a63e-124">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="3a63e-125">No se proporciona seguridad en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="3a63e-125">There is no security offered at the transport layer.</span></span> <span data-ttu-id="3a63e-126">Esto es similar a la seguridad proporcionada por otros enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="3a63e-126">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="3a63e-127">-Both: Proporciona seguridad en el transporte y capa de mensajería SOAP.</span><span class="sxs-lookup"><span data-stu-id="3a63e-127">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="3a63e-128">Se requiere la misma credencial en ambos niveles.</span><span class="sxs-lookup"><span data-stu-id="3a63e-128">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="3a63e-129">El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="3a63e-129">The default value is Transport.</span></span> <span data-ttu-id="3a63e-130">Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3a63e-130">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a63e-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a63e-131">Child Elements</span></span>  
  
|<span data-ttu-id="3a63e-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a63e-132">Element</span></span>|<span data-ttu-id="3a63e-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a63e-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a63e-134">\<mensaje ></span><span class="sxs-lookup"><span data-stu-id="3a63e-134">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|<span data-ttu-id="3a63e-135">Define la configuración de seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="3a63e-135">Defines the SOAP message security settings.</span></span> <span data-ttu-id="3a63e-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="3a63e-136">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="3a63e-137">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="3a63e-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|<span data-ttu-id="3a63e-138">Define la configuración de seguridad del transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="3a63e-138">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="3a63e-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3a63e-139">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a63e-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a63e-140">Parent Elements</span></span>  
  
|<span data-ttu-id="3a63e-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a63e-141">Element</span></span>|<span data-ttu-id="3a63e-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a63e-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a63e-143">enlace</span><span class="sxs-lookup"><span data-stu-id="3a63e-143">binding</span></span>|<span data-ttu-id="3a63e-144">El elemento de enlace de la [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3a63e-144">The binding element of the [\<netMsmqBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a63e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a63e-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [<span data-ttu-id="3a63e-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3a63e-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3a63e-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3a63e-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3a63e-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3a63e-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3a63e-149">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="3a63e-149">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3a63e-150">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="3a63e-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="3a63e-151">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="3a63e-151">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)

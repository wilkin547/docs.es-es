---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 8d79523db2a1567283b934abbd3de1adbbe6b0b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125793"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="8e73d-102">\<seguridad > de \<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="8e73d-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="8e73d-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8e73d-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="8e73d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e73d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e73d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8e73d-105">\<bindings></span></span>  
<span data-ttu-id="8e73d-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="8e73d-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="8e73d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8e73d-107">\<binding></span></span>  
<span data-ttu-id="8e73d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="8e73d-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e73d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e73d-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e73d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8e73d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8e73d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8e73d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e73d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8e73d-112">Attributes</span></span>  
  
|<span data-ttu-id="8e73d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e73d-113">Attribute</span></span>|<span data-ttu-id="8e73d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e73d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e73d-115">modo</span><span class="sxs-lookup"><span data-stu-id="8e73d-115">mode</span></span>|<span data-ttu-id="8e73d-116">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="8e73d-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="8e73d-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8e73d-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8e73d-118">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="8e73d-118">-   None: This disables security.</span></span><br /><span data-ttu-id="8e73d-119">-Transporte: El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="8e73d-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="8e73d-120">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="8e73d-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="8e73d-121">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="8e73d-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="8e73d-122">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8e73d-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="8e73d-123">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="8e73d-123">The default value is `Transport`.</span></span> <span data-ttu-id="8e73d-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8e73d-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e73d-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8e73d-125">Child Elements</span></span>  
  
|<span data-ttu-id="8e73d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e73d-126">Element</span></span>|<span data-ttu-id="8e73d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e73d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e73d-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="8e73d-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="8e73d-129">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="8e73d-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="8e73d-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8e73d-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e73d-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8e73d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8e73d-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="8e73d-132">Element</span></span>|<span data-ttu-id="8e73d-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e73d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e73d-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="8e73d-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8e73d-135">El elemento de enlace de la [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8e73d-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e73d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e73d-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="8e73d-137">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="8e73d-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="8e73d-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8e73d-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8e73d-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8e73d-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8e73d-140">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8e73d-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8e73d-141">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8e73d-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8e73d-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="8e73d-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="8e73d-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="8e73d-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)

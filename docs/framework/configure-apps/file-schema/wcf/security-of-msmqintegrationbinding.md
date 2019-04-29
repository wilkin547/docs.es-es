---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 8d79523db2a1567283b934abbd3de1adbbe6b0b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670539"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="891be-102">\<seguridad > de \<msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="891be-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="891be-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="891be-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="891be-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="891be-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="891be-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="891be-105">\<bindings></span></span>  
<span data-ttu-id="891be-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="891be-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="891be-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="891be-107">\<binding></span></span>  
<span data-ttu-id="891be-108">\<security></span><span class="sxs-lookup"><span data-stu-id="891be-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="891be-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="891be-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="891be-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="891be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="891be-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="891be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="891be-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="891be-112">Attributes</span></span>  
  
|<span data-ttu-id="891be-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="891be-113">Attribute</span></span>|<span data-ttu-id="891be-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="891be-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="891be-115">modo</span><span class="sxs-lookup"><span data-stu-id="891be-115">mode</span></span>|<span data-ttu-id="891be-116">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="891be-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="891be-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="891be-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="891be-118">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="891be-118">-   None: This disables security.</span></span><br /><span data-ttu-id="891be-119">-Transporte: El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="891be-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="891be-120">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="891be-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="891be-121">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="891be-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="891be-122">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="891be-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="891be-123">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="891be-123">The default value is `Transport`.</span></span> <span data-ttu-id="891be-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="891be-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="891be-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="891be-125">Child Elements</span></span>  
  
|<span data-ttu-id="891be-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="891be-126">Element</span></span>|<span data-ttu-id="891be-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="891be-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="891be-128">\<transport></span><span class="sxs-lookup"><span data-stu-id="891be-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="891be-129">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="891be-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="891be-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="891be-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="891be-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="891be-131">Parent Elements</span></span>  
  
|<span data-ttu-id="891be-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="891be-132">Element</span></span>|<span data-ttu-id="891be-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="891be-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="891be-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="891be-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="891be-135">El elemento de enlace de la [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="891be-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="891be-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="891be-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="891be-137">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="891be-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="891be-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="891be-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="891be-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="891be-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="891be-140">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="891be-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="891be-141">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="891be-141">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="891be-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="891be-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="891be-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="891be-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)

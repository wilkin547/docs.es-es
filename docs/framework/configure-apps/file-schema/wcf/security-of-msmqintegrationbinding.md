---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 5b74c95ef2933fcf7e8d49aed89d95acbd288b80
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936709"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="8a01a-102">\<> de seguridad \<de msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="8a01a-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="8a01a-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="8a01a-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="8a01a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8a01a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8a01a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8a01a-105">\<bindings></span></span>  
<span data-ttu-id="8a01a-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="8a01a-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="8a01a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a01a-107">\<binding></span></span>  
<span data-ttu-id="8a01a-108">\<> de seguridad</span><span class="sxs-lookup"><span data-stu-id="8a01a-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a01a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a01a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a01a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a01a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8a01a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a01a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a01a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a01a-112">Attributes</span></span>  
  
|<span data-ttu-id="8a01a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a01a-113">Attribute</span></span>|<span data-ttu-id="8a01a-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a01a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a01a-115">modo</span><span class="sxs-lookup"><span data-stu-id="8a01a-115">mode</span></span>|<span data-ttu-id="8a01a-116">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="8a01a-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="8a01a-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8a01a-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8a01a-118">Ninguna Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a01a-118">-   None: This disables security.</span></span><br /><span data-ttu-id="8a01a-119">Porta El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="8a01a-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="8a01a-120">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="8a01a-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="8a01a-121">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="8a01a-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="8a01a-122">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a01a-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="8a01a-123">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="8a01a-123">The default value is `Transport`.</span></span> <span data-ttu-id="8a01a-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="8a01a-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a01a-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a01a-125">Child Elements</span></span>  
  
|<span data-ttu-id="8a01a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a01a-126">Element</span></span>|<span data-ttu-id="8a01a-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a01a-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a01a-128">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="8a01a-128">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="8a01a-129">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="8a01a-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="8a01a-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="8a01a-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a01a-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a01a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8a01a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a01a-132">Element</span></span>|<span data-ttu-id="8a01a-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a01a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a01a-134">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a01a-134">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="8a01a-135">Elemento de enlace del [ \<> msmqIntegrationBinding](msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8a01a-135">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a01a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a01a-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="8a01a-137">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="8a01a-137">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="8a01a-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a01a-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8a01a-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8a01a-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8a01a-140">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8a01a-140">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="8a01a-141">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8a01a-141">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8a01a-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="8a01a-142">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="8a01a-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="8a01a-143">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)

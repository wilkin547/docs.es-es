---
title: Elemento &lt;security&gt; de &lt;msmqIntegrationBinding&gt;
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6419c2157281d00cf79de16d4f494fc52bcee598
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988080"
---
# <a name="ltsecuritygt-of-ltmsmqintegrationbindinggt"></a><span data-ttu-id="59f47-102">Elemento &lt;security&gt; de &lt;msmqIntegrationBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="59f47-102">&lt;security&gt; of &lt;msmqIntegrationBinding&gt;</span></span>
<span data-ttu-id="59f47-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="59f47-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
 <span data-ttu-id="59f47-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59f47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59f47-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="59f47-105">\<bindings></span></span>  
<span data-ttu-id="59f47-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="59f47-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="59f47-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="59f47-107">\<binding></span></span>  
<span data-ttu-id="59f47-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="59f47-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f47-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59f47-109">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59f47-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59f47-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59f47-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59f47-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59f47-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="59f47-112">Attributes</span></span>  
  
|<span data-ttu-id="59f47-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="59f47-113">Attribute</span></span>|<span data-ttu-id="59f47-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f47-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59f47-115">modo</span><span class="sxs-lookup"><span data-stu-id="59f47-115">mode</span></span>|<span data-ttu-id="59f47-116">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="59f47-116">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="59f47-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="59f47-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="59f47-118">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="59f47-118">-   None: This disables security.</span></span><br /><span data-ttu-id="59f47-119">-Transporte: Protección y autenticación proporcionadas por el transporte.</span><span class="sxs-lookup"><span data-stu-id="59f47-119">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="59f47-120">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="59f47-120">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="59f47-121">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="59f47-121">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="59f47-122">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="59f47-122">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="59f47-123">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="59f47-123">The default value is `Transport`.</span></span> <span data-ttu-id="59f47-124">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="59f47-124">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59f47-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59f47-125">Child Elements</span></span>  
  
|<span data-ttu-id="59f47-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="59f47-126">Element</span></span>|<span data-ttu-id="59f47-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f47-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59f47-128">\<transporte ></span><span class="sxs-lookup"><span data-stu-id="59f47-128">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|<span data-ttu-id="59f47-129">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="59f47-129">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="59f47-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="59f47-130">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59f47-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59f47-131">Parent Elements</span></span>  
  
|<span data-ttu-id="59f47-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="59f47-132">Element</span></span>|<span data-ttu-id="59f47-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="59f47-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59f47-134">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="59f47-134">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="59f47-135">El elemento de enlace de la [ \<msmqIntegrationBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="59f47-135">The binding element of the [\<msmqIntegrationBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59f47-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="59f47-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>  
 [<span data-ttu-id="59f47-137">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="59f47-137">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [<span data-ttu-id="59f47-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="59f47-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="59f47-139">Enlaces</span><span class="sxs-lookup"><span data-stu-id="59f47-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="59f47-140">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="59f47-140">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="59f47-141">Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="59f47-141">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="59f47-142">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="59f47-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="59f47-143">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="59f47-143">\<msmqIntegrationBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)

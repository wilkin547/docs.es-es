---
description: 'Más información sobre: <security> de <msmqIntegrationBinding>'
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 4ad4cb89599198661d764cfeb985609be027c0eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683208"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="089ce-103">\<security> de \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="089ce-103">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="089ce-104">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="089ce-104">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="089ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="089ce-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="089ce-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="089ce-106">Attributes and Elements</span></span>  

 <span data-ttu-id="089ce-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="089ce-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="089ce-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="089ce-108">Attributes</span></span>  
  
|<span data-ttu-id="089ce-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="089ce-109">Attribute</span></span>|<span data-ttu-id="089ce-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="089ce-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="089ce-111">mode</span><span class="sxs-lookup"><span data-stu-id="089ce-111">mode</span></span>|<span data-ttu-id="089ce-112">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="089ce-112">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="089ce-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="089ce-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="089ce-114">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="089ce-114">-   None: This disables security.</span></span><br /><span data-ttu-id="089ce-115">-Transport: el transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="089ce-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="089ce-116">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="089ce-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="089ce-117">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="089ce-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="089ce-118">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="089ce-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="089ce-119">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="089ce-119">The default value is `Transport`.</span></span> <span data-ttu-id="089ce-120">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="089ce-120">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="089ce-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="089ce-121">Child Elements</span></span>  
  
|<span data-ttu-id="089ce-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="089ce-122">Element</span></span>|<span data-ttu-id="089ce-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="089ce-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="089ce-124">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="089ce-124">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="089ce-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="089ce-125">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="089ce-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="089ce-126">Parent Elements</span></span>  
  
|<span data-ttu-id="089ce-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="089ce-127">Element</span></span>|<span data-ttu-id="089ce-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="089ce-128">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="089ce-129">Elemento de enlace de [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="089ce-129">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="089ce-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="089ce-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="089ce-131">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="089ce-131">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="089ce-132">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="089ce-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="089ce-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="089ce-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="089ce-134">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="089ce-134">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="089ce-135">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="089ce-135">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)

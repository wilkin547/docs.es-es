---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: be2f48f7d9c3be4ea0a5fe95436930b3f23c7551
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170069"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="9b5d1-102">\<security> de \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="9b5d1-102">\<security> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="9b5d1-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="9b5d1-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="9b5d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b5d1-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b5d1-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9b5d1-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9b5d1-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b5d1-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9b5d1-107">Attributes</span></span>  
  
|<span data-ttu-id="9b5d1-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="9b5d1-108">Attribute</span></span>|<span data-ttu-id="9b5d1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b5d1-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b5d1-110">mode</span><span class="sxs-lookup"><span data-stu-id="9b5d1-110">mode</span></span>|<span data-ttu-id="9b5d1-111">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="9b5d1-112">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b5d1-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9b5d1-113">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-113">-   None: This disables security.</span></span><br /><span data-ttu-id="9b5d1-114">-Transport: el transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="9b5d1-115">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="9b5d1-116">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="9b5d1-117">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="9b5d1-118">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-118">The default value is `Transport`.</span></span> <span data-ttu-id="9b5d1-119">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b5d1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9b5d1-120">Child Elements</span></span>  
  
|<span data-ttu-id="9b5d1-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b5d1-121">Element</span></span>|<span data-ttu-id="9b5d1-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b5d1-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="9b5d1-123">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="9b5d1-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9b5d1-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b5d1-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9b5d1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="9b5d1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="9b5d1-126">Element</span></span>|<span data-ttu-id="9b5d1-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b5d1-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="9b5d1-128">Elemento de enlace de [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="9b5d1-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b5d1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b5d1-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="9b5d1-130">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="9b5d1-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9b5d1-131">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9b5d1-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9b5d1-132">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9b5d1-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9b5d1-133">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9b5d1-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9b5d1-134">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9b5d1-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)

---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: e4f10ab994429c6cbb690caef38114b8340e6839
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399864"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="73d5a-102">\<> de seguridad \<de msmqIntegrationBinding ></span><span class="sxs-lookup"><span data-stu-id="73d5a-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="73d5a-103">Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="73d5a-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
<span data-ttu-id="73d5a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73d5a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73d5a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="73d5a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="73d5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="73d5a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="73d5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> msmqIntegrationBinding**](msmqintegrationbinding.md)</span><span class="sxs-lookup"><span data-stu-id="73d5a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)</span></span>\
<span data-ttu-id="73d5a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="73d5a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="73d5a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="73d5a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d5a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73d5a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73d5a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73d5a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73d5a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73d5a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73d5a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="73d5a-113">Attributes</span></span>  
  
|<span data-ttu-id="73d5a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="73d5a-114">Attribute</span></span>|<span data-ttu-id="73d5a-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73d5a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73d5a-116">modo</span><span class="sxs-lookup"><span data-stu-id="73d5a-116">mode</span></span>|<span data-ttu-id="73d5a-117">Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="73d5a-117">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="73d5a-118">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="73d5a-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="73d5a-119">Ninguna Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="73d5a-119">-   None: This disables security.</span></span><br /><span data-ttu-id="73d5a-120">Porta El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="73d5a-120">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="73d5a-121">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="73d5a-121">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="73d5a-122">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="73d5a-122">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="73d5a-123">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73d5a-123">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="73d5a-124">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="73d5a-124">The default value is `Transport`.</span></span> <span data-ttu-id="73d5a-125">Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="73d5a-125">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73d5a-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73d5a-126">Child Elements</span></span>  
  
|<span data-ttu-id="73d5a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="73d5a-127">Element</span></span>|<span data-ttu-id="73d5a-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73d5a-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73d5a-129">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="73d5a-129">\<transport></span></span>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="73d5a-130">Define la configuración de seguridad para el transporte de integración de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="73d5a-130">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="73d5a-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="73d5a-131">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73d5a-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73d5a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="73d5a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="73d5a-133">Element</span></span>|<span data-ttu-id="73d5a-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73d5a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73d5a-135">\<binding></span><span class="sxs-lookup"><span data-stu-id="73d5a-135">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="73d5a-136">Elemento de enlace del [ \<> msmqIntegrationBinding](msmqintegrationbinding.md).</span><span class="sxs-lookup"><span data-stu-id="73d5a-136">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73d5a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="73d5a-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="73d5a-138">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="73d5a-138">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="73d5a-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="73d5a-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="73d5a-140">Enlaces</span><span class="sxs-lookup"><span data-stu-id="73d5a-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="73d5a-141">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="73d5a-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="73d5a-142">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="73d5a-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="73d5a-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="73d5a-143">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="73d5a-144">\<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="73d5a-144">\<msmqIntegrationBinding></span></span>](msmqintegrationbinding.md)

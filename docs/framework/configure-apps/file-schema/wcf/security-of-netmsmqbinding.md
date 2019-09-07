---
title: <security> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: c780b157d0d566e24c6826c253401a51fbfab69d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399841"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="e4242-102">\<> de seguridad \<de netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="e4242-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="e4242-103">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4242-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="e4242-104">Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.</span><span class="sxs-lookup"><span data-stu-id="e4242-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
<span data-ttu-id="e4242-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e4242-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e4242-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e4242-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e4242-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e4242-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e4242-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e4242-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="e4242-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="e4242-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e4242-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de seguridad**</span><span class="sxs-lookup"><span data-stu-id="e4242-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4242-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4242-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4242-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4242-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e4242-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4242-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4242-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4242-114">Attributes</span></span>  
  
|<span data-ttu-id="e4242-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4242-115">Attribute</span></span>|<span data-ttu-id="e4242-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4242-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4242-117">modo</span><span class="sxs-lookup"><span data-stu-id="e4242-117">mode</span></span>|<span data-ttu-id="e4242-118">Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.</span><span class="sxs-lookup"><span data-stu-id="e4242-118">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="e4242-119">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e4242-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e4242-120">Ninguna Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4242-120">-   None: This disables security.</span></span><br /><span data-ttu-id="e4242-121">Porta El transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="e4242-121">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="e4242-122">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="e4242-122">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="e4242-123">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="e4242-123">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="e4242-124">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4242-124">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="e4242-125">Mensaje Especifica la seguridad de la aplicación final.</span><span class="sxs-lookup"><span data-stu-id="e4242-125">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="e4242-126">No se proporciona seguridad en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="e4242-126">There is no security offered at the transport layer.</span></span> <span data-ttu-id="e4242-127">Esto es similar a la seguridad proporcionada por otros enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="e4242-127">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="e4242-128">Ambos Ofrece seguridad tanto en el nivel de mensajería SOAP como en el de transporte.</span><span class="sxs-lookup"><span data-stu-id="e4242-128">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="e4242-129">Se requiere la misma credencial en ambos niveles.</span><span class="sxs-lookup"><span data-stu-id="e4242-129">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="e4242-130">El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="e4242-130">The default value is Transport.</span></span> <span data-ttu-id="e4242-131">Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e4242-131">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4242-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4242-132">Child Elements</span></span>  
  
|<span data-ttu-id="e4242-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4242-133">Element</span></span>|<span data-ttu-id="e4242-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4242-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4242-135">\<message></span><span class="sxs-lookup"><span data-stu-id="e4242-135">\<message></span></span>](message-of-netmsmqbinding.md)|<span data-ttu-id="e4242-136">Define la configuración de seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="e4242-136">Defines the SOAP message security settings.</span></span> <span data-ttu-id="e4242-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="e4242-137">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[<span data-ttu-id="e4242-138">\<> de transporte</span><span class="sxs-lookup"><span data-stu-id="e4242-138">\<transport></span></span>](transport-of-netmsmqbinding.md)|<span data-ttu-id="e4242-139">Define la configuración de seguridad del transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e4242-139">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="e4242-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e4242-140">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4242-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4242-141">Parent Elements</span></span>  
  
|<span data-ttu-id="e4242-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4242-142">Element</span></span>|<span data-ttu-id="e4242-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e4242-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4242-144">enlace</span><span class="sxs-lookup"><span data-stu-id="e4242-144">binding</span></span>|<span data-ttu-id="e4242-145">Elemento de enlace del [ \<> netMsmqBinding](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e4242-145">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4242-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4242-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="e4242-147">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e4242-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e4242-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e4242-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e4242-149">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="e4242-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e4242-150">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e4242-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e4242-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="e4242-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="e4242-152">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="e4242-152">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)

---
description: 'Más información sobre: <security> de <netMsmqBinding>'
title: <security> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 1b60d9e390e371555f4c3abf4988e79bb0f04fe8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786855"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="66aa6-103">\<security> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="66aa6-103">\<security> of \<netMsmqBinding></span></span>

<span data-ttu-id="66aa6-104">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="66aa6-104">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="66aa6-105">Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.</span><span class="sxs-lookup"><span data-stu-id="66aa6-105">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="66aa6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66aa6-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66aa6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66aa6-107">Attributes and Elements</span></span>  

 <span data-ttu-id="66aa6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="66aa6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66aa6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="66aa6-109">Attributes</span></span>  
  
|<span data-ttu-id="66aa6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="66aa6-110">Attribute</span></span>|<span data-ttu-id="66aa6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="66aa6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="66aa6-112">mode</span><span class="sxs-lookup"><span data-stu-id="66aa6-112">mode</span></span>|<span data-ttu-id="66aa6-113">Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.</span><span class="sxs-lookup"><span data-stu-id="66aa6-113">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="66aa6-114">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="66aa6-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="66aa6-115">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="66aa6-115">-   None: This disables security.</span></span><br /><span data-ttu-id="66aa6-116">-Transport: el transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="66aa6-116">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="66aa6-117">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="66aa6-117">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="66aa6-118">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="66aa6-118">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="66aa6-119">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="66aa6-119">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="66aa6-120">-Message: especifica la seguridad de la aplicación final.</span><span class="sxs-lookup"><span data-stu-id="66aa6-120">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="66aa6-121">No se proporciona seguridad en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="66aa6-121">There is no security offered at the transport layer.</span></span> <span data-ttu-id="66aa6-122">Esto es similar a la seguridad proporcionada por otros enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="66aa6-122">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="66aa6-123">-Both: ofrece seguridad tanto en el nivel de mensajería de transporte como de SOAP.</span><span class="sxs-lookup"><span data-stu-id="66aa6-123">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="66aa6-124">Se requiere la misma credencial en ambos niveles.</span><span class="sxs-lookup"><span data-stu-id="66aa6-124">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="66aa6-125">El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="66aa6-125">The default value is Transport.</span></span> <span data-ttu-id="66aa6-126">Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="66aa6-126">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66aa6-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66aa6-127">Child Elements</span></span>  
  
|<span data-ttu-id="66aa6-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="66aa6-128">Element</span></span>|<span data-ttu-id="66aa6-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="66aa6-129">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="66aa6-130">Define la configuración de seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="66aa6-130">Defines the SOAP message security settings.</span></span> <span data-ttu-id="66aa6-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="66aa6-131">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="66aa6-132">Define la configuración de seguridad del transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="66aa6-132">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="66aa6-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="66aa6-133">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66aa6-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66aa6-134">Parent Elements</span></span>  
  
|<span data-ttu-id="66aa6-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="66aa6-135">Element</span></span>|<span data-ttu-id="66aa6-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="66aa6-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66aa6-137">binding</span><span class="sxs-lookup"><span data-stu-id="66aa6-137">binding</span></span>|<span data-ttu-id="66aa6-138">El elemento de enlace del [\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="66aa6-138">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66aa6-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="66aa6-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="66aa6-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="66aa6-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="66aa6-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="66aa6-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66aa6-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="66aa6-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66aa6-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="66aa6-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="66aa6-144">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="66aa6-144">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)

---
title: <security> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 32b066fdf4d8edbbd36fdff7b14bdec87ddc970d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170082"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="461be-102">\<security> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="461be-102">\<security> of \<netMsmqBinding></span></span>

<span data-ttu-id="461be-103">Define la configuración de seguridad de un enlace MSMQ.</span><span class="sxs-lookup"><span data-stu-id="461be-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="461be-104">Especifica si se habilitó el transporte o la seguridad de SOAP y, si así fuera, qué modo de autenticación y niveles de protección están en uso.</span><span class="sxs-lookup"><span data-stu-id="461be-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="461be-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="461be-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="461be-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="461be-106">Attributes and Elements</span></span>  

 <span data-ttu-id="461be-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="461be-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="461be-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="461be-108">Attributes</span></span>  
  
|<span data-ttu-id="461be-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="461be-109">Attribute</span></span>|<span data-ttu-id="461be-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="461be-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="461be-111">mode</span><span class="sxs-lookup"><span data-stu-id="461be-111">mode</span></span>|<span data-ttu-id="461be-112">Especifica el tipo de seguridad que controla la integridad, la confidencialidad y la autenticación.</span><span class="sxs-lookup"><span data-stu-id="461be-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="461be-113">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="461be-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="461be-114">-None: Esto deshabilita la seguridad.</span><span class="sxs-lookup"><span data-stu-id="461be-114">-   None: This disables security.</span></span><br /><span data-ttu-id="461be-115">-Transport: el transporte ofrece protección y autenticación.</span><span class="sxs-lookup"><span data-stu-id="461be-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="461be-116">Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola.</span><span class="sxs-lookup"><span data-stu-id="461be-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="461be-117">No se proporciona seguridad entre la aplicación y el administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="461be-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="461be-118">Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="461be-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="461be-119">-Message: especifica la seguridad de la aplicación final.</span><span class="sxs-lookup"><span data-stu-id="461be-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="461be-120">No se proporciona seguridad en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="461be-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="461be-121">Esto es similar a la seguridad proporcionada por otros enlaces estándar.</span><span class="sxs-lookup"><span data-stu-id="461be-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="461be-122">-Both: ofrece seguridad tanto en el nivel de mensajería de transporte como de SOAP.</span><span class="sxs-lookup"><span data-stu-id="461be-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="461be-123">Se requiere la misma credencial en ambos niveles.</span><span class="sxs-lookup"><span data-stu-id="461be-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="461be-124">El valor predeterminado es Transport.</span><span class="sxs-lookup"><span data-stu-id="461be-124">The default value is Transport.</span></span> <span data-ttu-id="461be-125">Este atributo es del tipo <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="461be-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="461be-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="461be-126">Child Elements</span></span>  
  
|<span data-ttu-id="461be-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="461be-127">Element</span></span>|<span data-ttu-id="461be-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="461be-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="461be-129">Define la configuración de seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="461be-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="461be-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="461be-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="461be-131">Define la configuración de seguridad del transporte MSMQ.</span><span class="sxs-lookup"><span data-stu-id="461be-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="461be-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="461be-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="461be-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="461be-133">Parent Elements</span></span>  
  
|<span data-ttu-id="461be-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="461be-134">Element</span></span>|<span data-ttu-id="461be-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="461be-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="461be-136">binding</span><span class="sxs-lookup"><span data-stu-id="461be-136">binding</span></span>|<span data-ttu-id="461be-137">El elemento de enlace del [\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="461be-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="461be-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="461be-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="461be-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="461be-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="461be-140">Enlaces</span><span class="sxs-lookup"><span data-stu-id="461be-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="461be-141">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="461be-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="461be-142">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="461be-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="461be-143">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="461be-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)

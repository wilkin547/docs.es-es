---
title: <security>elemento de<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738724"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="81129-102">\<security>elemento de\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="81129-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="81129-103">Define la configuración de seguridad del [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="81129-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="81129-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81129-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81129-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="81129-105">Attributes and Elements</span></span>  
 <span data-ttu-id="81129-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="81129-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81129-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="81129-107">Attributes</span></span>  
  
|<span data-ttu-id="81129-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="81129-108">Attribute</span></span>|<span data-ttu-id="81129-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="81129-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="81129-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="81129-110">Optional.</span></span> <span data-ttu-id="81129-111">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="81129-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="81129-112">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="81129-112">The default value is `Message`.</span></span> <span data-ttu-id="81129-113">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="81129-113">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="81129-114">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="81129-114">mode Attribute</span></span>  
  
|<span data-ttu-id="81129-115">Value</span><span class="sxs-lookup"><span data-stu-id="81129-115">Value</span></span>|<span data-ttu-id="81129-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="81129-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81129-117">None</span><span class="sxs-lookup"><span data-stu-id="81129-117">None</span></span>|<span data-ttu-id="81129-118">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="81129-118">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="81129-119">Message</span><span class="sxs-lookup"><span data-stu-id="81129-119">Message</span></span>|<span data-ttu-id="81129-120">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="81129-120">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="81129-121">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="81129-121">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="81129-122">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="81129-122">The service must be configured with a certificate.</span></span> <span data-ttu-id="81129-123">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="81129-123">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="81129-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="81129-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="81129-125">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="81129-125">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="81129-126">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="81129-126">The service must be configured with a certificate.</span></span> <span data-ttu-id="81129-127">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="81129-127">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81129-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="81129-128">Child Elements</span></span>  
  
|<span data-ttu-id="81129-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="81129-129">Element</span></span>|<span data-ttu-id="81129-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="81129-130">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="81129-131">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="81129-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="81129-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="81129-132">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81129-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="81129-133">Parent Elements</span></span>  
  
|<span data-ttu-id="81129-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="81129-134">Element</span></span>|<span data-ttu-id="81129-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="81129-135">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="81129-136">Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="81129-136">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81129-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81129-137">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="81129-138">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="81129-138">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="81129-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="81129-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="81129-140">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="81129-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="81129-141">Enlaces</span><span class="sxs-lookup"><span data-stu-id="81129-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="81129-142">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="81129-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="81129-143">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="81129-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

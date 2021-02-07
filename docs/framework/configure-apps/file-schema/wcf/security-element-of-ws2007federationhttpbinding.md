---
description: 'Más información acerca <security> de: elemento de <ws2007FederationHttpBinding>'
title: <security> elemento de <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 0caa2c3791c0dc3c8db0d9ee27175a28e52f6baa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683299"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="38e8e-103">\<security> elemento de \<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="38e8e-103">\<security> element of \<ws2007FederationHttpBinding></span></span>

<span data-ttu-id="38e8e-104">Define la configuración de seguridad del [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="38e8e-104">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="38e8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38e8e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e8e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38e8e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="38e8e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38e8e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e8e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="38e8e-108">Attributes</span></span>  
  
|<span data-ttu-id="38e8e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="38e8e-109">Attribute</span></span>|<span data-ttu-id="38e8e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="38e8e-110">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="38e8e-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="38e8e-111">Optional.</span></span> <span data-ttu-id="38e8e-112">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="38e8e-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="38e8e-113">El valor predeterminado es `Message`.</span><span class="sxs-lookup"><span data-stu-id="38e8e-113">The default value is `Message`.</span></span> <span data-ttu-id="38e8e-114">Este atributo es del tipo <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="38e8e-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="38e8e-115">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="38e8e-115">mode Attribute</span></span>  
  
|<span data-ttu-id="38e8e-116">Value</span><span class="sxs-lookup"><span data-stu-id="38e8e-116">Value</span></span>|<span data-ttu-id="38e8e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="38e8e-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38e8e-118">None</span><span class="sxs-lookup"><span data-stu-id="38e8e-118">None</span></span>|<span data-ttu-id="38e8e-119">El mensaje SOAP no es seguro durante la transferencia.</span><span class="sxs-lookup"><span data-stu-id="38e8e-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="38e8e-120">Message</span><span class="sxs-lookup"><span data-stu-id="38e8e-120">Message</span></span>|<span data-ttu-id="38e8e-121">La integridad, confidencialidad, autenticación de servidor y autenticación del cliente se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="38e8e-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="38e8e-122">De forma predeterminada, el cuerpo se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="38e8e-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="38e8e-123">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="38e8e-123">The service must be configured with a certificate.</span></span> <span data-ttu-id="38e8e-124">La autenticación del cliente está basada en el token emitido al cliente por un servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38e8e-124">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="38e8e-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="38e8e-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="38e8e-126">HTTPS proporciona integridad, confidencialidad y autenticación del servidor.</span><span class="sxs-lookup"><span data-stu-id="38e8e-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="38e8e-127">El servicio se debe configurar con un certificado.</span><span class="sxs-lookup"><span data-stu-id="38e8e-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="38e8e-128">La autenticación del cliente se proporciona por medio de la seguridad del mensaje SOAP y está basada en el token emitido al cliente por un servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38e8e-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e8e-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38e8e-129">Child Elements</span></span>  
  
|<span data-ttu-id="38e8e-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="38e8e-130">Element</span></span>|<span data-ttu-id="38e8e-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="38e8e-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="38e8e-132">Define la configuración de seguridad del nivel del mensaje.</span><span class="sxs-lookup"><span data-stu-id="38e8e-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="38e8e-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="38e8e-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38e8e-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38e8e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="38e8e-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="38e8e-135">Element</span></span>|<span data-ttu-id="38e8e-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="38e8e-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="38e8e-137">Define todas las funciones de enlace de [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="38e8e-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38e8e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="38e8e-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="38e8e-139">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="38e8e-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="38e8e-140">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="38e8e-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="38e8e-141">Selección de tipos de credenciales</span><span class="sxs-lookup"><span data-stu-id="38e8e-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="38e8e-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="38e8e-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38e8e-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="38e8e-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="38e8e-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="38e8e-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

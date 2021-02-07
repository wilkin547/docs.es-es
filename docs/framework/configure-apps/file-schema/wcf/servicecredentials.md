---
description: 'Más información acerca de: <serviceCredentials>'
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: c6fd39226ca2235d8f8253a7d2f2e363522870e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682870"
---
# \<serviceCredentials>

<span data-ttu-id="5c17e-102">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="5c17e-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="5c17e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c17e-103">Syntax</span></span>  
  
```xml  
<serviceCredentials type="String">
  <clientCertificate>
  </clientCertificate>
  <issuedTokenAuthentication>
  </issuedTokenAuthentication>
  <peer>
  </peer>
  <secureConversationAuthentication>
  </secureConversationAuthentication>
  <serviceCertificate>
  </serviceCertificate>
  <userNameAuthentication>
  </userNameAuthentication>
  <windowsAuthentication>
  </windowsAuthentication>
</serviceCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c17e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c17e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5c17e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c17e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c17e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c17e-106">Attributes</span></span>  
  
|<span data-ttu-id="5c17e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c17e-107">Attribute</span></span>|<span data-ttu-id="5c17e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c17e-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5c17e-109">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="5c17e-109">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c17e-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c17e-110">Child Elements</span></span>  
  
|<span data-ttu-id="5c17e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c17e-111">Element</span></span>|<span data-ttu-id="5c17e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c17e-112">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="5c17e-113">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="5c17e-113">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="5c17e-114">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="5c17e-114">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="5c17e-115">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="5c17e-116">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="5c17e-116">Specifies the current issued token for this service.</span></span> <span data-ttu-id="5c17e-117">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-117">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="5c17e-118">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="5c17e-118">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="5c17e-119">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-119">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="5c17e-120">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="5c17e-120">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="5c17e-121">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-121">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="5c17e-122">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="5c17e-122">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="5c17e-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-123">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="5c17e-124">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5c17e-124">Specifies the settings for username password validation.</span></span> <span data-ttu-id="5c17e-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-125">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="5c17e-126">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="5c17e-126">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="5c17e-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5c17e-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c17e-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c17e-128">Parent Elements</span></span>  
  
|<span data-ttu-id="5c17e-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c17e-129">Element</span></span>|<span data-ttu-id="5c17e-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c17e-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5c17e-131">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5c17e-131">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c17e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c17e-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="5c17e-133">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="5c17e-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

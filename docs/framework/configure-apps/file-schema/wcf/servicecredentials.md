---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399642"
---
# \<serviceCredentials>
<span data-ttu-id="58bf0-101">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="58bf0-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="58bf0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58bf0-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58bf0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58bf0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="58bf0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58bf0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58bf0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="58bf0-105">Attributes</span></span>  
  
|<span data-ttu-id="58bf0-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="58bf0-106">Attribute</span></span>|<span data-ttu-id="58bf0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="58bf0-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="58bf0-108">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="58bf0-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58bf0-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58bf0-109">Child Elements</span></span>  
  
|<span data-ttu-id="58bf0-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="58bf0-110">Element</span></span>|<span data-ttu-id="58bf0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="58bf0-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="58bf0-112">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="58bf0-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="58bf0-113">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="58bf0-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="58bf0-114">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="58bf0-115">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="58bf0-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="58bf0-116">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="58bf0-117">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="58bf0-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="58bf0-118">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="58bf0-119">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="58bf0-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="58bf0-120">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="58bf0-121">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="58bf0-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="58bf0-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="58bf0-123">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="58bf0-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="58bf0-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="58bf0-125">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="58bf0-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="58bf0-126">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="58bf0-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58bf0-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58bf0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="58bf0-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="58bf0-128">Element</span></span>|<span data-ttu-id="58bf0-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="58bf0-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="58bf0-130">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="58bf0-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58bf0-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58bf0-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="58bf0-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="58bf0-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

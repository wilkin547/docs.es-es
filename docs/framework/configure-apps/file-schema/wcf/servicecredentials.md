---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 63368355027856118546bc70183b41864eddb0e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172884"
---
# \<serviceCredentials>

<span data-ttu-id="76439-101">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="76439-101">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="76439-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76439-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76439-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76439-103">Attributes and Elements</span></span>  

 <span data-ttu-id="76439-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76439-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76439-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="76439-105">Attributes</span></span>  
  
|<span data-ttu-id="76439-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="76439-106">Attribute</span></span>|<span data-ttu-id="76439-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76439-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="76439-108">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="76439-108">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76439-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76439-109">Child Elements</span></span>  
  
|<span data-ttu-id="76439-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="76439-110">Element</span></span>|<span data-ttu-id="76439-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="76439-111">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="76439-112">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="76439-112">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="76439-113">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="76439-113">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="76439-114">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-114">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="76439-115">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="76439-115">Specifies the current issued token for this service.</span></span> <span data-ttu-id="76439-116">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-116">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="76439-117">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="76439-117">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="76439-118">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-118">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<secureConversationAuthentication>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="76439-119">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="76439-119">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="76439-120">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-120">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="76439-121">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="76439-121">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="76439-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-122">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[\<userNameAuthentication>](usernameauthentication.md)|<span data-ttu-id="76439-123">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="76439-123">Specifies the settings for username password validation.</span></span> <span data-ttu-id="76439-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-124">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[\<windowsAuthentication>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="76439-125">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="76439-125">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="76439-126">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="76439-126">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76439-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76439-127">Parent Elements</span></span>  
  
|<span data-ttu-id="76439-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="76439-128">Element</span></span>|<span data-ttu-id="76439-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="76439-129">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="76439-130">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="76439-130">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76439-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76439-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="76439-132">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="76439-132">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

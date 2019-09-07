---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 90a34a4a52b4c7a2e67d733fecba132818cac4fc
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399642"
---
# <a name="servicecredentials"></a><span data-ttu-id="e1b4d-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="e1b4d-101">\<serviceCredentials></span></span>
<span data-ttu-id="e1b4d-102">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
<span data-ttu-id="e1b4d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e1b4d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e1b4d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e1b4d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e1b4d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e1b4d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e1b4d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e1b4d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e1b4d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e1b4d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e1b4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de serviceCredentials**</span><span class="sxs-lookup"><span data-stu-id="e1b4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1b4d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1b4d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1b4d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1b4d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e1b4d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1b4d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1b4d-112">Attributes</span></span>  
  
|<span data-ttu-id="e1b4d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1b4d-113">Attribute</span></span>|<span data-ttu-id="e1b4d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e1b4d-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e1b4d-115">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1b4d-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1b4d-116">Child Elements</span></span>  
  
|<span data-ttu-id="e1b4d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1b4d-117">Element</span></span>|<span data-ttu-id="e1b4d-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e1b4d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1b4d-119">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="e1b4d-119">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="e1b4d-120">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="e1b4d-121">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="e1b4d-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="e1b4d-123">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="e1b4d-124">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="e1b4d-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-126">\<peer></span><span class="sxs-lookup"><span data-stu-id="e1b4d-126">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="e1b4d-127">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="e1b4d-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-129">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="e1b4d-129">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="e1b4d-130">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="e1b4d-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e1b4d-132">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="e1b4d-133">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="e1b4d-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-135">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="e1b4d-135">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="e1b4d-136">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="e1b4d-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="e1b4d-138">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="e1b4d-138">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="e1b4d-139">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="e1b4d-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1b4d-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1b4d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="e1b4d-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1b4d-142">Element</span></span>|<span data-ttu-id="e1b4d-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e1b4d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1b4d-144">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e1b4d-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e1b4d-145">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e1b4d-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1b4d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1b4d-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="e1b4d-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1b4d-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: 54ac4f0aa31a4311976449d545880d825c06337d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256477"
---
# <a name="servicecredentials"></a><span data-ttu-id="65d1d-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="65d1d-101">\<serviceCredentials></span></span>
<span data-ttu-id="65d1d-102">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="65d1d-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="65d1d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="65d1d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="65d1d-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="65d1d-104">\<behaviors></span></span>  
<span data-ttu-id="65d1d-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="65d1d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="65d1d-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="65d1d-106">\<behavior></span></span>  
<span data-ttu-id="65d1d-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="65d1d-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d1d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65d1d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65d1d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65d1d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="65d1d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65d1d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65d1d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="65d1d-111">Attributes</span></span>  
  
|<span data-ttu-id="65d1d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="65d1d-112">Attribute</span></span>|<span data-ttu-id="65d1d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="65d1d-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="65d1d-114">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="65d1d-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65d1d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65d1d-115">Child Elements</span></span>  
  
|<span data-ttu-id="65d1d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="65d1d-116">Element</span></span>|<span data-ttu-id="65d1d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="65d1d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65d1d-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="65d1d-118">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="65d1d-119">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="65d1d-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="65d1d-120">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="65d1d-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="65d1d-121">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="65d1d-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="65d1d-122">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="65d1d-123">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="65d1d-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="65d1d-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="65d1d-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="65d1d-125">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="65d1d-126">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="65d1d-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="65d1d-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="65d1d-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="65d1d-128">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="65d1d-129">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="65d1d-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="65d1d-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="65d1d-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="65d1d-131">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="65d1d-132">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="65d1d-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="65d1d-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="65d1d-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="65d1d-134">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="65d1d-135">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="65d1d-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="65d1d-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="65d1d-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="65d1d-137">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="65d1d-138">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="65d1d-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="65d1d-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="65d1d-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65d1d-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65d1d-140">Parent Elements</span></span>  
  
|<span data-ttu-id="65d1d-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="65d1d-141">Element</span></span>|<span data-ttu-id="65d1d-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="65d1d-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65d1d-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="65d1d-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="65d1d-144">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="65d1d-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65d1d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="65d1d-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="65d1d-146">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="65d1d-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

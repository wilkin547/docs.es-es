---
title: '&lt;ServiceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b9e32509a5e182301455eaf0e602a03c51fbc23a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150778"
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="0ff34-102">&lt;ServiceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="0ff34-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="0ff34-103">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff34-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="0ff34-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0ff34-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ff34-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="0ff34-105">\<behaviors></span></span>  
<span data-ttu-id="0ff34-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0ff34-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0ff34-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="0ff34-107">\<behavior></span></span>  
<span data-ttu-id="0ff34-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="0ff34-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ff34-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ff34-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ff34-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ff34-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0ff34-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ff34-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ff34-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ff34-112">Attributes</span></span>  
  
|<span data-ttu-id="0ff34-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="0ff34-113">Attribute</span></span>|<span data-ttu-id="0ff34-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ff34-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="0ff34-115">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="0ff34-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ff34-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ff34-116">Child Elements</span></span>  
  
|<span data-ttu-id="0ff34-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ff34-117">Element</span></span>|<span data-ttu-id="0ff34-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ff34-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ff34-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="0ff34-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="0ff34-120">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="0ff34-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="0ff34-121">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="0ff34-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="0ff34-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="0ff34-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0ff34-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="0ff34-124">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="0ff34-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="0ff34-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="0ff34-126">\<elemento del mismo nivel ></span><span class="sxs-lookup"><span data-stu-id="0ff34-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="0ff34-127">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="0ff34-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="0ff34-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="0ff34-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0ff34-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="0ff34-130">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="0ff34-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="0ff34-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="0ff34-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="0ff34-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="0ff34-133">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="0ff34-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="0ff34-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="0ff34-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0ff34-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="0ff34-136">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="0ff34-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="0ff34-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="0ff34-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="0ff34-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="0ff34-139">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="0ff34-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="0ff34-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0ff34-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ff34-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ff34-141">Parent Elements</span></span>  
  
|<span data-ttu-id="0ff34-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ff34-142">Element</span></span>|<span data-ttu-id="0ff34-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ff34-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ff34-144">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="0ff34-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0ff34-145">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="0ff34-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ff34-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ff34-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="0ff34-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="0ff34-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

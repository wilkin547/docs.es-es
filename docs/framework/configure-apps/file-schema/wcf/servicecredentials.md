---
title: '&lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00567c32b800bb98386e15b2ba822ccc9623d72b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicecredentialsgt"></a><span data-ttu-id="3e10d-102">&lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="3e10d-102">&lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="3e10d-103">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="3e10d-103">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="3e10d-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3e10d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3e10d-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3e10d-105">\<behaviors></span></span>  
<span data-ttu-id="3e10d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3e10d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3e10d-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3e10d-107">\<behavior></span></span>  
<span data-ttu-id="3e10d-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="3e10d-108">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e10d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e10d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e10d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e10d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3e10d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3e10d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e10d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e10d-112">Attributes</span></span>  
  
|<span data-ttu-id="3e10d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e10d-113">Attribute</span></span>|<span data-ttu-id="3e10d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e10d-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="3e10d-115">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="3e10d-115">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e10d-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e10d-116">Child Elements</span></span>  
  
|<span data-ttu-id="3e10d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e10d-117">Element</span></span>|<span data-ttu-id="3e10d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e10d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e10d-119">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="3e10d-119">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="3e10d-120">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="3e10d-120">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="3e10d-121">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="3e10d-121">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="3e10d-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="3e10d-123">\<issuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3e10d-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="3e10d-124">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="3e10d-124">Specifies the current issued token for this service.</span></span> <span data-ttu-id="3e10d-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-125">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="3e10d-126">\<punto ></span><span class="sxs-lookup"><span data-stu-id="3e10d-126">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="3e10d-127">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="3e10d-127">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="3e10d-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-128">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="3e10d-129">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3e10d-129">\<secureConversationAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="3e10d-130">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="3e10d-130">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="3e10d-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-131">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="3e10d-132">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3e10d-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|<span data-ttu-id="3e10d-133">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="3e10d-133">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="3e10d-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-134">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="3e10d-135">\<userNameAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3e10d-135">\<userNameAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)|<span data-ttu-id="3e10d-136">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="3e10d-136">Specifies the settings for username password validation.</span></span> <span data-ttu-id="3e10d-137">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-137">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="3e10d-138">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="3e10d-138">\<windowsAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="3e10d-139">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="3e10d-139">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="3e10d-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="3e10d-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e10d-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e10d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3e10d-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e10d-142">Element</span></span>|<span data-ttu-id="3e10d-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e10d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e10d-144">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3e10d-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3e10d-145">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3e10d-145">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e10d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e10d-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 [<span data-ttu-id="3e10d-147">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="3e10d-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)

---
title: <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 96db336c-4f7a-4193-81a5-910b8ffd804f
ms.openlocfilehash: b5d257b3082717ba94b9a4517ed5ccd4bd325c06
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936294"
---
# <a name="servicecredentials"></a><span data-ttu-id="5f38c-101">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="5f38c-101">\<serviceCredentials></span></span>
<span data-ttu-id="5f38c-102">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="5f38c-102">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>  
  
 <span data-ttu-id="5f38c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5f38c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5f38c-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5f38c-104">\<behaviors></span></span>  
<span data-ttu-id="5f38c-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5f38c-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5f38c-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5f38c-106">\<behavior></span></span>  
<span data-ttu-id="5f38c-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="5f38c-107">\<serviceCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f38c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f38c-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f38c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f38c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5f38c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f38c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f38c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f38c-111">Attributes</span></span>  
  
|<span data-ttu-id="5f38c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5f38c-112">Attribute</span></span>|<span data-ttu-id="5f38c-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5f38c-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5f38c-114">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="5f38c-114">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f38c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f38c-115">Child Elements</span></span>  
  
|<span data-ttu-id="5f38c-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f38c-116">Element</span></span>|<span data-ttu-id="5f38c-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5f38c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f38c-118">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="5f38c-118">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)|<span data-ttu-id="5f38c-119">Especifica el certificado que se va a usar cuando el certificado de cliente está disponible fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="5f38c-119">Specifies the certificate to be used when the client certificate is available out-of-band.</span></span> <span data-ttu-id="5f38c-120">Este elemento también especifica los valores de validación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="5f38c-120">This element also specifies client certificate validation settings.</span></span> <span data-ttu-id="5f38c-121">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-121">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="5f38c-122">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="5f38c-122">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="5f38c-123">Especifica el token emitido actualmente para este servicio.</span><span class="sxs-lookup"><span data-stu-id="5f38c-123">Specifies the current issued token for this service.</span></span> <span data-ttu-id="5f38c-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-124">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>.</span></span>|  
|[<span data-ttu-id="5f38c-125">\<peer></span><span class="sxs-lookup"><span data-stu-id="5f38c-125">\<peer></span></span>](peer-of-servicecredentials.md)|<span data-ttu-id="5f38c-126">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="5f38c-126">Specifies the current credentials for a peer node.</span></span> <span data-ttu-id="5f38c-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-127">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="5f38c-128">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="5f38c-128">\<secureConversationAuthentication></span></span>](secureconversationauthentication-of-servicecredential.md)|<span data-ttu-id="5f38c-129">Especifica las credenciales actuales para una conversación segura.</span><span class="sxs-lookup"><span data-stu-id="5f38c-129">Specifies the current credentials for a secure conversation.</span></span> <span data-ttu-id="5f38c-130">Este elemento es del tipo <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-130">This element is of type <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>.</span></span>|  
|[<span data-ttu-id="5f38c-131">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="5f38c-131">\<serviceCertificate></span></span>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="5f38c-132">Especifica un certificado utilizado por un servicio para identificarse.</span><span class="sxs-lookup"><span data-stu-id="5f38c-132">Specifies a certificate used by a service to identify itself.</span></span> <span data-ttu-id="5f38c-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-133">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>.</span></span>|  
|[<span data-ttu-id="5f38c-134">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="5f38c-134">\<userNameAuthentication></span></span>](usernameauthentication.md)|<span data-ttu-id="5f38c-135">Especifica la configuración para la validación del nombre de usuario y de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="5f38c-135">Specifies the settings for username password validation.</span></span> <span data-ttu-id="5f38c-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-136">This element is of type <xref:System.ServiceModel.Configuration.UserNameServiceElement>.</span></span>|  
|[<span data-ttu-id="5f38c-137">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="5f38c-137">\<windowsAuthentication></span></span>](windowsauthentication-of-servicecredentials.md)|<span data-ttu-id="5f38c-138">Especifica la configuración para la validación de credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="5f38c-138">Specifies the settings for Windows credential validation.</span></span> <span data-ttu-id="5f38c-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="5f38c-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsServiceElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f38c-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f38c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="5f38c-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f38c-141">Element</span></span>|<span data-ttu-id="5f38c-142">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5f38c-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f38c-143">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5f38c-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5f38c-144">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5f38c-144">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f38c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f38c-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- [<span data-ttu-id="5f38c-146">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="5f38c-146">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)

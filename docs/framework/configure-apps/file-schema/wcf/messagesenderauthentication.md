---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 428dbdc65a4f66e5632e4ded7d7ded0d10b7c9d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagesenderauthenticationgt"></a><span data-ttu-id="8fe91-102">&lt;messageSenderAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="8fe91-102">&lt;messageSenderAuthentication&gt;</span></span>
<span data-ttu-id="8fe91-103">Especifica los valores de autenticación para el certificado del mismo nivel utilizado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8fe91-103">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
 <span data-ttu-id="8fe91-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8fe91-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8fe91-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="8fe91-105">\<behaviors></span></span>  
<span data-ttu-id="8fe91-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8fe91-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8fe91-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8fe91-107">\<behavior></span></span>  
<span data-ttu-id="8fe91-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="8fe91-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8fe91-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="8fe91-109">\<peer></span></span>  
<span data-ttu-id="8fe91-110">\<messageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="8fe91-110">\<messageSenderAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe91-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fe91-111">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fe91-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8fe91-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8fe91-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8fe91-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fe91-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="8fe91-114">Attributes</span></span>  
  
|<span data-ttu-id="8fe91-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="8fe91-115">Attribute</span></span>|<span data-ttu-id="8fe91-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fe91-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="8fe91-117">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="8fe91-117">Optional enumeration.</span></span> <span data-ttu-id="8fe91-118">Especifica uno de los cinco modos usados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="8fe91-118">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="8fe91-119">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="8fe91-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="8fe91-120">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="8fe91-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="8fe91-121">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="8fe91-121">Optional string.</span></span> <span data-ttu-id="8fe91-122">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="8fe91-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="8fe91-123">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="8fe91-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="8fe91-124">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="8fe91-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="8fe91-125"> proporciona un validador de certificado predeterminado del mismo nivel que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fe91-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="8fe91-126">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="8fe91-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="8fe91-127">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="8fe91-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="8fe91-128">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="8fe91-128">Optional enumeration.</span></span> <span data-ttu-id="8fe91-129">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="8fe91-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="8fe91-130">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="8fe91-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="8fe91-131">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="8fe91-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="8fe91-132">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="8fe91-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="8fe91-133">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="8fe91-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="8fe91-134">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="8fe91-134">Optional enumeration.</span></span> <span data-ttu-id="8fe91-135">Especifica la ubicación del almacén fiable donde el sistema de seguridad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="8fe91-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="8fe91-136">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="8fe91-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fe91-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8fe91-137">Child Elements</span></span>  
 <span data-ttu-id="8fe91-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8fe91-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fe91-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8fe91-139">Parent Elements</span></span>  
  
|<span data-ttu-id="8fe91-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="8fe91-140">Element</span></span>|<span data-ttu-id="8fe91-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fe91-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fe91-142">\<punto ></span><span class="sxs-lookup"><span data-stu-id="8fe91-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="8fe91-143">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="8fe91-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fe91-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fe91-144">Remarks</span></span>  
 <span data-ttu-id="8fe91-145">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8fe91-145">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="8fe91-146">Para los canales de salida, cada mensaje se firma utilizando el certificado proporcionado por [ \<certificado >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span><span class="sxs-lookup"><span data-stu-id="8fe91-146">For output channels, each message is signed using the certificate provided by [\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).</span></span> <span data-ttu-id="8fe91-147">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="8fe91-147">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="8fe91-148">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="8fe91-148">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe91-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fe91-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [<span data-ttu-id="8fe91-150">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="8fe91-150">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="8fe91-151">Redes de punto a punto</span><span class="sxs-lookup"><span data-stu-id="8fe91-151">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="8fe91-152">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="8fe91-152">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="8fe91-153">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="8fe91-153">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="8fe91-154">Proteger las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="8fe91-154">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)

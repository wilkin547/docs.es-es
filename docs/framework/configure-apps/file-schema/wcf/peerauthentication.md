---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a900a1f3fc2e07cffe04833cc3c7d3ccd063e24a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeerauthenticationgt"></a><span data-ttu-id="1c09c-102">&lt;peerAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="1c09c-102">&lt;peerAuthentication&gt;</span></span>
<span data-ttu-id="1c09c-103">Especifica los valores de autenticación para un certificado del mismo nivel usado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1c09c-103">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
 <span data-ttu-id="1c09c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1c09c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c09c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1c09c-105">\<behaviors></span></span>  
<span data-ttu-id="1c09c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1c09c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1c09c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1c09c-107">\<behavior></span></span>  
<span data-ttu-id="1c09c-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1c09c-108">\<serviceCredentials></span></span>  
<span data-ttu-id="1c09c-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="1c09c-109">\<peer></span></span>  
<span data-ttu-id="1c09c-110">\<peerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="1c09c-110">\<peerAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c09c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c09c-111">Syntax</span></span>  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c09c-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c09c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1c09c-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1c09c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c09c-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c09c-114">Attributes</span></span>  
  
|<span data-ttu-id="1c09c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="1c09c-115">Attribute</span></span>|<span data-ttu-id="1c09c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c09c-116">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="1c09c-117">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="1c09c-117">Optional enumeration.</span></span> <span data-ttu-id="1c09c-118">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="1c09c-118">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="1c09c-119">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="1c09c-119">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="1c09c-120">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="1c09c-120">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="1c09c-121">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="1c09c-121">Optional string.</span></span> <span data-ttu-id="1c09c-122">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c09c-122">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="1c09c-123">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="1c09c-123">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="1c09c-124">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="1c09c-124">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="1c09c-125"> proporciona un validador de certificado predeterminado del mismo nivel que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="1c09c-125"> provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="1c09c-126">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="1c09c-126">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="1c09c-127">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="1c09c-127">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="1c09c-128">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="1c09c-128">Optional enumeration.</span></span> <span data-ttu-id="1c09c-129">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="1c09c-129">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="1c09c-130">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="1c09c-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="1c09c-131">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="1c09c-131">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="1c09c-132">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1c09c-132">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="1c09c-133">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="1c09c-133">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="1c09c-134">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="1c09c-134">Optional enumeration.</span></span> <span data-ttu-id="1c09c-135">Especifica la ubicación del almacén fiable donde el sistema de seguridad [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1c09c-135">Specifies the trusted store location where the peer certificate is validated by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] security system.</span></span> <span data-ttu-id="1c09c-136">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="1c09c-136">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c09c-137">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c09c-137">Child Elements</span></span>  
 <span data-ttu-id="1c09c-138">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c09c-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c09c-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c09c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="1c09c-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c09c-140">Element</span></span>|<span data-ttu-id="1c09c-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c09c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c09c-142">\<peer></span><span class="sxs-lookup"><span data-stu-id="1c09c-142">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="1c09c-143">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="1c09c-143">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c09c-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c09c-144">Remarks</span></span>  
 <span data-ttu-id="1c09c-145">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="1c09c-145">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="1c09c-146">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="1c09c-146">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="1c09c-147">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="1c09c-147">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="1c09c-148">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="1c09c-148">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="1c09c-149">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="1c09c-149">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c09c-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c09c-150">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [<span data-ttu-id="1c09c-151">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="1c09c-151">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="1c09c-152">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="1c09c-152">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="1c09c-153">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="1c09c-153">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="1c09c-154">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="1c09c-154">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="1c09c-155">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="1c09c-155">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)

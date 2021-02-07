---
description: 'Más información acerca de: <peerAuthentication>'
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: b640b4aac296c40fadcc5f4070ba58e5f92fd265
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683663"
---
# \<peerAuthentication>

<span data-ttu-id="50d58-102">Especifica los valores de autenticación para un certificado del mismo nivel usado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="50d58-102">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="50d58-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50d58-103">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50d58-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50d58-104">Attributes and Elements</span></span>  

 <span data-ttu-id="50d58-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50d58-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50d58-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="50d58-106">Attributes</span></span>  
  
|<span data-ttu-id="50d58-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="50d58-107">Attribute</span></span>|<span data-ttu-id="50d58-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="50d58-108">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="50d58-109">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="50d58-109">Optional enumeration.</span></span> <span data-ttu-id="50d58-110">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="50d58-110">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="50d58-111">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="50d58-111">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="50d58-112">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="50d58-112">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="50d58-113">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="50d58-113">Optional string.</span></span> <span data-ttu-id="50d58-114">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="50d58-114">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="50d58-115">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="50d58-115">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="50d58-116">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="50d58-116">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="50d58-117">Windows Communication Foundation (WCF) proporciona un validador de certificado del mismo nivel predeterminado que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="50d58-117">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="50d58-118">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="50d58-118">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="50d58-119">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="50d58-119">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="50d58-120">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="50d58-120">Optional enumeration.</span></span> <span data-ttu-id="50d58-121">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="50d58-121">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="50d58-122">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="50d58-122">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="50d58-123">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="50d58-123">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="50d58-124">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="50d58-124">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="50d58-125">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="50d58-125">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="50d58-126">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="50d58-126">Optional enumeration.</span></span> <span data-ttu-id="50d58-127">Especifica la ubicación del almacén de confianza donde el sistema de seguridad de WCF valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="50d58-127">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="50d58-128">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="50d58-128">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50d58-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50d58-129">Child Elements</span></span>  

 <span data-ttu-id="50d58-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="50d58-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50d58-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50d58-131">Parent Elements</span></span>  
  
|<span data-ttu-id="50d58-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="50d58-132">Element</span></span>|<span data-ttu-id="50d58-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="50d58-133">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="50d58-134">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="50d58-134">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50d58-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="50d58-135">Remarks</span></span>  

 <span data-ttu-id="50d58-136">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="50d58-136">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="50d58-137">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="50d58-137">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="50d58-138">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="50d58-138">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="50d58-139">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="50d58-139">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="50d58-140">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="50d58-140">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d58-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d58-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="50d58-142">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="50d58-142">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="50d58-143">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="50d58-143">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="50d58-144">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="50d58-144">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="50d58-145">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="50d58-145">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="50d58-146">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="50d58-146">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

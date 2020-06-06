---
title: <peerAuthentication>
ms.date: 03/30/2017
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
ms.openlocfilehash: 118159617a7f4c27ecc5e8fe077c28cfefac8537
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397612"
---
# \<peerAuthentication>
<span data-ttu-id="98ec3-101">Especifica los valores de autenticación para un certificado del mismo nivel usado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="98ec3-101">Specifies authentication settings for a peer certificate used by a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="98ec3-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98ec3-102">Syntax</span></span>  
  
```xml  
<peerAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                    certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                    revocationMode="NoCheck/Online/Offline"
                    trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98ec3-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="98ec3-103">Attributes and Elements</span></span>  
 <span data-ttu-id="98ec3-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="98ec3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98ec3-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="98ec3-105">Attributes</span></span>  
  
|<span data-ttu-id="98ec3-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="98ec3-106">Attribute</span></span>|<span data-ttu-id="98ec3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ec3-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="98ec3-108">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="98ec3-108">Optional enumeration.</span></span> <span data-ttu-id="98ec3-109">Especifica uno de los tres modos utilizados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="98ec3-109">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="98ec3-110">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="98ec3-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="98ec3-111">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="98ec3-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="98ec3-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="98ec3-112">Optional string.</span></span> <span data-ttu-id="98ec3-113">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="98ec3-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="98ec3-114">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="98ec3-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="98ec3-115">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="98ec3-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="98ec3-116">Windows Communication Foundation (WCF) proporciona un validador de certificado del mismo nivel predeterminado que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="98ec3-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="98ec3-117">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="98ec3-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="98ec3-118">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="98ec3-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="98ec3-119">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="98ec3-119">Optional enumeration.</span></span> <span data-ttu-id="98ec3-120">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="98ec3-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="98ec3-121">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="98ec3-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="98ec3-122">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="98ec3-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="98ec3-123">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="98ec3-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="98ec3-124">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="98ec3-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="98ec3-125">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="98ec3-125">Optional enumeration.</span></span> <span data-ttu-id="98ec3-126">Especifica la ubicación del almacén de confianza donde el sistema de seguridad de WCF valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="98ec3-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="98ec3-127">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="98ec3-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98ec3-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="98ec3-128">Child Elements</span></span>  
 <span data-ttu-id="98ec3-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="98ec3-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98ec3-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="98ec3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="98ec3-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="98ec3-131">Element</span></span>|<span data-ttu-id="98ec3-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="98ec3-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="98ec3-133">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="98ec3-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98ec3-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98ec3-134">Remarks</span></span>  
 <span data-ttu-id="98ec3-135">El elemento `<authentication>` corresponde a la clase <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="98ec3-135">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> class.</span></span> <span data-ttu-id="98ec3-136">Este elemento especifica un validador, que se invoca durante la autenticación entre vecinos en la malla.</span><span class="sxs-lookup"><span data-stu-id="98ec3-136">This element specifies a validator, which is invoked during neighbor-to-neighbor authentication in the mesh.</span></span> <span data-ttu-id="98ec3-137">Cuando un nuevo par intenta establecer una conexión de vecino, pasa su propia credencial al par que responde.</span><span class="sxs-lookup"><span data-stu-id="98ec3-137">When a new peer tries to establish a neighbor connection, it passes its own credential to the responding peer.</span></span> <span data-ttu-id="98ec3-138">El validador del contestador se invoca para comprobar la credencial de la parte remota.</span><span class="sxs-lookup"><span data-stu-id="98ec3-138">The validator of the responder is invoked to verify the credential of the remote party.</span></span> <span data-ttu-id="98ec3-139">Cuando una conexión del mismo nivel se establece en la malla, se autentican ambos pares mutuamente, lo que significa que se invocan los validadores en ambos extremos.</span><span class="sxs-lookup"><span data-stu-id="98ec3-139">Whenever a peer connection is established in the mesh, both peers are mutually authenticated, meaning validators on both ends are invoked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ec3-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98ec3-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [<span data-ttu-id="98ec3-141">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="98ec3-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="98ec3-142">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="98ec3-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="98ec3-143">[Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="98ec3-143">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="98ec3-144">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="98ec3-144">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="98ec3-145">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="98ec3-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

---
description: 'Más información acerca de: <messageSenderAuthentication>'
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: e98388eafce24b0f19647364b6bbec94ee6ba135
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749328"
---
# \<messageSenderAuthentication>

<span data-ttu-id="ede64-102">Especifica los valores de autenticación para el certificado del mismo nivel utilizado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ede64-102">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="ede64-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ede64-103">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ede64-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ede64-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ede64-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ede64-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ede64-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ede64-106">Attributes</span></span>  
  
|<span data-ttu-id="ede64-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ede64-107">Attribute</span></span>|<span data-ttu-id="ede64-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ede64-108">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="ede64-109">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="ede64-109">Optional enumeration.</span></span> <span data-ttu-id="ede64-110">Especifica uno de los cinco modos usados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="ede64-110">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="ede64-111">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="ede64-111">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="ede64-112">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="ede64-112">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="ede64-113">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="ede64-113">Optional string.</span></span> <span data-ttu-id="ede64-114">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ede64-114">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="ede64-115">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="ede64-115">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="ede64-116">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="ede64-116">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="ede64-117">Windows Communication Foundation (WCF) proporciona un validador de certificado del mismo nivel predeterminado que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="ede64-117">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="ede64-118">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="ede64-118">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="ede64-119">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="ede64-119">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="ede64-120">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="ede64-120">Optional enumeration.</span></span> <span data-ttu-id="ede64-121">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="ede64-121">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="ede64-122">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="ede64-122">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="ede64-123">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="ede64-123">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="ede64-124">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="ede64-124">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="ede64-125">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="ede64-125">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="ede64-126">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="ede64-126">Optional enumeration.</span></span> <span data-ttu-id="ede64-127">Especifica la ubicación del almacén de confianza donde el sistema de seguridad de WCF valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ede64-127">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="ede64-128">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="ede64-128">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ede64-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ede64-129">Child Elements</span></span>  

 <span data-ttu-id="ede64-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ede64-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ede64-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ede64-131">Parent Elements</span></span>  
  
|<span data-ttu-id="ede64-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ede64-132">Element</span></span>|<span data-ttu-id="ede64-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="ede64-133">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="ede64-134">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="ede64-134">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ede64-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ede64-135">Remarks</span></span>  

 <span data-ttu-id="ede64-136">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ede64-136">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="ede64-137">En el caso de los canales de salida, cada mensaje se firma con el certificado proporcionado por [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="ede64-137">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="ede64-138">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="ede64-138">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="ede64-139">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="ede64-139">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede64-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ede64-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="ede64-141">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="ede64-141">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ede64-142">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="ede64-142">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="ede64-143">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ede64-143">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="ede64-144">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ede64-144">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="ede64-145">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="ede64-145">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

---
title: <messageSenderAuthentication>
ms.date: 03/30/2017
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
ms.openlocfilehash: c6183a8d27d56c7199b815ccb31b06f983a51b33
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398399"
---
# \<messageSenderAuthentication>
<span data-ttu-id="f75ad-101">Especifica los valores de autenticación para el certificado del mismo nivel utilizado por el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f75ad-101">Specifies authentication settings for peer certificate used by a message sender.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="f75ad-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f75ad-102">Syntax</span></span>  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f75ad-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f75ad-103">Attributes and Elements</span></span>  
 <span data-ttu-id="f75ad-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f75ad-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f75ad-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="f75ad-105">Attributes</span></span>  
  
|<span data-ttu-id="f75ad-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="f75ad-106">Attribute</span></span>|<span data-ttu-id="f75ad-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f75ad-107">Description</span></span>|  
|---------------|-----------------|  
|`certificateValidationMode`|<span data-ttu-id="f75ad-108">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f75ad-108">Optional enumeration.</span></span> <span data-ttu-id="f75ad-109">Especifica uno de los cinco modos usados para validar las credenciales.</span><span class="sxs-lookup"><span data-stu-id="f75ad-109">Specifies one of five modes used to validate credentials.</span></span> <span data-ttu-id="f75ad-110">Este atributo es del tipo <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="f75ad-110">This attribute is of type <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="f75ad-111">Si se establece en `Custom`, también debe proporcionarse un `customCertificateValidator`.</span><span class="sxs-lookup"><span data-stu-id="f75ad-111">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="f75ad-112">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="f75ad-112">Optional string.</span></span> <span data-ttu-id="f75ad-113">Especifica un tipo y ensamblado utilizados para validar un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f75ad-113">Specifies a type and assembly used to validate a custom type.</span></span> <span data-ttu-id="f75ad-114">Se debe establecer este atributo cuando `certificateValidationMode` está establecido en `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f75ad-114">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span> <span data-ttu-id="f75ad-115">Este atributo es del tipo <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="f75ad-115">This attribute is of type <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f75ad-116">Windows Communication Foundation (WCF) proporciona un validador de certificado del mismo nivel predeterminado que comprueba el certificado del mismo nivel con el almacén de personas de confianza.</span><span class="sxs-lookup"><span data-stu-id="f75ad-116">Windows Communication Foundation (WCF) provides a default peer certificate validator that verifies the peer certificate against the trusted people store.</span></span> <span data-ttu-id="f75ad-117">También comprueba las cadenas de certificados hasta una raíz válida.</span><span class="sxs-lookup"><span data-stu-id="f75ad-117">It also verifies that the certificate chains up to a valid root.</span></span> <span data-ttu-id="f75ad-118">Puede implementar un validador personalizado para especificar un comportamiento diferente y usar este atributo para señalar al validador personalizado.</span><span class="sxs-lookup"><span data-stu-id="f75ad-118">You can implement a custom validator to specify a different behavior and use this attribute to point to the custom validator.</span></span>|  
|`revocationMode`|<span data-ttu-id="f75ad-119">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f75ad-119">Optional enumeration.</span></span> <span data-ttu-id="f75ad-120">Especifica el modo de revocación de certificados.</span><span class="sxs-lookup"><span data-stu-id="f75ad-120">Specifies the certificate revocation mode.</span></span> <span data-ttu-id="f75ad-121">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="f75ad-121">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span> <span data-ttu-id="f75ad-122">El sistema busca en la lista de certificados revocados y comprueba que el certificado del mismo nivel no se ha revocado.</span><span class="sxs-lookup"><span data-stu-id="f75ad-122">The system verifies that the peer certificate has not been revoked by looking it up in the revoked certificate list.</span></span> <span data-ttu-id="f75ad-123">Esta comprobación se puede realizar tanto en línea como con una lista de revocaciones almacenada en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="f75ad-123">This check can be performed either by checking online or against a cached revocation list.</span></span> <span data-ttu-id="f75ad-124">La comprobación de la revocación se puede desactivar estableciendo esta atributo en NoCheck.</span><span class="sxs-lookup"><span data-stu-id="f75ad-124">Revocation checking can be turned off by setting this attribute to NoCheck.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="f75ad-125">Enumeración opcional.</span><span class="sxs-lookup"><span data-stu-id="f75ad-125">Optional enumeration.</span></span> <span data-ttu-id="f75ad-126">Especifica la ubicación del almacén de confianza donde el sistema de seguridad de WCF valida el certificado del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f75ad-126">Specifies the trusted store location where the peer certificate is validated by the WCF security system.</span></span> <span data-ttu-id="f75ad-127">Este atributo es del tipo <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="f75ad-127">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f75ad-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f75ad-128">Child Elements</span></span>  
 <span data-ttu-id="f75ad-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f75ad-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f75ad-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f75ad-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f75ad-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="f75ad-131">Element</span></span>|<span data-ttu-id="f75ad-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="f75ad-132">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="f75ad-133">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="f75ad-133">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f75ad-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f75ad-134">Remarks</span></span>  
 <span data-ttu-id="f75ad-135">Se debe configurar este elemento si se elige la autenticación de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f75ad-135">This element must be configured if message authentication is chosen.</span></span> <span data-ttu-id="f75ad-136">En el caso de los canales de salida, cada mensaje se firma con el certificado proporcionado por [\<certificate>](certificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="f75ad-136">For output channels, each message is signed using the certificate provided by [\<certificate>](certificate-element.md).</span></span> <span data-ttu-id="f75ad-137">Todos los mensajes, antes de ser entregados a la aplicación, se comprueban con la credencial de mensaje utilizando el validador especificado por el atributo `customCertificateValidatorType` de este elemento.</span><span class="sxs-lookup"><span data-stu-id="f75ad-137">All messages, before delivered to the application, are checked against the message credential using the validator specified by the `customCertificateValidatorType` attribute of this element.</span></span> <span data-ttu-id="f75ad-138">El validador puede aceptar o rechazar la credencial.</span><span class="sxs-lookup"><span data-stu-id="f75ad-138">The validator can either accept or reject the credential.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75ad-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f75ad-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- [<span data-ttu-id="f75ad-140">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="f75ad-140">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f75ad-141">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="f75ad-141">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f75ad-142">[Autenticación del mensaje del canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f75ad-142">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f75ad-143">[Autenticación personalizada de canal del mismo nivel](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f75ad-143">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f75ad-144">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="f75ad-144">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)

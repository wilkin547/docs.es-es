---
description: 'Más información sobre: <certificate> de <peer>'
title: <certificate> de <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: e48a96a3f1fa486b19289584ae0c059eb5b7048d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639060"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="23ae4-103">\<certificate> de \<peer></span><span class="sxs-lookup"><span data-stu-id="23ae4-103">\<certificate> of \<peer></span></span>

<span data-ttu-id="23ae4-104">Especifica un certificado usado por un igual.</span><span class="sxs-lookup"><span data-stu-id="23ae4-104">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="23ae4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23ae4-105">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23ae4-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="23ae4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="23ae4-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="23ae4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23ae4-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="23ae4-108">Attributes</span></span>  
  
|<span data-ttu-id="23ae4-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="23ae4-109">Attribute</span></span>|<span data-ttu-id="23ae4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="23ae4-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="23ae4-111">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="23ae4-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="23ae4-112">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="23ae4-112">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="23ae4-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="23ae4-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="23ae4-114">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="23ae4-114">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="23ae4-115">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="23ae4-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23ae4-116">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="23ae4-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="23ae4-117">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="23ae4-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="23ae4-118">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="23ae4-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="23ae4-119">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="23ae4-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="23ae4-120">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="23ae4-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23ae4-121">-AddressBook: almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="23ae4-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="23ae4-122">-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="23ae4-122">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="23ae4-123">-CertificateAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.</span><span class="sxs-lookup"><span data-stu-id="23ae4-123">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="23ae4-124">-No permitido: almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="23ae4-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="23ae4-125">-Mi: almacén de certificados para Certificados personales.</span><span class="sxs-lookup"><span data-stu-id="23ae4-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="23ae4-126">-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="23ae4-126">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="23ae4-127">-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="23ae4-127">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="23ae4-128">-TrustedPublisher: almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="23ae4-128">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="23ae4-129">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="23ae4-129">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="23ae4-130">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="23ae4-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="23ae4-131">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="23ae4-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="23ae4-132">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="23ae4-132">-   FindByThumbPrint</span></span><br /><span data-ttu-id="23ae4-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="23ae4-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="23ae4-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="23ae4-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="23ae4-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="23ae4-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="23ae4-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="23ae4-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="23ae4-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="23ae4-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="23ae4-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="23ae4-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="23ae4-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="23ae4-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="23ae4-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="23ae4-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="23ae4-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="23ae4-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="23ae4-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="23ae4-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="23ae4-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="23ae4-143">-   FindByExtension</span></span><br /><span data-ttu-id="23ae4-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="23ae4-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="23ae4-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="23ae4-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="23ae4-146">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="23ae4-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="23ae4-147">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="23ae4-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23ae4-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="23ae4-148">Child Elements</span></span>  

 <span data-ttu-id="23ae4-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="23ae4-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23ae4-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="23ae4-150">Parent Elements</span></span>  
  
|<span data-ttu-id="23ae4-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="23ae4-151">Element</span></span>|<span data-ttu-id="23ae4-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="23ae4-152">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="23ae4-153">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="23ae4-153">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23ae4-154">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23ae4-154">Remarks</span></span>  

 <span data-ttu-id="23ae4-155">Este elemento de configuración contiene una instancia de `X509Certificate2` que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="23ae4-155">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="23ae4-156">Para obtener más información sobre la programación punto a punto, vea [redes punto a punto](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="23ae4-156">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23ae4-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="23ae4-157">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="23ae4-158">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="23ae4-158">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="23ae4-159">Conexión de redes punto a punto</span><span class="sxs-lookup"><span data-stu-id="23ae4-159">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="23ae4-160">[Autenticación del mensaje del canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="23ae4-160">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="23ae4-161">[Autenticación personalizada de canal del mismo nivel](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="23ae4-161">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="23ae4-162">Protección de las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="23ae4-162">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="23ae4-163">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="23ae4-163">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

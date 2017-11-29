---
title: '&lt;certificate&gt; de &lt;peer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bf53ec9538834fc6fdb098bff4f78ef1c726ef5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="c5836-102">&lt;certificate&gt; de &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="c5836-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="c5836-103">Especifica un certificado usado por un igual.</span><span class="sxs-lookup"><span data-stu-id="c5836-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="c5836-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c5836-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c5836-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c5836-105">\<behaviors></span></span>  
<span data-ttu-id="c5836-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c5836-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c5836-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c5836-107">\<behavior></span></span>  
<span data-ttu-id="c5836-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="c5836-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c5836-109">\<punto ></span><span class="sxs-lookup"><span data-stu-id="c5836-109">\<peer></span></span>  
<span data-ttu-id="c5836-110">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="c5836-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5836-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5836-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5836-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c5836-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5836-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c5836-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5836-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c5836-114">Attributes</span></span>  
  
|<span data-ttu-id="c5836-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c5836-115">Attribute</span></span>|<span data-ttu-id="c5836-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5836-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="c5836-117">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="c5836-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="c5836-118">El tipo contenido en este atributo debe satisfacer los requisitos del `x509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="c5836-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="c5836-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="c5836-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="c5836-120">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del igual.</span><span class="sxs-lookup"><span data-stu-id="c5836-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="c5836-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5836-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c5836-122">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="c5836-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="c5836-123">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="c5836-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="c5836-124">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c5836-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="c5836-125">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="c5836-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="c5836-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5836-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c5836-127">-AddressBook: Almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="c5836-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="c5836-128">-AuthRoot: Almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="c5836-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="c5836-129">-CertificateAuthority: Almacén de certificados intermedios para entidades de certificación (CA).</span><span class="sxs-lookup"><span data-stu-id="c5836-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="c5836-130">-Disallowed: Almacén de certificados para certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="c5836-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="c5836-131">-My: Almacén de certificados para los certificados personales.</span><span class="sxs-lookup"><span data-stu-id="c5836-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="c5836-132">-Root: Almacén de certificados para entidades de certificación raíz de confianza (CA).</span><span class="sxs-lookup"><span data-stu-id="c5836-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="c5836-133">-TrustedPeople: Almacén de certificados para las personas de confianza directa y recursos.</span><span class="sxs-lookup"><span data-stu-id="c5836-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="c5836-134">-TrustedPublisher: Almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="c5836-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="c5836-135">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="c5836-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="c5836-136">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c5836-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="c5836-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5836-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c5836-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="c5836-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="c5836-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="c5836-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="c5836-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="c5836-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="c5836-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="c5836-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="c5836-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="c5836-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="c5836-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="c5836-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="c5836-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="c5836-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="c5836-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="c5836-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="c5836-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="c5836-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="c5836-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="c5836-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="c5836-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="c5836-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="c5836-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="c5836-149">-   FindByExtension</span></span><br /><span data-ttu-id="c5836-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="c5836-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="c5836-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="c5836-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="c5836-152">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del `X509FindType` especificado.</span><span class="sxs-lookup"><span data-stu-id="c5836-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="c5836-153">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="c5836-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5836-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c5836-154">Child Elements</span></span>  
 <span data-ttu-id="c5836-155">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c5836-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5836-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c5836-156">Parent Elements</span></span>  
  
|<span data-ttu-id="c5836-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5836-157">Element</span></span>|<span data-ttu-id="c5836-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5836-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5836-159">\<punto ></span><span class="sxs-lookup"><span data-stu-id="c5836-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="c5836-160">Especifica las credenciales actuales de un nodo del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c5836-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5836-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5836-161">Remarks</span></span>  
 <span data-ttu-id="c5836-162">Este elemento de configuración contiene una instancia de `X509Certificate2` que se usa al autenticar a los vecinos en la malla del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c5836-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="c5836-163">Para obtener más información acerca de la programación de punto a punto, vea [redes Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="c5836-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5836-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5836-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="c5836-165">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c5836-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="c5836-166">Redes de punto a punto</span><span class="sxs-lookup"><span data-stu-id="c5836-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="c5836-167">Autenticación de mensajes del canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c5836-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="c5836-168">Canal del mismo nivel de autenticación personalizada</span><span class="sxs-lookup"><span data-stu-id="c5836-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="c5836-169">Proteger las aplicaciones de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="c5836-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="c5836-170">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c5836-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

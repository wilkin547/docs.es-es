---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152819"
---
# <a name="certificatereference"></a><span data-ttu-id="79785-101">\<certificateReferencia></span><span class="sxs-lookup"><span data-stu-id="79785-101">\<certificateReference></span></span>
<span data-ttu-id="79785-102">Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="79785-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="79785-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79785-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79785-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="79785-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="79785-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="79785-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="79785-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="79785-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="79785-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReferencia>**</span><span class="sxs-lookup"><span data-stu-id="79785-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79785-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79785-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79785-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79785-109">Attributes and Elements</span></span>  
 <span data-ttu-id="79785-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79785-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79785-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="79785-111">Attributes</span></span>  
  
|<span data-ttu-id="79785-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="79785-112">Attribute</span></span>|<span data-ttu-id="79785-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="79785-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79785-114">storeName</span><span class="sxs-lookup"><span data-stu-id="79785-114">storeName</span></span>|<span data-ttu-id="79785-115">Nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="79785-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="79785-116">El valor predeterminado es "Mi".</span><span class="sxs-lookup"><span data-stu-id="79785-116">The default is "My".</span></span> <span data-ttu-id="79785-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79785-117">Optional.</span></span>|  
|<span data-ttu-id="79785-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="79785-118">storeLocation</span></span>|<span data-ttu-id="79785-119">Valor <xref:System.Security.Cryptography.X509Certificates.StoreLocation> que especifica la ubicación del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="79785-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="79785-120">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="79785-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="79785-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79785-121">Optional.</span></span>|  
|<span data-ttu-id="79785-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="79785-122">x509FindType</span></span>|<span data-ttu-id="79785-123">Valor <xref:System.Security.Cryptography.X509Certificates.X509FindType> que especifica el tipo de búsqueda que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="79785-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="79785-124">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="79785-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="79785-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79785-125">Optional.</span></span>|  
|<span data-ttu-id="79785-126">findValue</span><span class="sxs-lookup"><span data-stu-id="79785-126">findValue</span></span>|<span data-ttu-id="79785-127">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="79785-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="79785-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79785-128">Optional.</span></span>|  
|<span data-ttu-id="79785-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="79785-129">isChainIncluded</span></span>|<span data-ttu-id="79785-130">Especifica si se debe realizar la validación mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="79785-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="79785-131">El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="79785-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="79785-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="79785-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79785-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79785-133">Child Elements</span></span>  
 <span data-ttu-id="79785-134">None</span><span class="sxs-lookup"><span data-stu-id="79785-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79785-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79785-135">Parent Elements</span></span>  
  
|<span data-ttu-id="79785-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="79785-136">Element</span></span>|<span data-ttu-id="79785-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="79785-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79785-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="79785-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="79785-139">Configura el certificado que se usa para cifrar y descifrar tokens.</span><span class="sxs-lookup"><span data-stu-id="79785-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79785-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="79785-140">Remarks</span></span>  
 <span data-ttu-id="79785-141">El `<certificateReference>` elemento especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="79785-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="79785-142">Cuando se especifica como el elemento `<serviceCertificate>` secundario del elemento, especifica la ubicación y la configuración de verificación del certificado X.509 que se usa para cifrar y descifrar tokens.</span><span class="sxs-lookup"><span data-stu-id="79785-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="79785-143">El `<certificateReference>` elemento se representa <xref:System.ServiceModel.Configuration.CertificateReferenceElement> mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="79785-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

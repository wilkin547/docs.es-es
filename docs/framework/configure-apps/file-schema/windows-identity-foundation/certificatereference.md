---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252142"
---
# <a name="certificatereference"></a><span data-ttu-id="dc9b3-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="dc9b3-101">\<certificateReference></span></span>
<span data-ttu-id="dc9b3-102">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="dc9b3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc9b3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc9b3-104">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="dc9b3-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="dc9b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="dc9b3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="dc9b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="dc9b3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="dc9b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> certificateReference**</span><span class="sxs-lookup"><span data-stu-id="dc9b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc9b3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc9b3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc9b3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc9b3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dc9b3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc9b3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc9b3-111">Attributes</span></span>  
  
|<span data-ttu-id="dc9b3-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="dc9b3-112">Attribute</span></span>|<span data-ttu-id="dc9b3-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc9b3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc9b3-114">storeName</span><span class="sxs-lookup"><span data-stu-id="dc9b3-114">storeName</span></span>|<span data-ttu-id="dc9b3-115">Nombre del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="dc9b3-116">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="dc9b3-116">The default is "My".</span></span> <span data-ttu-id="dc9b3-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-117">Optional.</span></span>|  
|<span data-ttu-id="dc9b3-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="dc9b3-118">storeLocation</span></span>|<span data-ttu-id="dc9b3-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica la ubicación del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="dc9b3-120">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="dc9b3-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="dc9b3-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-121">Optional.</span></span>|  
|<span data-ttu-id="dc9b3-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="dc9b3-122">x509FindType</span></span>|<span data-ttu-id="dc9b3-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Valor que especifica el tipo de búsqueda que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="dc9b3-124">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="dc9b3-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="dc9b3-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-125">Optional.</span></span>|  
|<span data-ttu-id="dc9b3-126">findValue</span><span class="sxs-lookup"><span data-stu-id="dc9b3-126">findValue</span></span>|<span data-ttu-id="dc9b3-127">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="dc9b3-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-128">Optional.</span></span>|  
|<span data-ttu-id="dc9b3-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="dc9b3-129">isChainIncluded</span></span>|<span data-ttu-id="dc9b3-130">Especifica si se debe realizar la validación mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="dc9b3-131">El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="dc9b3-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc9b3-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc9b3-133">Child Elements</span></span>  
 <span data-ttu-id="dc9b3-134">None</span><span class="sxs-lookup"><span data-stu-id="dc9b3-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc9b3-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc9b3-135">Parent Elements</span></span>  
  
|<span data-ttu-id="dc9b3-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc9b3-136">Element</span></span>|<span data-ttu-id="dc9b3-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc9b3-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc9b3-138">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="dc9b3-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="dc9b3-139">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc9b3-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc9b3-140">Remarks</span></span>  
 <span data-ttu-id="dc9b3-141">El `<certificateReference>` elemento especifica valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="dc9b3-142">Cuando se especifica como el elemento secundario del `<serviceCertificate>` elemento, especifica la configuración de ubicación y comprobación del certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="dc9b3-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="dc9b3-143">El elemento se representa mediante la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase. `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="dc9b3-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

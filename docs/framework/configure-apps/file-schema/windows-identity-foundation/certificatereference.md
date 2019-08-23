---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941932"
---
# <a name="certificatereference"></a><span data-ttu-id="e1291-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="e1291-101">\<certificateReference></span></span>
<span data-ttu-id="e1291-102">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="e1291-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="e1291-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="e1291-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="e1291-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="e1291-104">\<federationConfiguration></span></span>  
<span data-ttu-id="e1291-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e1291-105">\<serviceCertificate></span></span>  
<span data-ttu-id="e1291-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="e1291-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1291-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1291-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1291-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1291-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e1291-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1291-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1291-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1291-110">Attributes</span></span>  
  
|<span data-ttu-id="e1291-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1291-111">Attribute</span></span>|<span data-ttu-id="e1291-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e1291-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1291-113">storeName</span><span class="sxs-lookup"><span data-stu-id="e1291-113">storeName</span></span>|<span data-ttu-id="e1291-114">Nombre del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="e1291-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="e1291-115">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="e1291-115">The default is "My".</span></span> <span data-ttu-id="e1291-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1291-116">Optional.</span></span>|  
|<span data-ttu-id="e1291-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="e1291-117">storeLocation</span></span>|<span data-ttu-id="e1291-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Valor que especifica la ubicación del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="e1291-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="e1291-119">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="e1291-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="e1291-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1291-120">Optional.</span></span>|  
|<span data-ttu-id="e1291-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="e1291-121">x509FindType</span></span>|<span data-ttu-id="e1291-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Valor que especifica el tipo de búsqueda que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e1291-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="e1291-123">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="e1291-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="e1291-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1291-124">Optional.</span></span>|  
|<span data-ttu-id="e1291-125">findValue</span><span class="sxs-lookup"><span data-stu-id="e1291-125">findValue</span></span>|<span data-ttu-id="e1291-126">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="e1291-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="e1291-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1291-127">Optional.</span></span>|  
|<span data-ttu-id="e1291-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="e1291-128">isChainIncluded</span></span>|<span data-ttu-id="e1291-129">Especifica si se debe realizar la validación mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="e1291-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="e1291-130">El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="e1291-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="e1291-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e1291-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1291-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1291-132">Child Elements</span></span>  
 <span data-ttu-id="e1291-133">None</span><span class="sxs-lookup"><span data-stu-id="e1291-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1291-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1291-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e1291-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1291-135">Element</span></span>|<span data-ttu-id="e1291-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e1291-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1291-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="e1291-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="e1291-138">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="e1291-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1291-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1291-139">Remarks</span></span>  
 <span data-ttu-id="e1291-140">El `<certificateReference>` elemento especifica valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="e1291-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="e1291-141">Cuando se especifica como el elemento secundario del `<serviceCertificate>` elemento, especifica la configuración de ubicación y comprobación del certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="e1291-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="e1291-142">El elemento se representa mediante la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase. `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="e1291-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423025"
---
# <a name="certificatereference"></a><span data-ttu-id="32737-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="32737-101">\<certificateReference></span></span>
<span data-ttu-id="32737-102">Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="32737-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="32737-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="32737-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="32737-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="32737-104">\<federationConfiguration></span></span>  
<span data-ttu-id="32737-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="32737-105">\<serviceCertificate></span></span>  
<span data-ttu-id="32737-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="32737-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32737-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32737-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32737-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="32737-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32737-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="32737-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32737-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="32737-110">Attributes</span></span>  
  
|<span data-ttu-id="32737-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="32737-111">Attribute</span></span>|<span data-ttu-id="32737-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="32737-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32737-113">storeName</span><span class="sxs-lookup"><span data-stu-id="32737-113">storeName</span></span>|<span data-ttu-id="32737-114">El nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="32737-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="32737-115">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="32737-115">The default is "My".</span></span> <span data-ttu-id="32737-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="32737-116">Optional.</span></span>|  
|<span data-ttu-id="32737-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="32737-117">storeLocation</span></span>|<span data-ttu-id="32737-118">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica la ubicación del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="32737-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="32737-119">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="32737-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="32737-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="32737-120">Optional.</span></span>|  
|<span data-ttu-id="32737-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="32737-121">x509FindType</span></span>|<span data-ttu-id="32737-122">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valor que especifica el tipo de búsqueda que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="32737-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="32737-123">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="32737-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="32737-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="32737-124">Optional.</span></span>|  
|<span data-ttu-id="32737-125">findValue</span><span class="sxs-lookup"><span data-stu-id="32737-125">findValue</span></span>|<span data-ttu-id="32737-126">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="32737-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="32737-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="32737-127">Optional.</span></span>|  
|<span data-ttu-id="32737-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="32737-128">isChainIncluded</span></span>|<span data-ttu-id="32737-129">Especifica si se debe realizar la validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="32737-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="32737-130">El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="32737-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="32737-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="32737-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32737-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="32737-132">Child Elements</span></span>  
 <span data-ttu-id="32737-133">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32737-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32737-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="32737-134">Parent Elements</span></span>  
  
|<span data-ttu-id="32737-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="32737-135">Element</span></span>|<span data-ttu-id="32737-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="32737-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32737-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="32737-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="32737-138">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="32737-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32737-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32737-139">Remarks</span></span>  
 <span data-ttu-id="32737-140">El `<certificateReference>` elemento especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="32737-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="32737-141">Cuando se especifica como el elemento secundario de la `<serviceCertificate>` elemento, especifica la configuración de ubicación y la comprobación del certificado X.509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="32737-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="32737-142">El `<certificateReference>` elemento representado por la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.</span><span class="sxs-lookup"><span data-stu-id="32737-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

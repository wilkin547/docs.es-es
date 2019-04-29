---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667384"
---
# <a name="certificatereference"></a><span data-ttu-id="f5ac4-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="f5ac4-101">\<certificateReference></span></span>
<span data-ttu-id="f5ac4-102">Especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="f5ac4-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="f5ac4-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="f5ac4-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f5ac4-104">\<federationConfiguration></span></span>  
<span data-ttu-id="f5ac4-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f5ac4-105">\<serviceCertificate></span></span>  
<span data-ttu-id="f5ac4-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="f5ac4-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ac4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5ac4-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5ac4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5ac4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f5ac4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5ac4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5ac4-110">Attributes</span></span>  
  
|<span data-ttu-id="f5ac4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5ac4-111">Attribute</span></span>|<span data-ttu-id="f5ac4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5ac4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5ac4-113">storeName</span><span class="sxs-lookup"><span data-stu-id="f5ac4-113">storeName</span></span>|<span data-ttu-id="f5ac4-114">El nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="f5ac4-115">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="f5ac4-115">The default is "My".</span></span> <span data-ttu-id="f5ac4-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-116">Optional.</span></span>|  
|<span data-ttu-id="f5ac4-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f5ac4-117">storeLocation</span></span>|<span data-ttu-id="f5ac4-118">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica la ubicación del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="f5ac4-119">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="f5ac4-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="f5ac4-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-120">Optional.</span></span>|  
|<span data-ttu-id="f5ac4-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f5ac4-121">x509FindType</span></span>|<span data-ttu-id="f5ac4-122">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valor que especifica el tipo de búsqueda que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="f5ac4-123">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="f5ac4-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="f5ac4-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-124">Optional.</span></span>|  
|<span data-ttu-id="f5ac4-125">findValue</span><span class="sxs-lookup"><span data-stu-id="f5ac4-125">findValue</span></span>|<span data-ttu-id="f5ac4-126">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f5ac4-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-127">Optional.</span></span>|  
|<span data-ttu-id="f5ac4-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="f5ac4-128">isChainIncluded</span></span>|<span data-ttu-id="f5ac4-129">Especifica si se debe realizar la validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="f5ac4-130">El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="f5ac4-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5ac4-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5ac4-132">Child Elements</span></span>  
 <span data-ttu-id="f5ac4-133">Ninguna</span><span class="sxs-lookup"><span data-stu-id="f5ac4-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5ac4-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5ac4-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f5ac4-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5ac4-135">Element</span></span>|<span data-ttu-id="f5ac4-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5ac4-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5ac4-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f5ac4-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="f5ac4-138">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ac4-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5ac4-139">Remarks</span></span>  
 <span data-ttu-id="f5ac4-140">El `<certificateReference>` elemento especifica la configuración que se usa para buscar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="f5ac4-141">Cuando se especifica como el elemento secundario de la `<serviceCertficate>` elemento, especifica la configuración de ubicación y la comprobación del certificado X.509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-141">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="f5ac4-142">El `<certificateReference>` elemento representado por la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.</span><span class="sxs-lookup"><span data-stu-id="f5ac4-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

---
title: '&lt;certificateReference&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c8acf4b6d6e6e8a0fcf7d73139a1d2c5ea03f063
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="a5d6d-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="a5d6d-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="a5d6d-103">Especifica valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="a5d6d-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="a5d6d-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="a5d6d-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a5d6d-105">\<federationConfiguration></span></span>  
<span data-ttu-id="a5d6d-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a5d6d-106">\<serviceCertificate></span></span>  
<span data-ttu-id="a5d6d-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="a5d6d-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d6d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5d6d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5d6d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5d6d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5d6d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5d6d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5d6d-111">Attributes</span></span>  
  
|<span data-ttu-id="a5d6d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a5d6d-112">Attribute</span></span>|<span data-ttu-id="a5d6d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5d6d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5d6d-114">storeName</span><span class="sxs-lookup"><span data-stu-id="a5d6d-114">storeName</span></span>|<span data-ttu-id="a5d6d-115">El nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="a5d6d-116">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="a5d6d-116">The default is "My".</span></span> <span data-ttu-id="a5d6d-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-117">Optional.</span></span>|  
|<span data-ttu-id="a5d6d-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="a5d6d-118">storeLocation</span></span>|<span data-ttu-id="a5d6d-119">Un <xref:System.Security.Cryptography.X509Certificates.StoreLocation> valor que especifica la ubicación del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="a5d6d-120">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="a5d6d-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="a5d6d-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-121">Optional.</span></span>|  
|<span data-ttu-id="a5d6d-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="a5d6d-122">x509FindType</span></span>|<span data-ttu-id="a5d6d-123">Un <xref:System.Security.Cryptography.X509Certificates.X509FindType> valor que especifica el tipo de búsqueda que va a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="a5d6d-124">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="a5d6d-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="a5d6d-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-125">Optional.</span></span>|  
|<span data-ttu-id="a5d6d-126">findValue</span><span class="sxs-lookup"><span data-stu-id="a5d6d-126">findValue</span></span>|<span data-ttu-id="a5d6d-127">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a5d6d-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-128">Optional.</span></span>|  
|<span data-ttu-id="a5d6d-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="a5d6d-129">isChainIncluded</span></span>|<span data-ttu-id="a5d6d-130">Especifica si se debe realizar validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="a5d6d-131">El valor predeterminado es "true"; se realiza la validación mediante el uso de la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="a5d6d-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5d6d-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a5d6d-133">Child Elements</span></span>  
 <span data-ttu-id="a5d6d-134">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a5d6d-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5d6d-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5d6d-135">Parent Elements</span></span>  
  
|<span data-ttu-id="a5d6d-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5d6d-136">Element</span></span>|<span data-ttu-id="a5d6d-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5d6d-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5d6d-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="a5d6d-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="a5d6d-139">Configura el certificado que se utiliza para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5d6d-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5d6d-140">Remarks</span></span>  
 <span data-ttu-id="a5d6d-141">El `<certificateReference>` elemento especifica los valores que se usan para encontrar y validar un certificado X.509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="a5d6d-142">Cuando se especifica como el elemento secundario de la `<serviceCertficate>` elemento, especifica la configuración de ubicación y la comprobación del certificado X.509 que se utiliza para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="a5d6d-143">El `<certificateReference>` elemento representado por la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.</span><span class="sxs-lookup"><span data-stu-id="a5d6d-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

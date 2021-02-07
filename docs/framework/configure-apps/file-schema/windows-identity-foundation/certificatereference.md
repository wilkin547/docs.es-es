---
description: 'Más información acerca de: <certificateReference>'
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 3404d44457849fb78ae88617d049a2199f2b5509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681791"
---
# \<certificateReference>

<span data-ttu-id="c7fdb-102">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="c7fdb-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7fdb-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7fdb-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c7fdb-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c7fdb-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7fdb-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c7fdb-106">Attributes</span></span>  
  
|<span data-ttu-id="c7fdb-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="c7fdb-107">Attribute</span></span>|<span data-ttu-id="c7fdb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7fdb-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7fdb-109">storeName</span><span class="sxs-lookup"><span data-stu-id="c7fdb-109">storeName</span></span>|<span data-ttu-id="c7fdb-110">Nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-110">The name of the X.509 certificate store.</span></span> <span data-ttu-id="c7fdb-111">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="c7fdb-111">The default is "My".</span></span> <span data-ttu-id="c7fdb-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-112">Optional.</span></span>|  
|<span data-ttu-id="c7fdb-113">storeLocation</span><span class="sxs-lookup"><span data-stu-id="c7fdb-113">storeLocation</span></span>|<span data-ttu-id="c7fdb-114"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica la ubicación del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-114">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="c7fdb-115">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="c7fdb-115">The default value is "LocalMachine".</span></span> <span data-ttu-id="c7fdb-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-116">Optional.</span></span>|  
|<span data-ttu-id="c7fdb-117">x509FindType</span><span class="sxs-lookup"><span data-stu-id="c7fdb-117">x509FindType</span></span>|<span data-ttu-id="c7fdb-118"><xref:System.Security.Cryptography.X509Certificates.X509FindType>Valor que especifica el tipo de búsqueda que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-118">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="c7fdb-119">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="c7fdb-119">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="c7fdb-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-120">Optional.</span></span>|  
|<span data-ttu-id="c7fdb-121">findValue</span><span class="sxs-lookup"><span data-stu-id="c7fdb-121">findValue</span></span>|<span data-ttu-id="c7fdb-122">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-122">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="c7fdb-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-123">Optional.</span></span>|  
|<span data-ttu-id="c7fdb-124">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="c7fdb-124">isChainIncluded</span></span>|<span data-ttu-id="c7fdb-125">Especifica si se debe realizar la validación mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-125">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="c7fdb-126">El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-126">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="c7fdb-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-127">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7fdb-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c7fdb-128">Child Elements</span></span>  

 <span data-ttu-id="c7fdb-129">None</span><span class="sxs-lookup"><span data-stu-id="c7fdb-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c7fdb-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c7fdb-130">Parent Elements</span></span>  
  
|<span data-ttu-id="c7fdb-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7fdb-131">Element</span></span>|<span data-ttu-id="c7fdb-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7fdb-132">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="c7fdb-133">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-133">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7fdb-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7fdb-134">Remarks</span></span>  

 <span data-ttu-id="c7fdb-135">El `<certificateReference>` elemento especifica valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-135">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="c7fdb-136">Cuando se especifica como el elemento secundario del `<serviceCertificate>` elemento, especifica la configuración de ubicación y comprobación del certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-136">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="c7fdb-137">El `<certificateReference>` elemento se representa mediante la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.</span><span class="sxs-lookup"><span data-stu-id="c7fdb-137">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

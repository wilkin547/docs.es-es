---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201386"
---
# \<certificateReference>

<span data-ttu-id="6cfc6-101">Especifica los valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="6cfc6-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6cfc6-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cfc6-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6cfc6-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6cfc6-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cfc6-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="6cfc6-105">Attributes</span></span>  
  
|<span data-ttu-id="6cfc6-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="6cfc6-106">Attribute</span></span>|<span data-ttu-id="6cfc6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6cfc6-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6cfc6-108">storeName</span><span class="sxs-lookup"><span data-stu-id="6cfc6-108">storeName</span></span>|<span data-ttu-id="6cfc6-109">Nombre del almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="6cfc6-110">El valor predeterminado es "My".</span><span class="sxs-lookup"><span data-stu-id="6cfc6-110">The default is "My".</span></span> <span data-ttu-id="6cfc6-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-111">Optional.</span></span>|  
|<span data-ttu-id="6cfc6-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="6cfc6-112">storeLocation</span></span>|<span data-ttu-id="6cfc6-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>Valor que especifica la ubicación del almacén de certificados X. 509.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="6cfc6-114">El valor predeterminado es "LocalMachine".</span><span class="sxs-lookup"><span data-stu-id="6cfc6-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="6cfc6-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-115">Optional.</span></span>|  
|<span data-ttu-id="6cfc6-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="6cfc6-116">x509FindType</span></span>|<span data-ttu-id="6cfc6-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>Valor que especifica el tipo de búsqueda que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="6cfc6-118">El valor predeterminado es "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="6cfc6-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="6cfc6-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-119">Optional.</span></span>|  
|<span data-ttu-id="6cfc6-120">findValue</span><span class="sxs-lookup"><span data-stu-id="6cfc6-120">findValue</span></span>|<span data-ttu-id="6cfc6-121">El valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="6cfc6-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-122">Optional.</span></span>|  
|<span data-ttu-id="6cfc6-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="6cfc6-123">isChainIncluded</span></span>|<span data-ttu-id="6cfc6-124">Especifica si se debe realizar la validación mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="6cfc6-125">El valor predeterminado es "true"; la validación se realiza mediante la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="6cfc6-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6cfc6-127">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6cfc6-127">Child Elements</span></span>  

 <span data-ttu-id="6cfc6-128">None</span><span class="sxs-lookup"><span data-stu-id="6cfc6-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6cfc6-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6cfc6-129">Parent Elements</span></span>  
  
|<span data-ttu-id="6cfc6-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="6cfc6-130">Element</span></span>|<span data-ttu-id="6cfc6-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="6cfc6-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="6cfc6-132">Configura el certificado que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cfc6-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6cfc6-133">Remarks</span></span>  

 <span data-ttu-id="6cfc6-134">El `<certificateReference>` elemento especifica valores que se usan para buscar y validar un certificado X. 509 en un almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="6cfc6-135">Cuando se especifica como el elemento secundario del `<serviceCertificate>` elemento, especifica la configuración de ubicación y comprobación del certificado X. 509 que se usa para cifrar y descifrar los tokens.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="6cfc6-136">El `<certificateReference>` elemento se representa mediante la <xref:System.ServiceModel.Configuration.CertificateReferenceElement> clase.</span><span class="sxs-lookup"><span data-stu-id="6cfc6-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>

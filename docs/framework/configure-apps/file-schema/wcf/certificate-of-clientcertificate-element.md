---
title: '&lt;certificate&gt; del elemento &lt;clientCertificate&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef4067d0fa74aa90841040ca5e6b3ea22f1e499
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="a27b0-102">&lt;certificate&gt; del elemento &lt;clientCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="a27b0-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="a27b0-103">Especifica un certificado X.509 usado para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a27b0-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="a27b0-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a27b0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a27b0-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a27b0-105">\<behaviors></span></span>  
<span data-ttu-id="a27b0-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a27b0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a27b0-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a27b0-107">\<behavior></span></span>  
<span data-ttu-id="a27b0-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a27b0-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a27b0-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="a27b0-109">\<clientCertificate></span></span>  
<span data-ttu-id="a27b0-110">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="a27b0-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a27b0-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a27b0-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a27b0-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a27b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a27b0-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a27b0-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a27b0-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="a27b0-114">Attributes</span></span>  
  
|<span data-ttu-id="a27b0-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="a27b0-115">Attribute</span></span>|<span data-ttu-id="a27b0-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a27b0-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="a27b0-117">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="a27b0-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a27b0-118">El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="a27b0-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="a27b0-119">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a27b0-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="a27b0-120">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="a27b0-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="a27b0-121">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a27b0-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a27b0-122">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="a27b0-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="a27b0-123">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a27b0-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a27b0-124">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="a27b0-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="a27b0-125">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="a27b0-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="a27b0-126">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a27b0-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a27b0-127">-AddressBook: Almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="a27b0-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a27b0-128">-AuthRoot: Almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="a27b0-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a27b0-129">-CertificationAuthority: Almacén de certificados para entidades de certificación intermedias (CA).</span><span class="sxs-lookup"><span data-stu-id="a27b0-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="a27b0-130">-Disallowed: Almacén de certificados para certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="a27b0-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a27b0-131">-My: Almacén de certificados para los certificados personales.</span><span class="sxs-lookup"><span data-stu-id="a27b0-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a27b0-132">-Root: Almacén de certificados para entidades de certificación raíz de confianza (CA).</span><span class="sxs-lookup"><span data-stu-id="a27b0-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="a27b0-133">-TrustedPeople: Almacén de certificados para las personas de confianza directa y recursos.</span><span class="sxs-lookup"><span data-stu-id="a27b0-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a27b0-134">-TrustedPublisher: Almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="a27b0-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a27b0-135">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="a27b0-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="a27b0-136">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a27b0-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="a27b0-137">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a27b0-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a27b0-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a27b0-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a27b0-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a27b0-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="a27b0-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a27b0-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a27b0-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a27b0-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="a27b0-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a27b0-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a27b0-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a27b0-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a27b0-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a27b0-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="a27b0-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a27b0-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a27b0-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a27b0-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="a27b0-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a27b0-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a27b0-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a27b0-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a27b0-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a27b0-149">-   FindByExtension</span></span><br /><span data-ttu-id="a27b0-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a27b0-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a27b0-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a27b0-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a27b0-152">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="a27b0-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="a27b0-153">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a27b0-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a27b0-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a27b0-154">Child Elements</span></span>  
 <span data-ttu-id="a27b0-155">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a27b0-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a27b0-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a27b0-156">Parent Elements</span></span>  
  
|<span data-ttu-id="a27b0-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="a27b0-157">Element</span></span>|<span data-ttu-id="a27b0-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="a27b0-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a27b0-159">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="a27b0-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="a27b0-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a27b0-160">Remarks</span></span>  
 <span data-ttu-id="a27b0-161">El elemento `<certificate>` se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="a27b0-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="a27b0-162">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="a27b0-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="a27b0-163">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="a27b0-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="a27b0-164">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="a27b0-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="a27b0-165">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="a27b0-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="a27b0-166">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a27b0-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a27b0-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a27b0-167">Example</span></span>  
 <span data-ttu-id="a27b0-168">El código siguiente especifica cómo buscar un certificado X.509 adecuado y un tipo de validación personalizado en el elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="a27b0-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a27b0-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="a27b0-169">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [<span data-ttu-id="a27b0-170">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="a27b0-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a27b0-171">Cómo: crear un servicio que emplee un validador de certificado personalizada</span><span class="sxs-lookup"><span data-stu-id="a27b0-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="a27b0-172">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="a27b0-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

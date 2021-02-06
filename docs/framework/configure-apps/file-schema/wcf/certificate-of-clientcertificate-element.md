---
description: 'Más información sobre: <certificate> del <clientCertificate> elemento'
title: <certificate> del <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: a677c04055016c77794dd99a8c237b5eb6c13f5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639099"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="04bae-103">\<certificate> del \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="04bae-103">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="04bae-104">Especifica un certificado X.509 usado para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="04bae-104">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="04bae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04bae-105">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04bae-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04bae-106">Attributes and Elements</span></span>  

 <span data-ttu-id="04bae-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04bae-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04bae-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="04bae-108">Attributes</span></span>  
  
|<span data-ttu-id="04bae-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="04bae-109">Attribute</span></span>|<span data-ttu-id="04bae-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="04bae-110">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="04bae-111">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="04bae-111">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="04bae-112">El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="04bae-112">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="04bae-113">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="04bae-113">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="04bae-114">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="04bae-114">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="04bae-115">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="04bae-115">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04bae-116">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="04bae-116">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="04bae-117">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="04bae-117">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="04bae-118">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="04bae-118">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="04bae-119">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="04bae-119">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="04bae-120">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="04bae-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04bae-121">-AddressBook: almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="04bae-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="04bae-122">-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="04bae-122">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="04bae-123">-CertificationAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.</span><span class="sxs-lookup"><span data-stu-id="04bae-123">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="04bae-124">-No permitido: almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="04bae-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="04bae-125">-Mi: almacén de certificados para Certificados personales.</span><span class="sxs-lookup"><span data-stu-id="04bae-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="04bae-126">-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="04bae-126">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="04bae-127">-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="04bae-127">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="04bae-128">-TrustedPublisher: almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="04bae-128">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="04bae-129">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="04bae-129">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="04bae-130">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="04bae-130">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="04bae-131">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="04bae-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="04bae-132">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="04bae-132">-   FindByThumbPrint</span></span><br /><span data-ttu-id="04bae-133">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="04bae-133">-   FindBySubjectName</span></span><br /><span data-ttu-id="04bae-134">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04bae-134">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="04bae-135">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="04bae-135">-   FindByIssuerName</span></span><br /><span data-ttu-id="04bae-136">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="04bae-136">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="04bae-137">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="04bae-137">-   FindBySerialNumber</span></span><br /><span data-ttu-id="04bae-138">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="04bae-138">-   FindByTimeValid</span></span><br /><span data-ttu-id="04bae-139">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="04bae-139">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="04bae-140">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="04bae-140">-   FindByTemplateName</span></span><br /><span data-ttu-id="04bae-141">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="04bae-141">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="04bae-142">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="04bae-142">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="04bae-143">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="04bae-143">-   FindByExtension</span></span><br /><span data-ttu-id="04bae-144">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="04bae-144">-   FindByKeyUsage</span></span><br /><span data-ttu-id="04bae-145">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="04bae-145">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="04bae-146">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="04bae-146">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="04bae-147">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="04bae-147">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04bae-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04bae-148">Child Elements</span></span>  

 <span data-ttu-id="04bae-149">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="04bae-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04bae-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04bae-150">Parent Elements</span></span>  
  
|<span data-ttu-id="04bae-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="04bae-151">Element</span></span>|<span data-ttu-id="04bae-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="04bae-152">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="04bae-153">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04bae-153">Remarks</span></span>  

 <span data-ttu-id="04bae-154">El elemento `<certificate>` se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="04bae-154">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="04bae-155">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="04bae-155">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="04bae-156">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="04bae-156">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="04bae-157">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="04bae-157">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="04bae-158">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="04bae-158">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="04bae-159">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="04bae-159">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04bae-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04bae-160">Example</span></span>  

 <span data-ttu-id="04bae-161">El código siguiente especifica cómo buscar un certificado X.509 adecuado y un tipo de validación personalizado en el elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="04bae-161">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
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
  
## <a name="see-also"></a><span data-ttu-id="04bae-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="04bae-162">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="04bae-163">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="04bae-163">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="04bae-164">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="04bae-164">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="04bae-165">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="04bae-165">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

---
title: <certificate> del <clientCertificate> elemento
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: 35ea3814e208921abaf44e6ef431c4e1b44cde60
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151146"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="f0725-102">\<certificate> del \<clientCertificate> elemento</span><span class="sxs-lookup"><span data-stu-id="f0725-102">\<certificate> of \<clientCertificate> Element</span></span>

<span data-ttu-id="f0725-103">Especifica un certificado X.509 usado para firmar y cifrar mensajes.</span><span class="sxs-lookup"><span data-stu-id="f0725-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="f0725-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0725-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0725-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0725-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f0725-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0725-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0725-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0725-107">Attributes</span></span>  
  
|<span data-ttu-id="f0725-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f0725-108">Attribute</span></span>|<span data-ttu-id="f0725-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0725-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f0725-110">Una cadena que contiene el valor que se va a buscar en el almacén de certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f0725-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f0725-111">El tipo contenido en el atributo debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="f0725-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="f0725-112">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="f0725-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f0725-113">Especifica la ubicación del almacén de certificados X.509 que el cliente utiliza para validar el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="f0725-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="f0725-114">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0725-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f0725-115">-LocalMachine: el almacén de certificados asignado al equipo local.</span><span class="sxs-lookup"><span data-stu-id="f0725-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f0725-116">-CurrentUser: el almacén de certificados asignado al usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f0725-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f0725-117">El valor predeterminado es LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f0725-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f0725-118">Especifica el nombre del almacén del certificado X.509 que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="f0725-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f0725-119">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0725-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f0725-120">-AddressBook: almacén de certificados para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="f0725-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f0725-121">-AuthRoot: almacén de certificados para entidades de certificación (CA) de terceros.</span><span class="sxs-lookup"><span data-stu-id="f0725-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f0725-122">-CertificationAuthority: almacén de certificados para las entidades de certificación (CA) intermedias.</span><span class="sxs-lookup"><span data-stu-id="f0725-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f0725-123">-No permitido: almacén de certificados para los certificados revocados.</span><span class="sxs-lookup"><span data-stu-id="f0725-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f0725-124">-Mi: almacén de certificados para Certificados personales.</span><span class="sxs-lookup"><span data-stu-id="f0725-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f0725-125">-Root: almacén de certificados para entidades de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="f0725-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f0725-126">-TrustedPeople: almacén de certificados para las personas y los recursos de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="f0725-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="f0725-127">-TrustedPublisher: almacén de certificados para publicadores de confianza directa.</span><span class="sxs-lookup"><span data-stu-id="f0725-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="f0725-128">El valor predeterminado es My.</span><span class="sxs-lookup"><span data-stu-id="f0725-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f0725-129">Define el tipo de búsqueda de X.509 que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f0725-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f0725-130">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0725-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f0725-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="f0725-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f0725-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f0725-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="f0725-133">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f0725-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f0725-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="f0725-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="f0725-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="f0725-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f0725-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="f0725-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f0725-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="f0725-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="f0725-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="f0725-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f0725-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="f0725-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="f0725-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="f0725-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f0725-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="f0725-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f0725-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="f0725-142">-   FindByExtension</span></span><br /><span data-ttu-id="f0725-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="f0725-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f0725-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="f0725-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f0725-145">El tipo contenido en el atributo `findValue` debe satisfacer los requisitos del X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="f0725-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="f0725-146">El valor predeterminado es FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f0725-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0725-147">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0725-147">Child Elements</span></span>  

 <span data-ttu-id="f0725-148">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0725-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f0725-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0725-149">Parent Elements</span></span>  
  
|<span data-ttu-id="f0725-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0725-150">Element</span></span>|<span data-ttu-id="f0725-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0725-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="f0725-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0725-152">Remarks</span></span>  

 <span data-ttu-id="f0725-153">El elemento `<certificate>` se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="f0725-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="f0725-154">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="f0725-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="f0725-155">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="f0725-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="f0725-156">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="f0725-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="f0725-157">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="f0725-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="f0725-158">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="f0725-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0725-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f0725-159">Example</span></span>  

 <span data-ttu-id="f0725-160">El código siguiente especifica cómo buscar un certificado X.509 adecuado y un tipo de validación personalizado en el elemento `<authentication>`.</span><span class="sxs-lookup"><span data-stu-id="f0725-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0725-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0725-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="f0725-162">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f0725-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f0725-163">Procedimiento para crear un servicio que emplee un validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="f0725-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="f0725-164">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="f0725-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

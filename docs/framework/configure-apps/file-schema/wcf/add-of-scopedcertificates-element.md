---
title: <add>del <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398342"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="9a7f5-102">\<Agregar > del \<elemento > scopedCertificates</span><span class="sxs-lookup"><span data-stu-id="9a7f5-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="9a7f5-103">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="9a7f5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9a7f5-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9a7f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9a7f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="9a7f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="9a7f5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="9a7f5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="9a7f5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> scopedCertificates**](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="9a7f5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="9a7f5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="9a7f5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a7f5-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a7f5-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a7f5-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a7f5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9a7f5-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a7f5-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a7f5-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a7f5-116">Attributes</span></span>  
  
|<span data-ttu-id="9a7f5-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="9a7f5-117">Attribute</span></span>|<span data-ttu-id="9a7f5-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9a7f5-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="9a7f5-119">targetUri</span></span>|<span data-ttu-id="9a7f5-120">Cadena.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-120">String.</span></span> <span data-ttu-id="9a7f5-121">Especifica el URI del servicio asociado al certificado.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="9a7f5-122">findValue</span><span class="sxs-lookup"><span data-stu-id="9a7f5-122">findValue</span></span>|<span data-ttu-id="9a7f5-123">Cadena.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-123">String.</span></span> <span data-ttu-id="9a7f5-124">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-124">The value to search for.</span></span>|  
|<span data-ttu-id="9a7f5-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="9a7f5-125">x509FindType</span></span>|<span data-ttu-id="9a7f5-126">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-126">Enumeration.</span></span> <span data-ttu-id="9a7f5-127">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="9a7f5-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="9a7f5-128">storeLocation</span></span>|<span data-ttu-id="9a7f5-129">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-129">Enumeration.</span></span> <span data-ttu-id="9a7f5-130">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="9a7f5-131">storeName</span><span class="sxs-lookup"><span data-stu-id="9a7f5-131">storeName</span></span>|<span data-ttu-id="9a7f5-132">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-132">Enumeration.</span></span> <span data-ttu-id="9a7f5-133">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="9a7f5-134">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="9a7f5-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="9a7f5-135">Value</span><span class="sxs-lookup"><span data-stu-id="9a7f5-135">Value</span></span>|<span data-ttu-id="9a7f5-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a7f5-137">string</span><span class="sxs-lookup"><span data-stu-id="9a7f5-137">String</span></span>|<span data-ttu-id="9a7f5-138">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="9a7f5-139">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="9a7f5-140">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="9a7f5-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="9a7f5-141">Valor</span><span class="sxs-lookup"><span data-stu-id="9a7f5-141">Value</span></span>|<span data-ttu-id="9a7f5-142">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a7f5-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="9a7f5-143">Enumeration</span></span>|<span data-ttu-id="9a7f5-144">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="9a7f5-145">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="9a7f5-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="9a7f5-146">Valor</span><span class="sxs-lookup"><span data-stu-id="9a7f5-146">Value</span></span>|<span data-ttu-id="9a7f5-147">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a7f5-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="9a7f5-148">Enumeration</span></span>|<span data-ttu-id="9a7f5-149">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="9a7f5-150">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="9a7f5-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="9a7f5-151">Value</span><span class="sxs-lookup"><span data-stu-id="9a7f5-151">Value</span></span>|<span data-ttu-id="9a7f5-152">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9a7f5-153">Enumeración</span><span class="sxs-lookup"><span data-stu-id="9a7f5-153">Enumeration</span></span>|<span data-ttu-id="9a7f5-154">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, no permitido, My, root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9a7f5-155">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a7f5-155">Child Elements</span></span>  
 <span data-ttu-id="9a7f5-156">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a7f5-157">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a7f5-157">Parent Elements</span></span>  
  
|<span data-ttu-id="9a7f5-158">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a7f5-158">Element</span></span>|<span data-ttu-id="9a7f5-159">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a7f5-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a7f5-160">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="9a7f5-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="9a7f5-161">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a7f5-162">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a7f5-162">Remarks</span></span>  
 <span data-ttu-id="9a7f5-163">Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="9a7f5-164">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="9a7f5-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="9a7f5-165">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="9a7f5-166">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="9a7f5-167">Para obtener más información, consulte la sección "certificados con ámbito" [de How to: Cree un cliente](../../../wcf/feature-details/how-to-create-a-federated-client.md)federado.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a7f5-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a7f5-168">Example</span></span>  
 <span data-ttu-id="9a7f5-169">En el ejemplo siguiente se agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="9a7f5-169">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="9a7f5-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a7f5-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="9a7f5-171">Cómo: Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="9a7f5-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="9a7f5-172">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="9a7f5-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="9a7f5-173">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="9a7f5-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="9a7f5-174">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9a7f5-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <add> de <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 06a624d0146745581dfe907d044d1f7d3b857902
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673873"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="ff79b-102">\<Agregar > de \<scopedCertificates > elemento</span><span class="sxs-lookup"><span data-stu-id="ff79b-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="ff79b-103">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="ff79b-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
 <span data-ttu-id="ff79b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ff79b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ff79b-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="ff79b-105">\<behaviors></span></span>  
<span data-ttu-id="ff79b-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="ff79b-106">endpointBehaviors section</span></span>  
<span data-ttu-id="ff79b-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="ff79b-107">\<behavior></span></span>  
<span data-ttu-id="ff79b-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="ff79b-108">\<clientCredentials></span></span>  
<span data-ttu-id="ff79b-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="ff79b-109">\<serviceCertificate></span></span>  
<span data-ttu-id="ff79b-110">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="ff79b-110">\<scopedCertificates></span></span>  
<span data-ttu-id="ff79b-111">\<Agregar > elemento para \<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="ff79b-111">\<add> element for \<scopedCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff79b-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff79b-112">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff79b-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ff79b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ff79b-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff79b-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff79b-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff79b-115">Attributes</span></span>  
  
|<span data-ttu-id="ff79b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="ff79b-116">Attribute</span></span>|<span data-ttu-id="ff79b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff79b-118">targetUri</span><span class="sxs-lookup"><span data-stu-id="ff79b-118">targetUri</span></span>|<span data-ttu-id="ff79b-119">Cadena.</span><span class="sxs-lookup"><span data-stu-id="ff79b-119">String.</span></span> <span data-ttu-id="ff79b-120">Especifica el URI del servicio asociado al certificado.</span><span class="sxs-lookup"><span data-stu-id="ff79b-120">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="ff79b-121">findValue</span><span class="sxs-lookup"><span data-stu-id="ff79b-121">findValue</span></span>|<span data-ttu-id="ff79b-122">Cadena.</span><span class="sxs-lookup"><span data-stu-id="ff79b-122">String.</span></span> <span data-ttu-id="ff79b-123">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="ff79b-123">The value to search for.</span></span>|  
|<span data-ttu-id="ff79b-124">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ff79b-124">x509FindType</span></span>|<span data-ttu-id="ff79b-125">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff79b-125">Enumeration.</span></span> <span data-ttu-id="ff79b-126">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ff79b-126">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="ff79b-127">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ff79b-127">storeLocation</span></span>|<span data-ttu-id="ff79b-128">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff79b-128">Enumeration.</span></span> <span data-ttu-id="ff79b-129">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ff79b-129">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="ff79b-130">storeName</span><span class="sxs-lookup"><span data-stu-id="ff79b-130">storeName</span></span>|<span data-ttu-id="ff79b-131">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff79b-131">Enumeration.</span></span> <span data-ttu-id="ff79b-132">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="ff79b-132">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ff79b-133">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="ff79b-133">findValue Attribute</span></span>  
  
|<span data-ttu-id="ff79b-134">Valor</span><span class="sxs-lookup"><span data-stu-id="ff79b-134">Value</span></span>|<span data-ttu-id="ff79b-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff79b-136">String</span><span class="sxs-lookup"><span data-stu-id="ff79b-136">String</span></span>|<span data-ttu-id="ff79b-137">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="ff79b-137">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ff79b-138">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="ff79b-138">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ff79b-139">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="ff79b-139">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ff79b-140">Valor</span><span class="sxs-lookup"><span data-stu-id="ff79b-140">Value</span></span>|<span data-ttu-id="ff79b-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff79b-142">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ff79b-142">Enumeration</span></span>|<span data-ttu-id="ff79b-143">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="ff79b-143">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ff79b-144">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="ff79b-144">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ff79b-145">Valor</span><span class="sxs-lookup"><span data-stu-id="ff79b-145">Value</span></span>|<span data-ttu-id="ff79b-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff79b-147">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ff79b-147">Enumeration</span></span>|<span data-ttu-id="ff79b-148">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ff79b-148">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ff79b-149">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="ff79b-149">storeName Attribute</span></span>  
  
|<span data-ttu-id="ff79b-150">Valor</span><span class="sxs-lookup"><span data-stu-id="ff79b-150">Value</span></span>|<span data-ttu-id="ff79b-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ff79b-152">Enumeración</span><span class="sxs-lookup"><span data-stu-id="ff79b-152">Enumeration</span></span>|<span data-ttu-id="ff79b-153">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="ff79b-153">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff79b-154">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ff79b-154">Child Elements</span></span>  
 <span data-ttu-id="ff79b-155">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ff79b-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff79b-156">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ff79b-156">Parent Elements</span></span>  
  
|<span data-ttu-id="ff79b-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="ff79b-157">Element</span></span>|<span data-ttu-id="ff79b-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff79b-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff79b-159">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="ff79b-159">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="ff79b-160">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="ff79b-160">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff79b-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff79b-161">Remarks</span></span>  
 <span data-ttu-id="ff79b-162">Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="ff79b-162">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="ff79b-163">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="ff79b-163">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="ff79b-164">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="ff79b-164">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="ff79b-165">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ff79b-165">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="ff79b-166">Para obtener más información, vea la sección "Certificados con ámbito" de [Cómo: Crear un cliente federado](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="ff79b-166">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff79b-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff79b-167">Example</span></span>  
 <span data-ttu-id="ff79b-168">En el ejemplo siguiente se agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="ff79b-168">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff79b-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff79b-169">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="ff79b-170">Cómo: Crear a un cliente federado</span><span class="sxs-lookup"><span data-stu-id="ff79b-170">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ff79b-171">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="ff79b-171">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="ff79b-172">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="ff79b-172">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="ff79b-173">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ff79b-173">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

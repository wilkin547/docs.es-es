---
title: Elemento &lt;defaultCertificate&gt;
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: a4af1c6ec452b24634fa50162fa71f069e2451f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="5a351-102">Elemento &lt;defaultCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="5a351-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="5a351-103">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="5a351-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="5a351-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5a351-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5a351-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5a351-105">\<behaviors></span></span>  
<span data-ttu-id="5a351-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="5a351-106">endpointBehaviors section</span></span>  
<span data-ttu-id="5a351-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5a351-107">\<behavior></span></span>  
<span data-ttu-id="5a351-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="5a351-108">\<clientCredentials></span></span>  
<span data-ttu-id="5a351-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="5a351-109">\<serviceCertificate></span></span>  
<span data-ttu-id="5a351-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="5a351-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a351-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a351-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"   
storeLocation=" CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"   
x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a351-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a351-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5a351-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a351-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a351-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a351-114">Attributes</span></span>  
  
|<span data-ttu-id="5a351-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="5a351-115">Attribute</span></span>|<span data-ttu-id="5a351-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a351-117">findValue</span><span class="sxs-lookup"><span data-stu-id="5a351-117">findValue</span></span>|<span data-ttu-id="5a351-118">Cadena.</span><span class="sxs-lookup"><span data-stu-id="5a351-118">String.</span></span> <span data-ttu-id="5a351-119">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="5a351-119">The value to search for.</span></span>|  
|<span data-ttu-id="5a351-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="5a351-120">x509FindType</span></span>|<span data-ttu-id="5a351-121">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5a351-121">Enumeration.</span></span> <span data-ttu-id="5a351-122">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5a351-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="5a351-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="5a351-123">storeLocation</span></span>|<span data-ttu-id="5a351-124">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5a351-124">Enumeration.</span></span> <span data-ttu-id="5a351-125">Una de las dos ubicaciones de almacén de sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5a351-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="5a351-126">storeName</span><span class="sxs-lookup"><span data-stu-id="5a351-126">storeName</span></span>|<span data-ttu-id="5a351-127">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="5a351-127">Enumeration.</span></span> <span data-ttu-id="5a351-128">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="5a351-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="5a351-129">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="5a351-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="5a351-130">Valor</span><span class="sxs-lookup"><span data-stu-id="5a351-130">Value</span></span>|<span data-ttu-id="5a351-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a351-132">String</span><span class="sxs-lookup"><span data-stu-id="5a351-132">String</span></span>|<span data-ttu-id="5a351-133">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="5a351-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="5a351-134">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="5a351-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="5a351-135">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="5a351-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="5a351-136">Valor</span><span class="sxs-lookup"><span data-stu-id="5a351-136">Value</span></span>|<span data-ttu-id="5a351-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a351-138">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5a351-138">Enumeration</span></span>|<span data-ttu-id="5a351-139">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="5a351-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="5a351-140">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="5a351-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="5a351-141">Valor</span><span class="sxs-lookup"><span data-stu-id="5a351-141">Value</span></span>|<span data-ttu-id="5a351-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a351-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5a351-143">Enumeration</span></span>|<span data-ttu-id="5a351-144">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="5a351-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="5a351-145">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="5a351-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="5a351-146">Valor</span><span class="sxs-lookup"><span data-stu-id="5a351-146">Value</span></span>|<span data-ttu-id="5a351-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a351-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="5a351-148">Enumeration</span></span>|<span data-ttu-id="5a351-149">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="5a351-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a351-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a351-150">Child Elements</span></span>  
 <span data-ttu-id="5a351-151">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5a351-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a351-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a351-152">Parent Elements</span></span>  
  
|<span data-ttu-id="5a351-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a351-153">Element</span></span>|<span data-ttu-id="5a351-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a351-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a351-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="5a351-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="5a351-156">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="5a351-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a351-157">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a351-157">Remarks</span></span>  
 <span data-ttu-id="5a351-158">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="5a351-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="5a351-159">Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="5a351-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a351-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a351-160">Example</span></span>  
 <span data-ttu-id="5a351-161">En el ejemplo siguiente se especifica un certificado que se usará para los extremos cuyo URI comienza con http://www.contoso.com y un certificado que se utilizará para todos los demás extremos que no realizan la negociación del certificado.</span><span class="sxs-lookup"><span data-stu-id="5a351-161">The following example specifies a certificate to use for endpoints whose URI begins with http://www.contoso.com and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a351-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a351-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="5a351-163">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="5a351-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="5a351-164">\<autenticación ></span><span class="sxs-lookup"><span data-stu-id="5a351-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="5a351-165">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="5a351-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="5a351-166">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5a351-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

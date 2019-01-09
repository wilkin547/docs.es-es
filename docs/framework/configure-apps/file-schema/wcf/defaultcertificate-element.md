---
title: Elemento &lt;defaultCertificate&gt;
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 2f6167d7b30da753d093a87753eeef3374fcc0f0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146997"
---
# <a name="ltdefaultcertificategt-element"></a><span data-ttu-id="d471c-102">Elemento &lt;defaultCertificate&gt;</span><span class="sxs-lookup"><span data-stu-id="d471c-102">&lt;defaultCertificate&gt; Element</span></span>
<span data-ttu-id="d471c-103">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="d471c-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="d471c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d471c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d471c-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="d471c-105">\<behaviors></span></span>  
<span data-ttu-id="d471c-106">sección endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="d471c-106">endpointBehaviors section</span></span>  
<span data-ttu-id="d471c-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="d471c-107">\<behavior></span></span>  
<span data-ttu-id="d471c-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="d471c-108">\<clientCredentials></span></span>  
<span data-ttu-id="d471c-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d471c-109">\<serviceCertificate></span></span>  
<span data-ttu-id="d471c-110">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="d471c-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d471c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d471c-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d471c-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d471c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d471c-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d471c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d471c-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d471c-114">Attributes</span></span>  
  
|<span data-ttu-id="d471c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d471c-115">Attribute</span></span>|<span data-ttu-id="d471c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d471c-117">findValue</span><span class="sxs-lookup"><span data-stu-id="d471c-117">findValue</span></span>|<span data-ttu-id="d471c-118">Cadena.</span><span class="sxs-lookup"><span data-stu-id="d471c-118">String.</span></span> <span data-ttu-id="d471c-119">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="d471c-119">The value to search for.</span></span>|  
|<span data-ttu-id="d471c-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d471c-120">x509FindType</span></span>|<span data-ttu-id="d471c-121">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d471c-121">Enumeration.</span></span> <span data-ttu-id="d471c-122">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d471c-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="d471c-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d471c-123">storeLocation</span></span>|<span data-ttu-id="d471c-124">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d471c-124">Enumeration.</span></span> <span data-ttu-id="d471c-125">Una de las dos ubicaciones de almacén de sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d471c-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="d471c-126">storeName</span><span class="sxs-lookup"><span data-stu-id="d471c-126">storeName</span></span>|<span data-ttu-id="d471c-127">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d471c-127">Enumeration.</span></span> <span data-ttu-id="d471c-128">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d471c-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d471c-129">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="d471c-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="d471c-130">Valor</span><span class="sxs-lookup"><span data-stu-id="d471c-130">Value</span></span>|<span data-ttu-id="d471c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d471c-132">String</span><span class="sxs-lookup"><span data-stu-id="d471c-132">String</span></span>|<span data-ttu-id="d471c-133">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="d471c-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d471c-134">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="d471c-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d471c-135">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="d471c-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d471c-136">Valor</span><span class="sxs-lookup"><span data-stu-id="d471c-136">Value</span></span>|<span data-ttu-id="d471c-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d471c-138">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d471c-138">Enumeration</span></span>|<span data-ttu-id="d471c-139">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="d471c-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d471c-140">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="d471c-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d471c-141">Valor</span><span class="sxs-lookup"><span data-stu-id="d471c-141">Value</span></span>|<span data-ttu-id="d471c-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d471c-143">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d471c-143">Enumeration</span></span>|<span data-ttu-id="d471c-144">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d471c-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d471c-145">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="d471c-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="d471c-146">Valor</span><span class="sxs-lookup"><span data-stu-id="d471c-146">Value</span></span>|<span data-ttu-id="d471c-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d471c-148">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d471c-148">Enumeration</span></span>|<span data-ttu-id="d471c-149">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="d471c-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d471c-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d471c-150">Child Elements</span></span>  
 <span data-ttu-id="d471c-151">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d471c-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d471c-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d471c-152">Parent Elements</span></span>  
  
|<span data-ttu-id="d471c-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="d471c-153">Element</span></span>|<span data-ttu-id="d471c-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="d471c-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d471c-155">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="d471c-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="d471c-156">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="d471c-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d471c-157">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d471c-157">Remarks</span></span>  
 <span data-ttu-id="d471c-158">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="d471c-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="d471c-159">Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="d471c-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d471c-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d471c-160">Example</span></span>  
 <span data-ttu-id="d471c-161">En el ejemplo siguiente se especifica un certificado que se usará para los extremos cuyo URI comienza con `http://www.contoso.com` y un certificado que se usará para todos los demás extremos que no realizan la negociación de certificado.</span><span class="sxs-lookup"><span data-stu-id="d471c-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="d471c-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="d471c-162">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>  
 [<span data-ttu-id="d471c-163">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="d471c-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="d471c-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d471c-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="d471c-165">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d471c-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="d471c-166">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d471c-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

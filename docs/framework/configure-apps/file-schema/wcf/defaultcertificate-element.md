---
title: <defaultCertificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400426"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="fc348-102">\<defaultCertificate >, elemento</span><span class="sxs-lookup"><span data-stu-id="fc348-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="fc348-103">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="fc348-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="fc348-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc348-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fc348-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="fc348-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="fc348-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="fc348-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="fc348-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceCertificate**](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc348-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="fc348-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> defaultCertificate**</span><span class="sxs-lookup"><span data-stu-id="fc348-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc348-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc348-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc348-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc348-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc348-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc348-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc348-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc348-115">Attributes</span></span>  
  
|<span data-ttu-id="fc348-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc348-116">Attribute</span></span>|<span data-ttu-id="fc348-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc348-118">findValue</span><span class="sxs-lookup"><span data-stu-id="fc348-118">findValue</span></span>|<span data-ttu-id="fc348-119">Cadena.</span><span class="sxs-lookup"><span data-stu-id="fc348-119">String.</span></span> <span data-ttu-id="fc348-120">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="fc348-120">The value to search for.</span></span>|  
|<span data-ttu-id="fc348-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="fc348-121">x509FindType</span></span>|<span data-ttu-id="fc348-122">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="fc348-122">Enumeration.</span></span> <span data-ttu-id="fc348-123">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="fc348-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="fc348-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="fc348-124">storeLocation</span></span>|<span data-ttu-id="fc348-125">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="fc348-125">Enumeration.</span></span> <span data-ttu-id="fc348-126">Una de las dos ubicaciones de almacén de sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="fc348-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="fc348-127">storeName</span><span class="sxs-lookup"><span data-stu-id="fc348-127">storeName</span></span>|<span data-ttu-id="fc348-128">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="fc348-128">Enumeration.</span></span> <span data-ttu-id="fc348-129">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="fc348-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="fc348-130">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="fc348-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="fc348-131">Valor</span><span class="sxs-lookup"><span data-stu-id="fc348-131">Value</span></span>|<span data-ttu-id="fc348-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc348-133">string</span><span class="sxs-lookup"><span data-stu-id="fc348-133">String</span></span>|<span data-ttu-id="fc348-134">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="fc348-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="fc348-135">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="fc348-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="fc348-136">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="fc348-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="fc348-137">Value</span><span class="sxs-lookup"><span data-stu-id="fc348-137">Value</span></span>|<span data-ttu-id="fc348-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc348-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fc348-139">Enumeration</span></span>|<span data-ttu-id="fc348-140">Estos valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName , FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="fc348-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="fc348-141">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="fc348-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="fc348-142">Valor</span><span class="sxs-lookup"><span data-stu-id="fc348-142">Value</span></span>|<span data-ttu-id="fc348-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc348-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fc348-144">Enumeration</span></span>|<span data-ttu-id="fc348-145">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="fc348-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="fc348-146">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="fc348-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="fc348-147">Valor</span><span class="sxs-lookup"><span data-stu-id="fc348-147">Value</span></span>|<span data-ttu-id="fc348-148">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fc348-149">Enumeración</span><span class="sxs-lookup"><span data-stu-id="fc348-149">Enumeration</span></span>|<span data-ttu-id="fc348-150">Estos valores incluyen: AddressBook, AuthRoot, CertificateAuthority, no permitido, My, root, TrustedPeople y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="fc348-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc348-151">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc348-151">Child Elements</span></span>  
 <span data-ttu-id="fc348-152">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc348-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc348-153">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc348-153">Parent Elements</span></span>  
  
|<span data-ttu-id="fc348-154">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc348-154">Element</span></span>|<span data-ttu-id="fc348-155">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc348-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc348-156">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="fc348-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="fc348-157">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="fc348-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc348-158">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc348-158">Remarks</span></span>  
 <span data-ttu-id="fc348-159">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="fc348-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="fc348-160">Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="fc348-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc348-161">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc348-161">Example</span></span>  
 <span data-ttu-id="fc348-162">En el ejemplo siguiente se especifica un certificado que se va a usar para los `http://www.contoso.com` puntos de conexión cuyo URI comienza con y un certificado que se va a usar para todos los demás extremos que no realizan la negociación de certificados.</span><span class="sxs-lookup"><span data-stu-id="fc348-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc348-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc348-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="fc348-164">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="fc348-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="fc348-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="fc348-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="fc348-166">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="fc348-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="fc348-167">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fc348-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

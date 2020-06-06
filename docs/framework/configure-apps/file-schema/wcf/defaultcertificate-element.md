---
title: <defaultCertificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400426"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="705d6-102">\<defaultCertificate> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="705d6-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="705d6-103">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="705d6-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="705d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="705d6-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="705d6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="705d6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="705d6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="705d6-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="705d6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="705d6-107">Attributes</span></span>  
  
|<span data-ttu-id="705d6-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="705d6-108">Attribute</span></span>|<span data-ttu-id="705d6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="705d6-110">findValue</span><span class="sxs-lookup"><span data-stu-id="705d6-110">findValue</span></span>|<span data-ttu-id="705d6-111">String.</span><span class="sxs-lookup"><span data-stu-id="705d6-111">String.</span></span> <span data-ttu-id="705d6-112">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="705d6-112">The value to search for.</span></span>|  
|<span data-ttu-id="705d6-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="705d6-113">x509FindType</span></span>|<span data-ttu-id="705d6-114">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="705d6-114">Enumeration.</span></span> <span data-ttu-id="705d6-115">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="705d6-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="705d6-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="705d6-116">storeLocation</span></span>|<span data-ttu-id="705d6-117">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="705d6-117">Enumeration.</span></span> <span data-ttu-id="705d6-118">Una de las dos ubicaciones de almacén de sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="705d6-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="705d6-119">storeName</span><span class="sxs-lookup"><span data-stu-id="705d6-119">storeName</span></span>|<span data-ttu-id="705d6-120">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="705d6-120">Enumeration.</span></span> <span data-ttu-id="705d6-121">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="705d6-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="705d6-122">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="705d6-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="705d6-123">Value</span><span class="sxs-lookup"><span data-stu-id="705d6-123">Value</span></span>|<span data-ttu-id="705d6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="705d6-125">String</span><span class="sxs-lookup"><span data-stu-id="705d6-125">String</span></span>|<span data-ttu-id="705d6-126">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="705d6-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="705d6-127">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="705d6-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="705d6-128">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="705d6-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="705d6-129">Value</span><span class="sxs-lookup"><span data-stu-id="705d6-129">Value</span></span>|<span data-ttu-id="705d6-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="705d6-131">Enumeración</span><span class="sxs-lookup"><span data-stu-id="705d6-131">Enumeration</span></span>|<span data-ttu-id="705d6-132">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="705d6-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="705d6-133">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="705d6-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="705d6-134">Value</span><span class="sxs-lookup"><span data-stu-id="705d6-134">Value</span></span>|<span data-ttu-id="705d6-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="705d6-136">Enumeración</span><span class="sxs-lookup"><span data-stu-id="705d6-136">Enumeration</span></span>|<span data-ttu-id="705d6-137">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="705d6-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="705d6-138">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="705d6-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="705d6-139">Value</span><span class="sxs-lookup"><span data-stu-id="705d6-139">Value</span></span>|<span data-ttu-id="705d6-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="705d6-141">Enumeración</span><span class="sxs-lookup"><span data-stu-id="705d6-141">Enumeration</span></span>|<span data-ttu-id="705d6-142">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="705d6-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="705d6-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="705d6-143">Child Elements</span></span>  
 <span data-ttu-id="705d6-144">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="705d6-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="705d6-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="705d6-145">Parent Elements</span></span>  
  
|<span data-ttu-id="705d6-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="705d6-146">Element</span></span>|<span data-ttu-id="705d6-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="705d6-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="705d6-148">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="705d6-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="705d6-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="705d6-149">Remarks</span></span>  
 <span data-ttu-id="705d6-150">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="705d6-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="705d6-151">Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="705d6-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="705d6-152">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="705d6-152">Example</span></span>  
 <span data-ttu-id="705d6-153">En el ejemplo siguiente se especifica un certificado que se va a usar para los puntos de conexión cuyo URI comienza con `http://www.contoso.com` y un certificado que se va a usar para todos los demás extremos que no realizan la negociación de certificados.</span><span class="sxs-lookup"><span data-stu-id="705d6-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="705d6-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="705d6-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="705d6-155">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="705d6-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="705d6-156">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="705d6-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="705d6-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="705d6-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

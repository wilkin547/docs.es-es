---
description: 'Más información acerca de: <defaultCertificate> elemento'
title: <defaultCertificate> (Elemento)
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 580236e521e91c8b475586f6c6378630960f233c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803924"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="70eed-103">\<defaultCertificate> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="70eed-103">\<defaultCertificate> Element</span></span>

<span data-ttu-id="70eed-104">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="70eed-104">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="70eed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70eed-105">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70eed-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70eed-106">Attributes and Elements</span></span>  

 <span data-ttu-id="70eed-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70eed-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70eed-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="70eed-108">Attributes</span></span>  
  
|<span data-ttu-id="70eed-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="70eed-109">Attribute</span></span>|<span data-ttu-id="70eed-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70eed-111">findValue</span><span class="sxs-lookup"><span data-stu-id="70eed-111">findValue</span></span>|<span data-ttu-id="70eed-112">String.</span><span class="sxs-lookup"><span data-stu-id="70eed-112">String.</span></span> <span data-ttu-id="70eed-113">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="70eed-113">The value to search for.</span></span>|  
|<span data-ttu-id="70eed-114">x509FindType</span><span class="sxs-lookup"><span data-stu-id="70eed-114">x509FindType</span></span>|<span data-ttu-id="70eed-115">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="70eed-115">Enumeration.</span></span> <span data-ttu-id="70eed-116">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="70eed-116">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="70eed-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="70eed-117">storeLocation</span></span>|<span data-ttu-id="70eed-118">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="70eed-118">Enumeration.</span></span> <span data-ttu-id="70eed-119">Una de las dos ubicaciones de almacén de sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="70eed-119">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="70eed-120">storeName</span><span class="sxs-lookup"><span data-stu-id="70eed-120">storeName</span></span>|<span data-ttu-id="70eed-121">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="70eed-121">Enumeration.</span></span> <span data-ttu-id="70eed-122">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="70eed-122">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="70eed-123">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="70eed-123">findValue Attribute</span></span>  
  
|<span data-ttu-id="70eed-124">Value</span><span class="sxs-lookup"><span data-stu-id="70eed-124">Value</span></span>|<span data-ttu-id="70eed-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-125">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70eed-126">String</span><span class="sxs-lookup"><span data-stu-id="70eed-126">String</span></span>|<span data-ttu-id="70eed-127">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="70eed-127">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="70eed-128">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="70eed-128">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="70eed-129">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="70eed-129">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="70eed-130">Value</span><span class="sxs-lookup"><span data-stu-id="70eed-130">Value</span></span>|<span data-ttu-id="70eed-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70eed-132">Enumeración</span><span class="sxs-lookup"><span data-stu-id="70eed-132">Enumeration</span></span>|<span data-ttu-id="70eed-133">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="70eed-133">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="70eed-134">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="70eed-134">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="70eed-135">Value</span><span class="sxs-lookup"><span data-stu-id="70eed-135">Value</span></span>|<span data-ttu-id="70eed-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70eed-137">Enumeración</span><span class="sxs-lookup"><span data-stu-id="70eed-137">Enumeration</span></span>|<span data-ttu-id="70eed-138">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="70eed-138">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="70eed-139">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="70eed-139">storeName Attribute</span></span>  
  
|<span data-ttu-id="70eed-140">Value</span><span class="sxs-lookup"><span data-stu-id="70eed-140">Value</span></span>|<span data-ttu-id="70eed-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-141">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70eed-142">Enumeración</span><span class="sxs-lookup"><span data-stu-id="70eed-142">Enumeration</span></span>|<span data-ttu-id="70eed-143">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="70eed-143">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70eed-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70eed-144">Child Elements</span></span>  

 <span data-ttu-id="70eed-145">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="70eed-145">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70eed-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70eed-146">Parent Elements</span></span>  
  
|<span data-ttu-id="70eed-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="70eed-147">Element</span></span>|<span data-ttu-id="70eed-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="70eed-148">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="70eed-149">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="70eed-149">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70eed-150">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70eed-150">Remarks</span></span>  

 <span data-ttu-id="70eed-151">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, el certificado especificado por este elemento de configuración se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="70eed-151">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="70eed-152">Almacena un certificado único que se va a utilizar cuando un servicio no especifica ningún certificado.</span><span class="sxs-lookup"><span data-stu-id="70eed-152">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70eed-153">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70eed-153">Example</span></span>  

 <span data-ttu-id="70eed-154">En el ejemplo siguiente se especifica un certificado que se va a usar para los puntos de conexión cuyo URI comienza con `http://www.contoso.com` y un certificado que se va a usar para todos los demás extremos que no realizan la negociación de certificados.</span><span class="sxs-lookup"><span data-stu-id="70eed-154">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70eed-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="70eed-155">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="70eed-156">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="70eed-156">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="70eed-157">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="70eed-157">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="70eed-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="70eed-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <add> del <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 28777ecac130295a8ba82a8e4d67cc519d088d8a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195147"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="d13b2-102">\<add> del \<scopedCertificates> elemento</span><span class="sxs-lookup"><span data-stu-id="d13b2-102">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="d13b2-103">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="d13b2-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="d13b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d13b2-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d13b2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d13b2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="d13b2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d13b2-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d13b2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d13b2-107">Attributes</span></span>  
  
|<span data-ttu-id="d13b2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d13b2-108">Attribute</span></span>|<span data-ttu-id="d13b2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d13b2-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="d13b2-110">targetUri</span></span>|<span data-ttu-id="d13b2-111">Cadena</span><span class="sxs-lookup"><span data-stu-id="d13b2-111">String.</span></span> <span data-ttu-id="d13b2-112">Especifica el URI del servicio asociado al certificado.</span><span class="sxs-lookup"><span data-stu-id="d13b2-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="d13b2-113">findValue</span><span class="sxs-lookup"><span data-stu-id="d13b2-113">findValue</span></span>|<span data-ttu-id="d13b2-114">Cadena</span><span class="sxs-lookup"><span data-stu-id="d13b2-114">String.</span></span> <span data-ttu-id="d13b2-115">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="d13b2-115">The value to search for.</span></span>|  
|<span data-ttu-id="d13b2-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="d13b2-116">x509FindType</span></span>|<span data-ttu-id="d13b2-117">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d13b2-117">Enumeration.</span></span> <span data-ttu-id="d13b2-118">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d13b2-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="d13b2-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="d13b2-119">storeLocation</span></span>|<span data-ttu-id="d13b2-120">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d13b2-120">Enumeration.</span></span> <span data-ttu-id="d13b2-121">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d13b2-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="d13b2-122">storeName</span><span class="sxs-lookup"><span data-stu-id="d13b2-122">storeName</span></span>|<span data-ttu-id="d13b2-123">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="d13b2-123">Enumeration.</span></span> <span data-ttu-id="d13b2-124">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="d13b2-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="d13b2-125">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="d13b2-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="d13b2-126">Value</span><span class="sxs-lookup"><span data-stu-id="d13b2-126">Value</span></span>|<span data-ttu-id="d13b2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d13b2-128">String</span><span class="sxs-lookup"><span data-stu-id="d13b2-128">String</span></span>|<span data-ttu-id="d13b2-129">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="d13b2-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="d13b2-130">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="d13b2-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="d13b2-131">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="d13b2-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="d13b2-132">Value</span><span class="sxs-lookup"><span data-stu-id="d13b2-132">Value</span></span>|<span data-ttu-id="d13b2-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d13b2-134">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d13b2-134">Enumeration</span></span>|<span data-ttu-id="d13b2-135">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="d13b2-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="d13b2-136">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="d13b2-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="d13b2-137">Value</span><span class="sxs-lookup"><span data-stu-id="d13b2-137">Value</span></span>|<span data-ttu-id="d13b2-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d13b2-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d13b2-139">Enumeration</span></span>|<span data-ttu-id="d13b2-140">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="d13b2-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="d13b2-141">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="d13b2-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="d13b2-142">Value</span><span class="sxs-lookup"><span data-stu-id="d13b2-142">Value</span></span>|<span data-ttu-id="d13b2-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d13b2-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="d13b2-144">Enumeration</span></span>|<span data-ttu-id="d13b2-145">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="d13b2-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d13b2-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d13b2-146">Child Elements</span></span>  

 <span data-ttu-id="d13b2-147">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d13b2-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d13b2-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d13b2-148">Parent Elements</span></span>  
  
|<span data-ttu-id="d13b2-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="d13b2-149">Element</span></span>|<span data-ttu-id="d13b2-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="d13b2-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="d13b2-151">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="d13b2-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d13b2-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d13b2-152">Remarks</span></span>  

 <span data-ttu-id="d13b2-153">Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="d13b2-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="d13b2-154">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="d13b2-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="d13b2-155">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="d13b2-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="d13b2-156">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d13b2-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="d13b2-157">Para obtener más información, consulte la sección "certificados con ámbito" de [Cómo: crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="d13b2-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13b2-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d13b2-158">Example</span></span>  

 <span data-ttu-id="d13b2-159">En el ejemplo siguiente se agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="d13b2-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d13b2-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d13b2-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="d13b2-161">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="d13b2-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d13b2-162">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="d13b2-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d13b2-163">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d13b2-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d13b2-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d13b2-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

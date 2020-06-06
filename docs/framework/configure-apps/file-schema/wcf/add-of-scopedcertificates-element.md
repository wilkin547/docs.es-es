---
title: <add>del <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398342"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="63b5a-102">\<add>del \<scopedCertificates> elemento</span><span class="sxs-lookup"><span data-stu-id="63b5a-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="63b5a-103">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="63b5a-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="63b5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63b5a-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63b5a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63b5a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="63b5a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63b5a-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63b5a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="63b5a-107">Attributes</span></span>  
  
|<span data-ttu-id="63b5a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="63b5a-108">Attribute</span></span>|<span data-ttu-id="63b5a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63b5a-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="63b5a-110">targetUri</span></span>|<span data-ttu-id="63b5a-111">String.</span><span class="sxs-lookup"><span data-stu-id="63b5a-111">String.</span></span> <span data-ttu-id="63b5a-112">Especifica el URI del servicio asociado al certificado.</span><span class="sxs-lookup"><span data-stu-id="63b5a-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="63b5a-113">findValue</span><span class="sxs-lookup"><span data-stu-id="63b5a-113">findValue</span></span>|<span data-ttu-id="63b5a-114">String.</span><span class="sxs-lookup"><span data-stu-id="63b5a-114">String.</span></span> <span data-ttu-id="63b5a-115">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="63b5a-115">The value to search for.</span></span>|  
|<span data-ttu-id="63b5a-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="63b5a-116">x509FindType</span></span>|<span data-ttu-id="63b5a-117">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="63b5a-117">Enumeration.</span></span> <span data-ttu-id="63b5a-118">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="63b5a-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="63b5a-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="63b5a-119">storeLocation</span></span>|<span data-ttu-id="63b5a-120">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="63b5a-120">Enumeration.</span></span> <span data-ttu-id="63b5a-121">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="63b5a-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="63b5a-122">storeName</span><span class="sxs-lookup"><span data-stu-id="63b5a-122">storeName</span></span>|<span data-ttu-id="63b5a-123">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="63b5a-123">Enumeration.</span></span> <span data-ttu-id="63b5a-124">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="63b5a-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="63b5a-125">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="63b5a-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="63b5a-126">Value</span><span class="sxs-lookup"><span data-stu-id="63b5a-126">Value</span></span>|<span data-ttu-id="63b5a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="63b5a-128">String</span><span class="sxs-lookup"><span data-stu-id="63b5a-128">String</span></span>|<span data-ttu-id="63b5a-129">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="63b5a-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="63b5a-130">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="63b5a-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="63b5a-131">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="63b5a-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="63b5a-132">Value</span><span class="sxs-lookup"><span data-stu-id="63b5a-132">Value</span></span>|<span data-ttu-id="63b5a-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="63b5a-134">Enumeración</span><span class="sxs-lookup"><span data-stu-id="63b5a-134">Enumeration</span></span>|<span data-ttu-id="63b5a-135">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="63b5a-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="63b5a-136">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="63b5a-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="63b5a-137">Value</span><span class="sxs-lookup"><span data-stu-id="63b5a-137">Value</span></span>|<span data-ttu-id="63b5a-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="63b5a-139">Enumeración</span><span class="sxs-lookup"><span data-stu-id="63b5a-139">Enumeration</span></span>|<span data-ttu-id="63b5a-140">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="63b5a-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="63b5a-141">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="63b5a-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="63b5a-142">Value</span><span class="sxs-lookup"><span data-stu-id="63b5a-142">Value</span></span>|<span data-ttu-id="63b5a-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="63b5a-144">Enumeración</span><span class="sxs-lookup"><span data-stu-id="63b5a-144">Enumeration</span></span>|<span data-ttu-id="63b5a-145">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="63b5a-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63b5a-146">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63b5a-146">Child Elements</span></span>  
 <span data-ttu-id="63b5a-147">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63b5a-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63b5a-148">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63b5a-148">Parent Elements</span></span>  
  
|<span data-ttu-id="63b5a-149">Elemento</span><span class="sxs-lookup"><span data-stu-id="63b5a-149">Element</span></span>|<span data-ttu-id="63b5a-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="63b5a-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="63b5a-151">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="63b5a-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63b5a-152">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63b5a-152">Remarks</span></span>  
 <span data-ttu-id="63b5a-153">Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="63b5a-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="63b5a-154">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="63b5a-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="63b5a-155">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="63b5a-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="63b5a-156">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="63b5a-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="63b5a-157">Para obtener más información, consulte la sección "certificados con ámbito" de [Cómo: crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="63b5a-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63b5a-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63b5a-158">Example</span></span>  
 <span data-ttu-id="63b5a-159">En el ejemplo siguiente se agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="63b5a-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63b5a-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63b5a-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="63b5a-161">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="63b5a-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="63b5a-162">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="63b5a-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="63b5a-163">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="63b5a-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="63b5a-164">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="63b5a-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

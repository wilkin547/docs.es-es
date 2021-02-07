---
description: 'Más información sobre: <add> del <scopedCertificates> elemento'
title: <add> del <scopedCertificates> elemento
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: 4c267164ccf065edee79a6aaaa9aaddc14d95909
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750278"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="68bf8-103">\<add> del \<scopedCertificates> elemento</span><span class="sxs-lookup"><span data-stu-id="68bf8-103">\<add> of \<scopedCertificates> Element</span></span>

<span data-ttu-id="68bf8-104">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="68bf8-104">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="68bf8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68bf8-105">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68bf8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68bf8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="68bf8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68bf8-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68bf8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="68bf8-108">Attributes</span></span>  
  
|<span data-ttu-id="68bf8-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="68bf8-109">Attribute</span></span>|<span data-ttu-id="68bf8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68bf8-111">targetUri</span><span class="sxs-lookup"><span data-stu-id="68bf8-111">targetUri</span></span>|<span data-ttu-id="68bf8-112">String.</span><span class="sxs-lookup"><span data-stu-id="68bf8-112">String.</span></span> <span data-ttu-id="68bf8-113">Especifica el URI del servicio asociado al certificado.</span><span class="sxs-lookup"><span data-stu-id="68bf8-113">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="68bf8-114">findValue</span><span class="sxs-lookup"><span data-stu-id="68bf8-114">findValue</span></span>|<span data-ttu-id="68bf8-115">String.</span><span class="sxs-lookup"><span data-stu-id="68bf8-115">String.</span></span> <span data-ttu-id="68bf8-116">Valor que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="68bf8-116">The value to search for.</span></span>|  
|<span data-ttu-id="68bf8-117">x509FindType</span><span class="sxs-lookup"><span data-stu-id="68bf8-117">x509FindType</span></span>|<span data-ttu-id="68bf8-118">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="68bf8-118">Enumeration.</span></span> <span data-ttu-id="68bf8-119">Uno de los campos de certificado en que buscar.</span><span class="sxs-lookup"><span data-stu-id="68bf8-119">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="68bf8-120">storeLocation</span><span class="sxs-lookup"><span data-stu-id="68bf8-120">storeLocation</span></span>|<span data-ttu-id="68bf8-121">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="68bf8-121">Enumeration.</span></span> <span data-ttu-id="68bf8-122">Una de las dos ubicaciones de almacén en que buscar.</span><span class="sxs-lookup"><span data-stu-id="68bf8-122">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="68bf8-123">storeName</span><span class="sxs-lookup"><span data-stu-id="68bf8-123">storeName</span></span>|<span data-ttu-id="68bf8-124">Enumeración.</span><span class="sxs-lookup"><span data-stu-id="68bf8-124">Enumeration.</span></span> <span data-ttu-id="68bf8-125">Uno de los almacenes del sistema en que buscar.</span><span class="sxs-lookup"><span data-stu-id="68bf8-125">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="68bf8-126">AtributofindValue</span><span class="sxs-lookup"><span data-stu-id="68bf8-126">findValue Attribute</span></span>  
  
|<span data-ttu-id="68bf8-127">Value</span><span class="sxs-lookup"><span data-stu-id="68bf8-127">Value</span></span>|<span data-ttu-id="68bf8-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68bf8-129">String</span><span class="sxs-lookup"><span data-stu-id="68bf8-129">String</span></span>|<span data-ttu-id="68bf8-130">El valor depende del campo (se especifica por el atributo X509FindType) en que se busca.</span><span class="sxs-lookup"><span data-stu-id="68bf8-130">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="68bf8-131">Por ejemplo, si se busca una huella digital, el valor debe ser una cadena de números hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="68bf8-131">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="68bf8-132">Atributo x509FindType</span><span class="sxs-lookup"><span data-stu-id="68bf8-132">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="68bf8-133">Value</span><span class="sxs-lookup"><span data-stu-id="68bf8-133">Value</span></span>|<span data-ttu-id="68bf8-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68bf8-135">Enumeración</span><span class="sxs-lookup"><span data-stu-id="68bf8-135">Enumeration</span></span>|<span data-ttu-id="68bf8-136">Los valores incluyen: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="68bf8-136">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="68bf8-137">Atributo storeLocation</span><span class="sxs-lookup"><span data-stu-id="68bf8-137">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="68bf8-138">Value</span><span class="sxs-lookup"><span data-stu-id="68bf8-138">Value</span></span>|<span data-ttu-id="68bf8-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68bf8-140">Enumeración</span><span class="sxs-lookup"><span data-stu-id="68bf8-140">Enumeration</span></span>|<span data-ttu-id="68bf8-141">CurrentUser o LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="68bf8-141">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="68bf8-142">Atributo storeName</span><span class="sxs-lookup"><span data-stu-id="68bf8-142">storeName Attribute</span></span>  
  
|<span data-ttu-id="68bf8-143">Value</span><span class="sxs-lookup"><span data-stu-id="68bf8-143">Value</span></span>|<span data-ttu-id="68bf8-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="68bf8-145">Enumeración</span><span class="sxs-lookup"><span data-stu-id="68bf8-145">Enumeration</span></span>|<span data-ttu-id="68bf8-146">Los valores incluyen: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, y TrustedPublisher.</span><span class="sxs-lookup"><span data-stu-id="68bf8-146">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68bf8-147">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68bf8-147">Child Elements</span></span>  

 <span data-ttu-id="68bf8-148">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68bf8-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68bf8-149">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68bf8-149">Parent Elements</span></span>  
  
|<span data-ttu-id="68bf8-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="68bf8-150">Element</span></span>|<span data-ttu-id="68bf8-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="68bf8-151">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="68bf8-152">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="68bf8-152">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68bf8-153">Observaciones</span><span class="sxs-lookup"><span data-stu-id="68bf8-153">Remarks</span></span>  

 <span data-ttu-id="68bf8-154">Este elemento permite al cliente configurar un certificado del servicio que se va a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="68bf8-154">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="68bf8-155">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="68bf8-155">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="68bf8-156">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="68bf8-156">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="68bf8-157">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="68bf8-157">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="68bf8-158">Para obtener más información, consulte la sección "certificados con ámbito" de [Cómo: crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="68bf8-158">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68bf8-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68bf8-159">Example</span></span>  

 <span data-ttu-id="68bf8-160">En el ejemplo siguiente se agrega un certificado X.509 a la colección.</span><span class="sxs-lookup"><span data-stu-id="68bf8-160">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="68bf8-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="68bf8-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="68bf8-162">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="68bf8-162">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="68bf8-163">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="68bf8-163">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="68bf8-164">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="68bf8-164">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="68bf8-165">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="68bf8-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

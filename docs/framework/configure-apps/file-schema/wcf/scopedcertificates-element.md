---
description: 'Más información acerca de: <scopedCertificates> elemento'
title: <scopedCertificates> (Elemento)
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 7aa108031831539396e8f737a214982655dd6bb1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683338"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="7387a-103">\<scopedCertificates> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="7387a-103">\<scopedCertificates> Element</span></span>

<span data-ttu-id="7387a-104">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="7387a-104">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="7387a-105">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="7387a-105">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="7387a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7387a-106">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7387a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7387a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="7387a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7387a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7387a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7387a-109">Attributes</span></span>  

 <span data-ttu-id="7387a-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7387a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7387a-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7387a-111">Child Elements</span></span>  
  
|<span data-ttu-id="7387a-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7387a-112">Element</span></span>|<span data-ttu-id="7387a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7387a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="7387a-114">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="7387a-114">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7387a-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7387a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="7387a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7387a-116">Element</span></span>|<span data-ttu-id="7387a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7387a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="7387a-118">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="7387a-118">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7387a-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7387a-119">Remarks</span></span>  

 <span data-ttu-id="7387a-120">Esta colección le permite al cliente configurar los certificados de servicio que se van a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="7387a-120">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="7387a-121">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="7387a-121">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="7387a-122">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="7387a-122">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="7387a-123">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7387a-123">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="7387a-124">Para obtener más información, consulte la sección "certificados con ámbito" de [Cómo: crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="7387a-124">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7387a-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7387a-125">Example</span></span>  

 <span data-ttu-id="7387a-126">En el ejemplo siguiente se especifica un certificado de servicio para que el cliente lo utilice al comunicarse con extremos cuyo nombre de dominio está `http://www.contoso.com` sobre el protocolo http.</span><span class="sxs-lookup"><span data-stu-id="7387a-126">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
```xml  
<serviceCertificate>
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="7387a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7387a-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="7387a-128">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="7387a-128">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7387a-129">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="7387a-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="7387a-130">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="7387a-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7387a-131">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7387a-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <scopedCertificates> (Elemento)
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: 4bee627fe186ed8dd85c118a37f59f575eb4650e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162262"
---
# <a name="scopedcertificates-element"></a><span data-ttu-id="f1e2f-102">\<scopedCertificates> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="f1e2f-102">\<scopedCertificates> Element</span></span>

<span data-ttu-id="f1e2f-103">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-103">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="f1e2f-104">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-104">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopedCertificates>**  
  
## <a name="syntax"></a><span data-ttu-id="f1e2f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1e2f-105">Syntax</span></span>  
  
```xml  
<scopedCertificates>
  <add findValue="String"
       storeLocation="CurrentUser/LocalMachine"
       storeName=" CurrentUser/LocalMachine"
       targetUri="string"
       x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
</scopedCertificates>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1e2f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f1e2f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f1e2f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1e2f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f1e2f-108">Attributes</span></span>  

 <span data-ttu-id="f1e2f-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1e2f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f1e2f-110">Child Elements</span></span>  
  
|<span data-ttu-id="f1e2f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1e2f-111">Element</span></span>|<span data-ttu-id="f1e2f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1e2f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-scopedcertificates-element.md)|<span data-ttu-id="f1e2f-113">Agrega un certificado X.509 a la colección de certificados con ámbito.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-113">Adds an X.509 certificate to the collection of scoped certificates.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1e2f-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f1e2f-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f1e2f-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1e2f-115">Element</span></span>|<span data-ttu-id="f1e2f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1e2f-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-servicecredentials.md)|<span data-ttu-id="f1e2f-117">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-117">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1e2f-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1e2f-118">Remarks</span></span>  

 <span data-ttu-id="f1e2f-119">Esta colección le permite al cliente configurar los certificados de servicio que se van a utilizar basándose en la dirección URL del servicio con el que se comunica.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-119">This collection enables the client to configure the service certificates to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="f1e2f-120">Esto es especialmente útil en escenarios del token emitidos donde un cliente puede estar comunicándose con varios servicios (el servicio final, así como los servicios del token de seguridad intermediarios).</span><span class="sxs-lookup"><span data-stu-id="f1e2f-120">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="f1e2f-121">Para los enlaces que utilizan la seguridad del mensaje basada en certificados, este certificado se utiliza para cifrar los mensajes del servicio y se espera que sea utilizado por el servicio para firmar las respuestas para el cliente.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-121">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="f1e2f-122">Si un enlace requiere un certificado para el servicio y no se encuentra ningún certificado concreto para la dirección URL del servicio en ScopedCertificates, se utilizará el certificado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-122">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="f1e2f-123">Para obtener más información, consulte la sección "certificados con ámbito" de [Cómo: crear un cliente federado](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span><span class="sxs-lookup"><span data-stu-id="f1e2f-123">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1e2f-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1e2f-124">Example</span></span>  

 <span data-ttu-id="f1e2f-125">En el ejemplo siguiente se especifica un certificado de servicio para que el cliente lo utilice al comunicarse con extremos cuyo nombre de dominio está `http://www.contoso.com` sobre el protocolo http.</span><span class="sxs-lookup"><span data-stu-id="f1e2f-125">The following example specifies a service certificate for the client to use when communicating with endpoints whose domain name is `http://www.contoso.com` over the HTTP protocol.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1e2f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1e2f-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="f1e2f-127">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="f1e2f-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f1e2f-128">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="f1e2f-128">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [\<add>](add-of-scopedcertificates-element.md)
- [<span data-ttu-id="f1e2f-129">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f1e2f-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f1e2f-130">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="f1e2f-130">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

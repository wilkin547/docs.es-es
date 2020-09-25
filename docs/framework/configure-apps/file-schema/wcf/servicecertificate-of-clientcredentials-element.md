---
title: <serviceCertificate> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 502452c664f2dcb0856f72e25ff8b1517f432919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172897"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="13276-102">\<serviceCertificate> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="13276-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="13276-103">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="13276-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="13276-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13276-104">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13276-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13276-105">Attributes and Elements</span></span>  

 <span data-ttu-id="13276-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13276-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13276-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="13276-107">Attributes</span></span>  

 <span data-ttu-id="13276-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13276-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13276-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13276-109">Child Elements</span></span>  
  
|<span data-ttu-id="13276-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="13276-110">Element</span></span>|<span data-ttu-id="13276-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="13276-111">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="13276-112">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="13276-112">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="13276-113">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="13276-113">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="13276-114">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="13276-114">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="13276-115">Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.</span><span class="sxs-lookup"><span data-stu-id="13276-115">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13276-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13276-116">Parent Elements</span></span>  
  
|<span data-ttu-id="13276-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="13276-117">Element</span></span>|<span data-ttu-id="13276-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="13276-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="13276-119">Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="13276-119">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13276-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13276-120">Remarks</span></span>  

 <span data-ttu-id="13276-121">Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL.</span><span class="sxs-lookup"><span data-stu-id="13276-121">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="13276-122">También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="13276-122">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="13276-123">Los atributos del `serviceCertificate` elemento son idénticos a los atributos de [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="13276-123">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13276-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13276-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="13276-125">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="13276-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="13276-126">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="13276-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="13276-127">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="13276-127">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="13276-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="13276-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

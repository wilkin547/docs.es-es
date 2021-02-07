---
description: 'Más información sobre: <serviceCertificate> del <clientCredentials> elemento'
title: <serviceCertificate> del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 5503c1a60b2d37f4f9359a2f49c019c37df71619
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682909"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="c1221-103">\<serviceCertificate> del \<clientCredentials> elemento</span><span class="sxs-lookup"><span data-stu-id="c1221-103">\<serviceCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="c1221-104">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="c1221-104">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="c1221-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1221-105">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1221-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1221-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c1221-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1221-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1221-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1221-108">Attributes</span></span>  

 <span data-ttu-id="c1221-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1221-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1221-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1221-110">Child Elements</span></span>  
  
|<span data-ttu-id="c1221-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1221-111">Element</span></span>|<span data-ttu-id="c1221-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1221-112">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultCertificate>](defaultcertificate-element.md)|<span data-ttu-id="c1221-113">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="c1221-113">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="c1221-114">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="c1221-114">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="c1221-115">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="c1221-115">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[\<authentication>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="c1221-116">Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.</span><span class="sxs-lookup"><span data-stu-id="c1221-116">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1221-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1221-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c1221-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1221-118">Element</span></span>|<span data-ttu-id="c1221-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1221-119">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="c1221-120">Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="c1221-120">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1221-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1221-121">Remarks</span></span>  

 <span data-ttu-id="c1221-122">Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL.</span><span class="sxs-lookup"><span data-stu-id="c1221-122">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="c1221-123">También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c1221-123">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="c1221-124">Los atributos del `serviceCertificate` elemento son idénticos a los atributos de [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c1221-124">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1221-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1221-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="c1221-126">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="c1221-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="c1221-127">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="c1221-127">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="c1221-128">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="c1221-128">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="c1221-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c1221-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

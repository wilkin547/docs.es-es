---
title: <serviceCertificate>del <clientCredentials> elemento
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4c7489a171bdd5cb4b747ca99f1b7ff6dd65517b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399682"
---
# <a name="servicecertificate-of-clientcredentials-element"></a><span data-ttu-id="d3ef1-102">\<serviceCertificate > de \<elemento > clientCredentials</span><span class="sxs-lookup"><span data-stu-id="d3ef1-102">\<serviceCertificate> of \<clientCredentials> Element</span></span>
<span data-ttu-id="d3ef1-103">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
<span data-ttu-id="d3ef1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d3ef1-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d3ef1-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d3ef1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d3ef1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d3ef1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d3ef1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="d3ef1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceCertificate**</span><span class="sxs-lookup"><span data-stu-id="d3ef1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ef1-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3ef1-111">Syntax</span></span>  
  
```xml  
<serviceCertificate />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3ef1-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d3ef1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d3ef1-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3ef1-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3ef1-114">Attributes</span></span>  
 <span data-ttu-id="d3ef1-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d3ef1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3ef1-116">Child Elements</span></span>  
  
|<span data-ttu-id="d3ef1-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3ef1-117">Element</span></span>|<span data-ttu-id="d3ef1-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3ef1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3ef1-119">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="d3ef1-119">\<defaultCertificate></span></span>](defaultcertificate-element.md)|<span data-ttu-id="d3ef1-120">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-120">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="d3ef1-121">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="d3ef1-121">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="d3ef1-122">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-122">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="d3ef1-123">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-123">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="d3ef1-124">\<authentication></span><span class="sxs-lookup"><span data-stu-id="d3ef1-124">\<authentication></span></span>](authentication-of-servicecertificate-element.md)|<span data-ttu-id="d3ef1-125">Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-125">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3ef1-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d3ef1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d3ef1-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3ef1-127">Element</span></span>|<span data-ttu-id="d3ef1-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d3ef1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3ef1-129">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="d3ef1-129">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="d3ef1-130">Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-130">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3ef1-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3ef1-131">Remarks</span></span>  
 <span data-ttu-id="d3ef1-132">Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-132">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="d3ef1-133">También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-133">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="d3ef1-134">Los atributos del `serviceCertificate` elemento son idénticos a los atributos [ \<del > clientCertificate](clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="d3ef1-134">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ef1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3ef1-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [<span data-ttu-id="d3ef1-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="d3ef1-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d3ef1-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="d3ef1-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d3ef1-138">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="d3ef1-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="d3ef1-139">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d3ef1-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

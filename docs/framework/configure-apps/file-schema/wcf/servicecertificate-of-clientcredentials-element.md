---
title: Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3fbb3ef0fddd287fa3feb30732b26c651ac0067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="e4a55-102">Elemento &lt;serviceCertificate&gt; de &lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="e4a55-102">&lt;serviceCertificate&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="e4a55-103">Especifica el certificado que se va a utilizar al autenticar un servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="e4a55-103">Specifies a certificate to use when authenticating a service to the client.</span></span>  
  
 <span data-ttu-id="e4a55-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e4a55-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e4a55-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="e4a55-105">\<behaviors></span></span>  
<span data-ttu-id="e4a55-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e4a55-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e4a55-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e4a55-107">\<behavior></span></span>  
<span data-ttu-id="e4a55-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e4a55-108">\<clientCredentials></span></span>  
<span data-ttu-id="e4a55-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="e4a55-109">\<serviceCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a55-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4a55-110">Syntax</span></span>  
  
```xml  
<serviceCertificate />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4a55-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4a55-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e4a55-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4a55-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4a55-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4a55-113">Attributes</span></span>  
 <span data-ttu-id="e4a55-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e4a55-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e4a55-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4a55-115">Child Elements</span></span>  
  
|<span data-ttu-id="e4a55-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4a55-116">Element</span></span>|<span data-ttu-id="e4a55-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4a55-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4a55-118">\<defaultCertificate ></span><span class="sxs-lookup"><span data-stu-id="e4a55-118">\<defaultCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|<span data-ttu-id="e4a55-119">Especifica un certificado X.509 que se usará cuando un servicio o STS no proporcione uno a través de un protocolo de negociación.</span><span class="sxs-lookup"><span data-stu-id="e4a55-119">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>|  
|[<span data-ttu-id="e4a55-120">\<scopedCertificates ></span><span class="sxs-lookup"><span data-stu-id="e4a55-120">\<scopedCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|<span data-ttu-id="e4a55-121">Representa una colección de certificados X.509 proporcionada por servicios concretos (con ámbito) para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="e4a55-121">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span> <span data-ttu-id="e4a55-122">Esta colección se utiliza normalmente para especificar los certificados de servicio para los servicios de token de seguridad en un escenario asociado externo.</span><span class="sxs-lookup"><span data-stu-id="e4a55-122">This collection is typically used to specify the service certificates for Security Token Services in a federated scenario.</span></span>|  
|[<span data-ttu-id="e4a55-123">\<autenticación ></span><span class="sxs-lookup"><span data-stu-id="e4a55-123">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|<span data-ttu-id="e4a55-124">Especifica los comportamientos de autenticación para los certificados de servicio utilizados por un cliente.</span><span class="sxs-lookup"><span data-stu-id="e4a55-124">Specifies authentication behaviors for service certificates used by a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4a55-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4a55-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e4a55-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4a55-126">Element</span></span>|<span data-ttu-id="e4a55-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4a55-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4a55-128">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="e4a55-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="e4a55-129">Especifica las credenciales utilizadas por el cliente para autenticarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="e4a55-129">Specifies the credentials used by the client to authenticate itself to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a55-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4a55-130">Remarks</span></span>  
 <span data-ttu-id="e4a55-131">Este elemento de configuración especifica la configuración utilizada por el cliente para validar el certificado presentado por el servicio utilizando la autenticación SSL.</span><span class="sxs-lookup"><span data-stu-id="e4a55-131">This configuration element specifies the settings used by the client to validate the certificate presented by the service using SSL authentication.</span></span> <span data-ttu-id="e4a55-132">También contiene cualquier certificado para el servicio que se configura explícitamente en el cliente y que se utiliza para cifrar los mensajes para el servicio, utilizando la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4a55-132">It also contains any certificate for the service that is explicitly configured on the client to use for encrypting messages to the service using message security.</span></span>  
  
 <span data-ttu-id="e4a55-133">Los atributos de la `serviceCertificate` elemento son idénticos a los atributos de la [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="e4a55-133">The attributes of the `serviceCertificate` element are identical to the attributes of the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a55-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4a55-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [<span data-ttu-id="e4a55-135">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="e4a55-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="e4a55-136">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="e4a55-136">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="e4a55-137">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="e4a55-137">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e4a55-138">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="e4a55-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

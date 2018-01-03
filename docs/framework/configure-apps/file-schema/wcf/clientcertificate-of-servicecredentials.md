---
title: '&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0bd36f0c13aebb75bb9d2147e871224c162b862
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a><span data-ttu-id="2104a-102">&lt;clientCertificate&gt; de &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="2104a-102">&lt;clientCertificate&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="2104a-103">Define un certificado X.509 usado para firmar y cifrar mensajes a un formulario de cliente un servicio en un modelo de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="2104a-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="2104a-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2104a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2104a-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="2104a-105">\<behaviors></span></span>  
<span data-ttu-id="2104a-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2104a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2104a-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2104a-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="2104a-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="2104a-108">\<behavior></span></span>  
<span data-ttu-id="2104a-109">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="2104a-109">\<serviceCredentials></span></span>  
<span data-ttu-id="2104a-110">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="2104a-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2104a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2104a-111">Syntax</span></span>  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2104a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2104a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2104a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2104a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2104a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="2104a-114">Attributes</span></span>  
 <span data-ttu-id="2104a-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2104a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2104a-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2104a-116">Child Elements</span></span>  
  
|<span data-ttu-id="2104a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2104a-117">Element</span></span>|<span data-ttu-id="2104a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2104a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2104a-119">\<autenticación ></span><span class="sxs-lookup"><span data-stu-id="2104a-119">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|<span data-ttu-id="2104a-120">Especifica las opciones de autenticación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="2104a-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="2104a-121">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="2104a-121">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|<span data-ttu-id="2104a-122">Especifica el certificado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="2104a-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2104a-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2104a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2104a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2104a-124">Element</span></span>|<span data-ttu-id="2104a-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2104a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2104a-126">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="2104a-126">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="2104a-127">Especifica las credenciales que se van a usar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="2104a-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2104a-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2104a-128">Remarks</span></span>  
 <span data-ttu-id="2104a-129">Este elemento se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="2104a-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="2104a-130">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="2104a-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="2104a-131">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="2104a-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="2104a-132">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="2104a-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="2104a-133">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="2104a-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="2104a-134">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="2104a-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="2104a-135">El conjunto de certificados de este elemento se utiliza para cifrar los mensajes para el cliente únicamente para los enlaces que se configuran con `MutualCertificateDuplex` el modo de autenticación de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="2104a-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2104a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2104a-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [<span data-ttu-id="2104a-137">Creación de un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="2104a-137">How to: Create a Duplex Contract</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="2104a-138">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="2104a-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="2104a-139">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="2104a-139">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)

---
description: 'Más información sobre: <clientCertificate> de <serviceCredentials>'
title: <clientCertificate> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: c3e6378f9646ec30188e2de3d1c832f363904ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638826"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="60c2f-103">\<clientCertificate> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="60c2f-103">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="60c2f-104">Define un certificado X.509 usado para firmar y cifrar mensajes a un formulario de cliente un servicio en un modelo de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="60c2f-104">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="60c2f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60c2f-105">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60c2f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60c2f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="60c2f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60c2f-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60c2f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="60c2f-108">Attributes</span></span>  

 <span data-ttu-id="60c2f-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60c2f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="60c2f-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60c2f-110">Child Elements</span></span>  
  
|<span data-ttu-id="60c2f-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="60c2f-111">Element</span></span>|<span data-ttu-id="60c2f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="60c2f-112">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="60c2f-113">Especifica las opciones de autenticación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2f-113">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="60c2f-114">Especifica el certificado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="60c2f-114">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60c2f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60c2f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="60c2f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="60c2f-116">Element</span></span>|<span data-ttu-id="60c2f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="60c2f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="60c2f-118">Especifica las credenciales que se van a usar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2f-118">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60c2f-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="60c2f-119">Remarks</span></span>  

 <span data-ttu-id="60c2f-120">Este elemento se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2f-120">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="60c2f-121">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="60c2f-121">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="60c2f-122">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2f-122">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="60c2f-123">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="60c2f-123">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="60c2f-124">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="60c2f-124">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="60c2f-125">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="60c2f-125">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="60c2f-126">El conjunto de certificados de este elemento se utiliza para cifrar los mensajes para el cliente únicamente para los enlaces que se configuran con `MutualCertificateDuplex` el modo de autenticación de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="60c2f-126">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c2f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="60c2f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="60c2f-128">Procedimiento para crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="60c2f-128">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="60c2f-129">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="60c2f-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="60c2f-130">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="60c2f-130">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

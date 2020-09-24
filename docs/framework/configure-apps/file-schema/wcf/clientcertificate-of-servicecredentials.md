---
title: <clientCertificate> de <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148922"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="a5515-102">\<clientCertificate> de \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="a5515-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="a5515-103">Define un certificado X.509 usado para firmar y cifrar mensajes a un formulario de cliente un servicio en un modelo de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="a5515-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="a5515-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5515-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5515-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5515-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a5515-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5515-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5515-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5515-107">Attributes</span></span>  

 <span data-ttu-id="a5515-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a5515-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5515-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a5515-109">Child Elements</span></span>  
  
|<span data-ttu-id="a5515-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5515-110">Element</span></span>|<span data-ttu-id="a5515-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5515-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="a5515-112">Especifica las opciones de autenticación del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="a5515-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="a5515-113">Especifica el certificado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a5515-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5515-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5515-114">Parent Elements</span></span>  
  
|<span data-ttu-id="a5515-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5515-115">Element</span></span>|<span data-ttu-id="a5515-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5515-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="a5515-117">Especifica las credenciales que se van a usar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="a5515-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5515-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5515-118">Remarks</span></span>  

 <span data-ttu-id="a5515-119">Este elemento se usa cuando el servicio debe tener el certificado del cliente por anticipado para comunicarse de manera segura con el cliente.</span><span class="sxs-lookup"><span data-stu-id="a5515-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="a5515-120">Esto se produce al utilizar el patrón de comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="a5515-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="a5515-121">En el patrón de solicitud/respuesta más típico, el cliente incluye su certificado en la solicitud, que utiliza el servicio para cifrar i firmar su respuesta de vuelta hasta el cliente.</span><span class="sxs-lookup"><span data-stu-id="a5515-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="a5515-122">Sin embargo, en el patrón de comunicación dúplex, el servicio no tiene una solicitud del cliente y por consiguiente necesita que el certificado del cliente proteja de antemano el mensaje al cliente.</span><span class="sxs-lookup"><span data-stu-id="a5515-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="a5515-123">Por tanto, debe obtener el certificado del cliente en una negociación fuera de banda y especificar el certificado usando este elemento.</span><span class="sxs-lookup"><span data-stu-id="a5515-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="a5515-124">Para obtener más información sobre los servicios dúplex, consulte [Cómo: crear un contrato dúplex](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a5515-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="a5515-125">El conjunto de certificados de este elemento se utiliza para cifrar los mensajes para el cliente únicamente para los enlaces que se configuran con `MutualCertificateDuplex` el modo de autenticación de seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a5515-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5515-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5515-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="a5515-127">Procedimiento para crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="a5515-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="a5515-128">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="a5515-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a5515-129">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="a5515-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)

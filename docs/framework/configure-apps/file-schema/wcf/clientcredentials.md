---
description: 'Más información acerca de: <clientCredentials>'
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: b10e046f8e4994e367db69d5863e54a0bfa07db5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638813"
---
# \<clientCredentials>

<span data-ttu-id="95b22-102">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="95b22-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="95b22-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95b22-103">Syntax</span></span>  
  
```xml  
<clientCredentials type="String"
                   supportInteractive="Boolean" >
  <clientCertificate>
  </clientCertificate>
  <digest>
  </digest>
  <isuedToken>
  </isuedToken>
  <peer>
  </peer>
  <serviceCertificate>
  </serviceCertificate>
  <windowsAuthentication>
  </windowsAuthentication>
</clientCredentials>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95b22-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95b22-104">Attributes and Elements</span></span>  

 <span data-ttu-id="95b22-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95b22-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95b22-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="95b22-106">Attributes</span></span>  
  
|<span data-ttu-id="95b22-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="95b22-107">Attribute</span></span>|<span data-ttu-id="95b22-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="95b22-108">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="95b22-109">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="95b22-109">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="95b22-110">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="95b22-110">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="95b22-111">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="95b22-111">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95b22-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95b22-112">Child Elements</span></span>  
  
|<span data-ttu-id="95b22-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="95b22-113">Element</span></span>|<span data-ttu-id="95b22-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="95b22-114">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="95b22-115">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="95b22-115">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="95b22-116">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-116">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="95b22-117">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="95b22-117">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="95b22-118">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-118">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="95b22-119">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="95b22-119">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="95b22-120">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-120">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="95b22-121">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="95b22-121">Specifies a current peer credential.</span></span> <span data-ttu-id="95b22-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-122">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="95b22-123">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="95b22-123">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="95b22-124">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="95b22-124">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="95b22-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-125">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="95b22-126">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="95b22-126">Specifies a Windows credential.</span></span> <span data-ttu-id="95b22-127">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="95b22-127">The default is the credential of the current thread.</span></span> <span data-ttu-id="95b22-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="95b22-128">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95b22-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95b22-129">Parent Elements</span></span>  
  
|<span data-ttu-id="95b22-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="95b22-130">Element</span></span>|<span data-ttu-id="95b22-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="95b22-131">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="95b22-132">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="95b22-132">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95b22-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="95b22-133">Remarks</span></span>  

 <span data-ttu-id="95b22-134">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="95b22-134">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="95b22-135">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="95b22-135">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b22-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="95b22-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="95b22-137">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="95b22-137">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="95b22-138">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="95b22-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)

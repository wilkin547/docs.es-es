---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 6094006df24ee824c419a783ab29d7604757577c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201465"
---
# \<clientCredentials>

<span data-ttu-id="1bc24-101">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="1bc24-101">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**  
  
## <a name="syntax"></a><span data-ttu-id="1bc24-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bc24-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bc24-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1bc24-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1bc24-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1bc24-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bc24-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="1bc24-105">Attributes</span></span>  
  
|<span data-ttu-id="1bc24-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="1bc24-106">Attribute</span></span>|<span data-ttu-id="1bc24-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bc24-107">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="1bc24-108">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1bc24-108">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="1bc24-109">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="1bc24-109">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="1bc24-110">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="1bc24-110">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bc24-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1bc24-111">Child Elements</span></span>  
  
|<span data-ttu-id="1bc24-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bc24-112">Element</span></span>|<span data-ttu-id="1bc24-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bc24-113">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="1bc24-114">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="1bc24-114">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="1bc24-115">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-115">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[\<httpDigest>](httpdigest-element.md)|<span data-ttu-id="1bc24-116">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="1bc24-116">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="1bc24-117">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-117">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="1bc24-118">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="1bc24-118">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="1bc24-119">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-119">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="1bc24-120">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="1bc24-120">Specifies a current peer credential.</span></span> <span data-ttu-id="1bc24-121">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-121">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="1bc24-122">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="1bc24-122">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="1bc24-123">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="1bc24-123">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="1bc24-124">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-124">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[\<windows>](windows-of-clientcredentials-element.md)|<span data-ttu-id="1bc24-125">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="1bc24-125">Specifies a Windows credential.</span></span> <span data-ttu-id="1bc24-126">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1bc24-126">The default is the credential of the current thread.</span></span> <span data-ttu-id="1bc24-127">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="1bc24-127">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1bc24-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1bc24-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1bc24-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bc24-129">Element</span></span>|<span data-ttu-id="1bc24-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bc24-130">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1bc24-131">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1bc24-131">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bc24-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bc24-132">Remarks</span></span>  

 <span data-ttu-id="1bc24-133">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="1bc24-133">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="1bc24-134">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="1bc24-134">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc24-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bc24-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="1bc24-136">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="1bc24-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="1bc24-137">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="1bc24-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)

---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: 7ee49d6960864826dc74fbff629f502fcc70b4bf
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254813"
---
# <a name="clientcredentials"></a><span data-ttu-id="b5b1a-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b5b1a-101">\<clientCredentials></span></span>
<span data-ttu-id="b5b1a-102">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="b5b1a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b5b1a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b5b1a-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="b5b1a-104">\<behaviors></span></span>  
<span data-ttu-id="b5b1a-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b5b1a-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="b5b1a-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="b5b1a-106">\<behavior></span></span>  
<span data-ttu-id="b5b1a-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b5b1a-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b1a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5b1a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5b1a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b5b1a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b5b1a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5b1a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b5b1a-111">Attributes</span></span>  
  
|<span data-ttu-id="b5b1a-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b5b1a-112">Attribute</span></span>|<span data-ttu-id="b5b1a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5b1a-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="b5b1a-114">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="b5b1a-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="b5b1a-116">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5b1a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b5b1a-117">Child Elements</span></span>  
  
|<span data-ttu-id="b5b1a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5b1a-118">Element</span></span>|<span data-ttu-id="b5b1a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5b1a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5b1a-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="b5b1a-120">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="b5b1a-121">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="b5b1a-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="b5b1a-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="b5b1a-123">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="b5b1a-124">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="b5b1a-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="b5b1a-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="b5b1a-126">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="b5b1a-127">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="b5b1a-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="b5b1a-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="b5b1a-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="b5b1a-129">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="b5b1a-130">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-130">Specifies a current peer credential.</span></span> <span data-ttu-id="b5b1a-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="b5b1a-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="b5b1a-132">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="b5b1a-133">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="b5b1a-134">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="b5b1a-135">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="b5b1a-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="b5b1a-136">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="b5b1a-137">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-137">Specifies a Windows credential.</span></span> <span data-ttu-id="b5b1a-138">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="b5b1a-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b5b1a-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b5b1a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="b5b1a-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="b5b1a-141">Element</span></span>|<span data-ttu-id="b5b1a-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5b1a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5b1a-143">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b5b1a-143">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b5b1a-144">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5b1a-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5b1a-145">Remarks</span></span>  
 <span data-ttu-id="b5b1a-146">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="b5b1a-147">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="b5b1a-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b1a-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5b1a-148">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="b5b1a-149">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="b5b1a-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b5b1a-150">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="b5b1a-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)

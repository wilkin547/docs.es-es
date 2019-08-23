---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: c3e756f49b7054d6553eb6c3f1850f0fbce14943
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926110"
---
# <a name="clientcredentials"></a><span data-ttu-id="8bcbc-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8bcbc-101">\<clientCredentials></span></span>
<span data-ttu-id="8bcbc-102">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="8bcbc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8bcbc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8bcbc-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="8bcbc-104">\<behaviors></span></span>  
<span data-ttu-id="8bcbc-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8bcbc-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="8bcbc-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8bcbc-106">\<behavior></span></span>  
<span data-ttu-id="8bcbc-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8bcbc-107">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bcbc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bcbc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bcbc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8bcbc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8bcbc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bcbc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8bcbc-111">Attributes</span></span>  
  
|<span data-ttu-id="8bcbc-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="8bcbc-112">Attribute</span></span>|<span data-ttu-id="8bcbc-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8bcbc-113">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="8bcbc-114">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-114">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="8bcbc-115">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-115">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="8bcbc-116">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-116">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bcbc-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8bcbc-117">Child Elements</span></span>  
  
|<span data-ttu-id="8bcbc-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bcbc-118">Element</span></span>|<span data-ttu-id="8bcbc-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8bcbc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bcbc-120">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="8bcbc-120">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="8bcbc-121">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-121">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="8bcbc-122">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-122">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="8bcbc-123">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="8bcbc-123">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="8bcbc-124">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-124">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="8bcbc-125">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-125">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="8bcbc-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8bcbc-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="8bcbc-127">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="8bcbc-127">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="8bcbc-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-128">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="8bcbc-129">\<peer></span><span class="sxs-lookup"><span data-stu-id="8bcbc-129">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="8bcbc-130">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-130">Specifies a current peer credential.</span></span> <span data-ttu-id="8bcbc-131">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-131">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="8bcbc-132">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="8bcbc-132">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="8bcbc-133">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-133">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="8bcbc-134">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-134">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="8bcbc-135">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-135">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="8bcbc-136">\<windows></span><span class="sxs-lookup"><span data-stu-id="8bcbc-136">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="8bcbc-137">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-137">Specifies a Windows credential.</span></span> <span data-ttu-id="8bcbc-138">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-138">The default is the credential of the current thread.</span></span> <span data-ttu-id="8bcbc-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-139">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bcbc-140">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8bcbc-140">Parent Elements</span></span>  
  
|<span data-ttu-id="8bcbc-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bcbc-141">Element</span></span>|<span data-ttu-id="8bcbc-142">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8bcbc-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bcbc-143">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8bcbc-143">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="8bcbc-144">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-144">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bcbc-145">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bcbc-145">Remarks</span></span>  
 <span data-ttu-id="8bcbc-146">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-146">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="8bcbc-147">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="8bcbc-147">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bcbc-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bcbc-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="8bcbc-149">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="8bcbc-149">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8bcbc-150">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="8bcbc-150">Securing Clients</span></span>](../../../wcf/securing-clients.md)

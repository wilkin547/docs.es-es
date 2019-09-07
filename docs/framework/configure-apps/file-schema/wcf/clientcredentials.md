---
title: <clientCredentials>
ms.date: 03/30/2017
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
ms.openlocfilehash: f295fe48e194611c80b78c0c23ab3e66ea1c0b64
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400499"
---
# <a name="clientcredentials"></a><span data-ttu-id="f6c9f-101">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f6c9f-101">\<clientCredentials></span></span>
<span data-ttu-id="f6c9f-102">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-102">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
<span data-ttu-id="f6c9f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f6c9f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f6c9f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f6c9f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f6c9f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f6c9f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f6c9f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f6c9f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f6c9f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f6c9f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f6c9f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clientCredentials >**</span><span class="sxs-lookup"><span data-stu-id="f6c9f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCredentials>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6c9f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6c9f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6c9f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f6c9f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f6c9f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6c9f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f6c9f-112">Attributes</span></span>  
  
|<span data-ttu-id="f6c9f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f6c9f-113">Attribute</span></span>|<span data-ttu-id="f6c9f-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f6c9f-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="f6c9f-115">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="f6c9f-116">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="f6c9f-117">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f6c9f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f6c9f-118">Child Elements</span></span>  
  
|<span data-ttu-id="f6c9f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6c9f-119">Element</span></span>|<span data-ttu-id="f6c9f-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f6c9f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6c9f-121">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="f6c9f-121">\<clientCertificate></span></span>](clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="f6c9f-122">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="f6c9f-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f6c9f-124">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="f6c9f-124">\<httpDigest></span></span>](httpdigest-element.md)|<span data-ttu-id="f6c9f-125">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="f6c9f-126">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="f6c9f-127">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="f6c9f-127">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="f6c9f-128">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="f6c9f-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="f6c9f-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="f6c9f-130">\<peer></span><span class="sxs-lookup"><span data-stu-id="f6c9f-130">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="f6c9f-131">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-131">Specifies a current peer credential.</span></span> <span data-ttu-id="f6c9f-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="f6c9f-133">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="f6c9f-133">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="f6c9f-134">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="f6c9f-135">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="f6c9f-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f6c9f-137">\<windows></span><span class="sxs-lookup"><span data-stu-id="f6c9f-137">\<windows></span></span>](windows-of-clientcredentials-element.md)|<span data-ttu-id="f6c9f-138">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-138">Specifies a Windows credential.</span></span> <span data-ttu-id="f6c9f-139">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="f6c9f-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6c9f-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f6c9f-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f6c9f-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="f6c9f-142">Element</span></span>|<span data-ttu-id="f6c9f-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f6c9f-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6c9f-144">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f6c9f-144">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f6c9f-145">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6c9f-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6c9f-146">Remarks</span></span>  
 <span data-ttu-id="f6c9f-147">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="f6c9f-148">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="f6c9f-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c9f-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6c9f-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- [<span data-ttu-id="f6c9f-150">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f6c9f-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f6c9f-151">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f6c9f-151">Securing Clients</span></span>](../../../wcf/securing-clients.md)

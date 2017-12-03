---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 834853d8a922148d2810cd391a64a281f2f9ae3c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientcredentialsgt"></a><span data-ttu-id="f220b-102">&lt;clientCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="f220b-102">&lt;clientCredentials&gt;</span></span>
<span data-ttu-id="f220b-103">Especifica las credenciales usadas para autenticar el cliente en un servicio.</span><span class="sxs-lookup"><span data-stu-id="f220b-103">Specifies the credentials used to authenticate the client to a service.</span></span>  
  
 <span data-ttu-id="f220b-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f220b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f220b-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f220b-105">\<behaviors></span></span>  
<span data-ttu-id="f220b-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f220b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="f220b-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f220b-107">\<behavior></span></span>  
<span data-ttu-id="f220b-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="f220b-108">\<clientCredentials></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f220b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f220b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f220b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f220b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f220b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f220b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f220b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f220b-112">Attributes</span></span>  
  
|<span data-ttu-id="f220b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f220b-113">Attribute</span></span>|<span data-ttu-id="f220b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f220b-114">Description</span></span>|  
|---------------|-----------------|  
|`supportInteractive`|<span data-ttu-id="f220b-115">Un valor booleano que especifica si un usuario interactivo puede estar implicado en la selección de una credencial del cliente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f220b-115">A Boolean value that specifies whether an interactive user can be involved in selecting a client credential at runtime.</span></span> <span data-ttu-id="f220b-116">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="f220b-116">The default value is `true`.</span></span>|  
|`type`|<span data-ttu-id="f220b-117">Una cadena que especifica el tipo de este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="f220b-117">A string that specifies the type of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f220b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f220b-118">Child Elements</span></span>  
  
|<span data-ttu-id="f220b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f220b-119">Element</span></span>|<span data-ttu-id="f220b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f220b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f220b-121">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="f220b-121">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|<span data-ttu-id="f220b-122">Especifica el certificado usado para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="f220b-122">Specifies the certificate used to authenticate the client to the service.</span></span> <span data-ttu-id="f220b-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-123">This element is of type <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f220b-124">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="f220b-124">\<httpDigest></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|<span data-ttu-id="f220b-125">Especifica el uso de una autenticación implícita para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="f220b-125">Specifies a digest used to authenticate the client to the service.</span></span> <span data-ttu-id="f220b-126">Este elemento es del tipo <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-126">This element is of type <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.</span></span>|  
|[<span data-ttu-id="f220b-127">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="f220b-127">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="f220b-128">Especifica un tipo de token usado para autenticar el cliente a un servicio de token seguro (STS).</span><span class="sxs-lookup"><span data-stu-id="f220b-128">Specifies a custom token type used to authenticate the client to a Secure Token Service (STS).</span></span> <span data-ttu-id="f220b-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-129">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.</span></span>|  
|[<span data-ttu-id="f220b-130">\<punto ></span><span class="sxs-lookup"><span data-stu-id="f220b-130">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="f220b-131">Especifica una credencial del mismo nivel actual.</span><span class="sxs-lookup"><span data-stu-id="f220b-131">Specifies a current peer credential.</span></span> <span data-ttu-id="f220b-132">Este elemento es del tipo <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-132">This element is of type <xref:System.ServiceModel.Configuration.PeerCredentialElement>.</span></span>|  
|[<span data-ttu-id="f220b-133">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f220b-133">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="f220b-134">Especifica el certificado usado para autenticar el servicio al cliente y proporciona una estructura para establecer las opciones de certificado.</span><span class="sxs-lookup"><span data-stu-id="f220b-134">Specifies the certificate used to authenticate the service to the client and provides a structure for setting certificate options.</span></span> <span data-ttu-id="f220b-135">Este certificado se debe proporcionar fuera de banda del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="f220b-135">This certificate must be supplied out-of-band from the service to the client.</span></span> <span data-ttu-id="f220b-136">Este elemento es del tipo <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-136">This element is of type <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.</span></span>|  
|[<span data-ttu-id="f220b-137">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="f220b-137">\<windows></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|<span data-ttu-id="f220b-138">Especifica la credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="f220b-138">Specifies a Windows credential.</span></span> <span data-ttu-id="f220b-139">El valor predeterminado es la credencial del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f220b-139">The default is the credential of the current thread.</span></span> <span data-ttu-id="f220b-140">Este elemento es del tipo <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span><span class="sxs-lookup"><span data-stu-id="f220b-140">This element is of type <xref:System.ServiceModel.Configuration.WindowsClientElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f220b-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f220b-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f220b-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="f220b-142">Element</span></span>|<span data-ttu-id="f220b-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="f220b-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f220b-144">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f220b-144">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f220b-145">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f220b-145">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f220b-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f220b-146">Remarks</span></span>  
 <span data-ttu-id="f220b-147">Las credenciales de cliente se utilizan para autenticar al cliente en los servicios en casos donde se requiere autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="f220b-147">Client credentials are used to authenticate the client to services in cases where mutual authentication is required.</span></span> <span data-ttu-id="f220b-148">Esta sección de configuración también se puede usar para especificar los certificados de servicio para escenarios donde el cliente debe proteger los mensajes para un servicio con el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="f220b-148">This configuration section can also be used to specify service certificates for scenarios where the client must secure messages to a service with the service's certificate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f220b-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="f220b-149">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [<span data-ttu-id="f220b-150">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="f220b-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f220b-151">Protección de clientes</span><span class="sxs-lookup"><span data-stu-id="f220b-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)

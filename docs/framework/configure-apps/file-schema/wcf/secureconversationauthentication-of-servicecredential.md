---
title: Elemento &lt;secureConversationAuthentication&gt; de &lt;serviceCredential&gt;
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 8433ac8f698f3e5569802a8d76f7dedaf22f53c3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180382"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="e8377-102">Elemento &lt;secureConversationAuthentication&gt; de &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="e8377-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="e8377-103">Especifica los valores para un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="e8377-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="e8377-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e8377-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e8377-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="e8377-105">\<behaviors></span></span>  
<span data-ttu-id="e8377-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e8377-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e8377-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e8377-107">\<behavior></span></span>  
<span data-ttu-id="e8377-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e8377-108">\<serviceCredentials></span></span>  
<span data-ttu-id="e8377-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="e8377-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8377-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8377-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8377-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8377-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e8377-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e8377-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8377-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8377-113">Attributes</span></span>  
  
|<span data-ttu-id="e8377-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e8377-114">Attribute</span></span>|<span data-ttu-id="e8377-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8377-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="e8377-116">Una cadena que especifica el tipo de <xref:System.ServiceModel.Security.SecurityStateEncoder> que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="e8377-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8377-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8377-117">Child Elements</span></span>  
 <span data-ttu-id="e8377-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8377-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8377-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8377-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e8377-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8377-120">Element</span></span>|<span data-ttu-id="e8377-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8377-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8377-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="e8377-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="e8377-123">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="e8377-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8377-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8377-124">Remarks</span></span>  
 <span data-ttu-id="e8377-125">Utilice este elemento de configuración para especificar una lista de tipos de demanda conocidos para la serialización de cookies de token de contexto de seguridad (SCT), así como un codificador para codificar y proteger la información de las cookies.</span><span class="sxs-lookup"><span data-stu-id="e8377-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="e8377-126">Para obtener más información acerca de SCT, vea <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="e8377-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8377-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8377-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

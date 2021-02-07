---
description: 'Más información sobre: <secureConversationAuthentication> de <serviceCredential>'
title: <secureConversationAuthentication> de <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 8f95b4009111996d2a5c1133c9ef762375b4e3e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683325"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="70043-103">\<secureConversationAuthentication> de \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="70043-103">\<secureConversationAuthentication> of \<serviceCredential></span></span>

<span data-ttu-id="70043-104">Especifica los valores para un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="70043-104">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="70043-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70043-105">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70043-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70043-106">Attributes and Elements</span></span>  

 <span data-ttu-id="70043-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="70043-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70043-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="70043-108">Attributes</span></span>  
  
|<span data-ttu-id="70043-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="70043-109">Attribute</span></span>|<span data-ttu-id="70043-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="70043-110">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="70043-111">Una cadena que especifica el tipo de <xref:System.ServiceModel.Security.SecurityStateEncoder> que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="70043-111">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70043-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70043-112">Child Elements</span></span>  

 <span data-ttu-id="70043-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="70043-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70043-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70043-114">Parent Elements</span></span>  
  
|<span data-ttu-id="70043-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="70043-115">Element</span></span>|<span data-ttu-id="70043-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="70043-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="70043-117">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="70043-117">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70043-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70043-118">Remarks</span></span>  

 <span data-ttu-id="70043-119">Utilice este elemento de configuración para especificar una lista de tipos de demanda conocidos para la serialización de cookies de token de contexto de seguridad (SCT), así como un codificador para codificar y proteger la información de las cookies.</span><span class="sxs-lookup"><span data-stu-id="70043-119">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="70043-120">Para obtener más información acerca de SCT, vea <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="70043-120">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70043-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="70043-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

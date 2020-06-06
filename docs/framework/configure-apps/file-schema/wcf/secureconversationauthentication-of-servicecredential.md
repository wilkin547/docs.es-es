---
title: <secureConversationAuthentication> de <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399932"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="7b910-102">\<secureConversationAuthentication> de \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="7b910-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="7b910-103">Especifica los valores para un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="7b910-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="7b910-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b910-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b910-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7b910-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7b910-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7b910-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b910-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="7b910-107">Attributes</span></span>  
  
|<span data-ttu-id="7b910-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="7b910-108">Attribute</span></span>|<span data-ttu-id="7b910-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b910-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="7b910-110">Una cadena que especifica el tipo de <xref:System.ServiceModel.Security.SecurityStateEncoder> que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="7b910-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b910-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7b910-111">Child Elements</span></span>  
 <span data-ttu-id="7b910-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7b910-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b910-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7b910-113">Parent Elements</span></span>  
  
|<span data-ttu-id="7b910-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b910-114">Element</span></span>|<span data-ttu-id="7b910-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b910-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="7b910-116">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="7b910-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b910-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b910-117">Remarks</span></span>  
 <span data-ttu-id="7b910-118">Utilice este elemento de configuración para especificar una lista de tipos de demanda conocidos para la serialización de cookies de token de contexto de seguridad (SCT), así como un codificador para codificar y proteger la información de las cookies.</span><span class="sxs-lookup"><span data-stu-id="7b910-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="7b910-119">Para obtener más información acerca de SCT, vea <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="7b910-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b910-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7b910-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

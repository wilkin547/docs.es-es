---
title: <secureConversationAuthentication> de <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399932"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="d099c-102">\<secureConversationAuthentication > \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="d099c-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="d099c-103">Especifica los valores para un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="d099c-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="d099c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d099c-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d099c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d099c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d099c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d099c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de serviceCredentials**](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d099c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="d099c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> secureConversationAuthentication**</span><span class="sxs-lookup"><span data-stu-id="d099c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d099c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d099c-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d099c-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d099c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d099c-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d099c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d099c-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d099c-114">Attributes</span></span>  
  
|<span data-ttu-id="d099c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d099c-115">Attribute</span></span>|<span data-ttu-id="d099c-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d099c-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="d099c-117">Una cadena que especifica el tipo de <xref:System.ServiceModel.Security.SecurityStateEncoder> que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="d099c-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d099c-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d099c-118">Child Elements</span></span>  
 <span data-ttu-id="d099c-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d099c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d099c-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d099c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d099c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d099c-121">Element</span></span>|<span data-ttu-id="d099c-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d099c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d099c-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="d099c-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="d099c-124">Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="d099c-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d099c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d099c-125">Remarks</span></span>  
 <span data-ttu-id="d099c-126">Utilice este elemento de configuración para especificar una lista de tipos de demanda conocidos para la serialización de cookies de token de contexto de seguridad (SCT), así como un codificador para codificar y proteger la información de las cookies.</span><span class="sxs-lookup"><span data-stu-id="d099c-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="d099c-127">Para obtener más información acerca de SCT, vea <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="d099c-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d099c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d099c-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

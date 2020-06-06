---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252016"
---
# \<customCookieHandler>
<span data-ttu-id="884eb-101">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="884eb-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="884eb-102">Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="884eb-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="884eb-103">El tipo personalizado se debe derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="884eb-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="884eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="884eb-104">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="884eb-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="884eb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="884eb-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="884eb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="884eb-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="884eb-107">Attributes</span></span>  
  
|<span data-ttu-id="884eb-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="884eb-108">Attribute</span></span>|<span data-ttu-id="884eb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="884eb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="884eb-110">type</span><span class="sxs-lookup"><span data-stu-id="884eb-110">type</span></span>|<span data-ttu-id="884eb-111">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="884eb-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="884eb-112">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="884eb-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="884eb-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="884eb-113">Child Elements</span></span>  
 <span data-ttu-id="884eb-114">None</span><span class="sxs-lookup"><span data-stu-id="884eb-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="884eb-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="884eb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="884eb-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="884eb-116">Element</span></span>|<span data-ttu-id="884eb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="884eb-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="884eb-118">Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> utiliza para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="884eb-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="884eb-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="884eb-119">Remarks</span></span>  
 <span data-ttu-id="884eb-120">Cuando se especifica un controlador de cookies personalizado estableciendo el `mode` atributo del `<cookieHandler>` elemento en "Custom", se debe especificar el tipo del controlador de cookies personalizado incluyendo un `<customCookieHandler>` elemento secundario que haga referencia al tipo de controlador de cookies.</span><span class="sxs-lookup"><span data-stu-id="884eb-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="884eb-121">No se puede especificar este elemento cuando el `mode` atributo está establecido en "fragmentado" o "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="884eb-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="884eb-122">Los controladores de cookies personalizados deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="884eb-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="884eb-123">El `<customCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.</span><span class="sxs-lookup"><span data-stu-id="884eb-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="884eb-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="884eb-124">Example</span></span>  
 <span data-ttu-id="884eb-125">En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizado de tipo `MyNamespace.MyCustomCookieHandler` .</span><span class="sxs-lookup"><span data-stu-id="884eb-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="884eb-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="884eb-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>

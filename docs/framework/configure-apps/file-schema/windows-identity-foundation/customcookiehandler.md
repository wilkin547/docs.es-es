---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252016"
---
# <a name="customcookiehandler"></a><span data-ttu-id="ca58b-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ca58b-101">\<customCookieHandler></span></span>
<span data-ttu-id="ca58b-102">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="ca58b-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="ca58b-103">Este elemento solo puede estar presente si el `mode` atributo `<cookieHandler>` del elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="ca58b-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="ca58b-104">El tipo personalizado se debe derivar de <xref:System.IdentityModel.Services.CookieHandler> la clase.</span><span class="sxs-lookup"><span data-stu-id="ca58b-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="ca58b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca58b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca58b-106">&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="ca58b-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="ca58b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> federationConfiguration**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ca58b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="ca58b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cookieHandler**](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="ca58b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="ca58b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customCookieHandler**</span><span class="sxs-lookup"><span data-stu-id="ca58b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca58b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca58b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca58b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca58b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ca58b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca58b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca58b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca58b-113">Attributes</span></span>  
  
|<span data-ttu-id="ca58b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="ca58b-114">Attribute</span></span>|<span data-ttu-id="ca58b-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ca58b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca58b-116">type</span><span class="sxs-lookup"><span data-stu-id="ca58b-116">type</span></span>|<span data-ttu-id="ca58b-117">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="ca58b-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="ca58b-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca58b-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca58b-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca58b-119">Child Elements</span></span>  
 <span data-ttu-id="ca58b-120">None</span><span class="sxs-lookup"><span data-stu-id="ca58b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca58b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca58b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ca58b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca58b-122">Element</span></span>|<span data-ttu-id="ca58b-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ca58b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca58b-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ca58b-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="ca58b-125">Configura el <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> que utiliza para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="ca58b-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca58b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca58b-126">Remarks</span></span>  
 <span data-ttu-id="ca58b-127">Cuando se especifica un controlador de cookies personalizado estableciendo `mode` el atributo `<cookieHandler>` del elemento en "Custom", se debe especificar el tipo del controlador de cookies personalizado incluyendo un `<customCookieHandler>` elemento secundario que haga referencia al tipo de controlador de cookies.</span><span class="sxs-lookup"><span data-stu-id="ca58b-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="ca58b-128">No se puede especificar este elemento cuando `mode` el atributo está establecido en "fragmentado" o "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="ca58b-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="ca58b-129">Los controladores de cookies personalizados deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="ca58b-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="ca58b-130">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase. `<customCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="ca58b-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca58b-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca58b-131">Example</span></span>  
 <span data-ttu-id="ca58b-132">En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizado `MyNamespace.MyCustomCookieHandler`de tipo.</span><span class="sxs-lookup"><span data-stu-id="ca58b-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca58b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca58b-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>

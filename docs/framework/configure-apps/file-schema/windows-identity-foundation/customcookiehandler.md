---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942791"
---
# <a name="customcookiehandler"></a><span data-ttu-id="633be-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="633be-101">\<customCookieHandler></span></span>
<span data-ttu-id="633be-102">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="633be-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="633be-103">Este elemento solo puede estar presente si el `mode` atributo `<cookieHandler>` del elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="633be-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="633be-104">El tipo personalizado se debe derivar de <xref:System.IdentityModel.Services.CookieHandler> la clase.</span><span class="sxs-lookup"><span data-stu-id="633be-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="633be-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="633be-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="633be-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="633be-106">\<federationConfiguration></span></span>  
<span data-ttu-id="633be-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="633be-107">\<cookieHandler></span></span>  
<span data-ttu-id="633be-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="633be-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="633be-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="633be-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="633be-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="633be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="633be-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="633be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="633be-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="633be-112">Attributes</span></span>  
  
|<span data-ttu-id="633be-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="633be-113">Attribute</span></span>|<span data-ttu-id="633be-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="633be-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="633be-115">type</span><span class="sxs-lookup"><span data-stu-id="633be-115">type</span></span>|<span data-ttu-id="633be-116">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="633be-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="633be-117">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="633be-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="633be-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="633be-118">Child Elements</span></span>  
 <span data-ttu-id="633be-119">None</span><span class="sxs-lookup"><span data-stu-id="633be-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="633be-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="633be-120">Parent Elements</span></span>  
  
|<span data-ttu-id="633be-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="633be-121">Element</span></span>|<span data-ttu-id="633be-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="633be-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="633be-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="633be-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="633be-124">Configura el <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> que utiliza para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="633be-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="633be-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="633be-125">Remarks</span></span>  
 <span data-ttu-id="633be-126">Cuando se especifica un controlador de cookies personalizado estableciendo `mode` el atributo `<cookieHandler>` del elemento en "Custom", se debe especificar el tipo del controlador de cookies personalizado incluyendo un `<customCookieHandler>` elemento secundario que haga referencia al tipo de controlador de cookies.</span><span class="sxs-lookup"><span data-stu-id="633be-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="633be-127">No se puede especificar este elemento cuando `mode` el atributo está establecido en "fragmentado" o "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="633be-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="633be-128">Los controladores de cookies personalizados deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="633be-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="633be-129">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase. `<customCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="633be-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="633be-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="633be-130">Example</span></span>  
 <span data-ttu-id="633be-131">En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizado `MyNamespace.MyCustomCookieHandler`de tipo.</span><span class="sxs-lookup"><span data-stu-id="633be-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="633be-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="633be-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>

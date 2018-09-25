---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081596"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="b6206-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="b6206-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="b6206-103">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="b6206-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="b6206-104">Este elemento solo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="b6206-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="b6206-105">El tipo personalizado debe derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="b6206-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="b6206-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="b6206-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="b6206-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b6206-107">\<federationConfiguration></span></span>  
<span data-ttu-id="b6206-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6206-108">\<cookieHandler></span></span>  
<span data-ttu-id="b6206-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6206-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6206-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6206-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6206-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b6206-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b6206-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b6206-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6206-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6206-113">Attributes</span></span>  
  
|<span data-ttu-id="b6206-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b6206-114">Attribute</span></span>|<span data-ttu-id="b6206-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6206-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6206-116">type</span><span class="sxs-lookup"><span data-stu-id="b6206-116">type</span></span>|<span data-ttu-id="b6206-117">Especifica un tipo personalizado que deriva la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="b6206-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="b6206-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="b6206-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6206-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b6206-119">Child Elements</span></span>  
 <span data-ttu-id="b6206-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b6206-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6206-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b6206-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b6206-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6206-122">Element</span></span>|<span data-ttu-id="b6206-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6206-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6206-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="b6206-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="b6206-125">Configura el <xref:System.IdentityModel.Services.CookieHandler> que el <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="b6206-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6206-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6206-126">Remarks</span></span>  
 <span data-ttu-id="b6206-127">Al especificar un controlador de cookies personalizado estableciendo la `mode` atributo de la `<cookieHandler>` elemento en "Custom", debe especificar el tipo del controlador de cookies personalizado mediante la inclusión de un `<customCookieHandler>` elemento secundario que hace referencia al tipo de controlador de cookie.</span><span class="sxs-lookup"><span data-stu-id="b6206-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="b6206-128">Este elemento no puede ser que se especificó cuando la `mode` atributo está establecido en "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="b6206-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="b6206-129">Controladores de cookies personalizado deben derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="b6206-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="b6206-130">El `<customCookieHandler>` elemento representado por la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.</span><span class="sxs-lookup"><span data-stu-id="b6206-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6206-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6206-131">Example</span></span>  
 <span data-ttu-id="b6206-132">El ejemplo siguiente configura el SAM para usar un controlador de cookies personalizado del tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="b6206-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6206-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6206-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>

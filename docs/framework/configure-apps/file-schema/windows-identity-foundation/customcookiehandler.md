---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: df95e8d47d6a19e4fd488fa14bc771bc2c2b56b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="98565-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="98565-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="98565-103">Establece el tipo de controlador de cookie personalizado.</span><span class="sxs-lookup"><span data-stu-id="98565-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="98565-104">Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="98565-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="98565-105">El tipo personalizado debe derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="98565-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="98565-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="98565-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="98565-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="98565-107">\<federationConfiguration></span></span>  
<span data-ttu-id="98565-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="98565-108">\<cookieHandler></span></span>  
<span data-ttu-id="98565-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="98565-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98565-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98565-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98565-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="98565-111">Attributes and Elements</span></span>  
 <span data-ttu-id="98565-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="98565-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98565-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="98565-113">Attributes</span></span>  
  
|<span data-ttu-id="98565-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="98565-114">Attribute</span></span>|<span data-ttu-id="98565-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="98565-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98565-116">type</span><span class="sxs-lookup"><span data-stu-id="98565-116">type</span></span>|<span data-ttu-id="98565-117">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="98565-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="98565-118">Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="98565-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98565-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="98565-119">Child Elements</span></span>  
 <span data-ttu-id="98565-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="98565-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98565-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="98565-121">Parent Elements</span></span>  
  
|<span data-ttu-id="98565-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="98565-122">Element</span></span>|<span data-ttu-id="98565-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="98565-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98565-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="98565-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="98565-125">Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> utiliza para leer y escribir las cookies.</span><span class="sxs-lookup"><span data-stu-id="98565-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98565-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98565-126">Remarks</span></span>  
 <span data-ttu-id="98565-127">Al especificar un controlador de cookies personalizado estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Custom", debe especificar el tipo del controlador de cookie personalizado mediante la inclusión de un `<customCookieHandler>` elemento secundario que hace referencia al tipo de controlador de cookie.</span><span class="sxs-lookup"><span data-stu-id="98565-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="98565-128">Este elemento no puede ser especificado cuando el `mode` atributo está establecido en "Chunked" o "Default".</span><span class="sxs-lookup"><span data-stu-id="98565-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="98565-129">Controladores de cookie personalizado deben derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="98565-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="98565-130">El `<customCookieHandler>` elemento representado por la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.</span><span class="sxs-lookup"><span data-stu-id="98565-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98565-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98565-131">Example</span></span>  
 <span data-ttu-id="98565-132">En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizados del tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="98565-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98565-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="98565-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>

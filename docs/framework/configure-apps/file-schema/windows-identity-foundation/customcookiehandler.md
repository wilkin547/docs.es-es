---
description: 'Más información acerca de: <customCookieHandler>'
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 6b433769c429ed4149efb324d7c4b216d6042705
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664085"
---
# \<customCookieHandler>

<span data-ttu-id="0cd82-102">Establece el tipo de controlador de cookies personalizado.</span><span class="sxs-lookup"><span data-stu-id="0cd82-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="0cd82-103">Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "Custom".</span><span class="sxs-lookup"><span data-stu-id="0cd82-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="0cd82-104">El tipo personalizado se debe derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="0cd82-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="0cd82-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cd82-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cd82-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0cd82-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0cd82-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0cd82-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cd82-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0cd82-108">Attributes</span></span>  
  
|<span data-ttu-id="0cd82-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0cd82-109">Attribute</span></span>|<span data-ttu-id="0cd82-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cd82-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0cd82-111">type</span><span class="sxs-lookup"><span data-stu-id="0cd82-111">type</span></span>|<span data-ttu-id="0cd82-112">Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="0cd82-112">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="0cd82-113">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cd82-113">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cd82-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0cd82-114">Child Elements</span></span>  

 <span data-ttu-id="0cd82-115">None</span><span class="sxs-lookup"><span data-stu-id="0cd82-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cd82-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0cd82-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0cd82-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0cd82-117">Element</span></span>|<span data-ttu-id="0cd82-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cd82-118">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="0cd82-119">Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> utiliza para leer y escribir cookies.</span><span class="sxs-lookup"><span data-stu-id="0cd82-119">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cd82-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0cd82-120">Remarks</span></span>  

 <span data-ttu-id="0cd82-121">Cuando se especifica un controlador de cookies personalizado estableciendo el `mode` atributo del `<cookieHandler>` elemento en "Custom", se debe especificar el tipo del controlador de cookies personalizado incluyendo un `<customCookieHandler>` elemento secundario que haga referencia al tipo de controlador de cookies.</span><span class="sxs-lookup"><span data-stu-id="0cd82-121">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="0cd82-122">No se puede especificar este elemento cuando el `mode` atributo está establecido en "fragmentado" o "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="0cd82-122">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="0cd82-123">Los controladores de cookies personalizados deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.</span><span class="sxs-lookup"><span data-stu-id="0cd82-123">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="0cd82-124">El `<customCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.</span><span class="sxs-lookup"><span data-stu-id="0cd82-124">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cd82-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cd82-125">Example</span></span>  

 <span data-ttu-id="0cd82-126">En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizado de tipo `MyNamespace.MyCustomCookieHandler` .</span><span class="sxs-lookup"><span data-stu-id="0cd82-126">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cd82-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cd82-127">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>

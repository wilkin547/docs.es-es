---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252091"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="63122-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="63122-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="63122-102">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="63122-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="63122-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63122-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63122-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="63122-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="63122-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="63122-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="63122-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimsAuthenticationManager**</span><span class="sxs-lookup"><span data-stu-id="63122-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63122-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63122-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63122-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63122-108">Attributes and Elements</span></span>  
 <span data-ttu-id="63122-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63122-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63122-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="63122-110">Attributes</span></span>  
  
|<span data-ttu-id="63122-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="63122-111">Attribute</span></span>|<span data-ttu-id="63122-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63122-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="63122-113">type</span><span class="sxs-lookup"><span data-stu-id="63122-113">type</span></span>|<span data-ttu-id="63122-114">Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="63122-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="63122-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="63122-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63122-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63122-116">Child Elements</span></span>  
 <span data-ttu-id="63122-117">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia <xref:System.Security.Claims.ClaimsAuthenticationManager> a la clase `<claimsAuthenticationManager>` , el elemento no toma los elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthenticationManager> las clases derivadas de pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="63122-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63122-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63122-118">Parent Elements</span></span>  
  
|<span data-ttu-id="63122-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="63122-119">Element</span></span>|<span data-ttu-id="63122-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63122-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63122-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="63122-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="63122-122">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="63122-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63122-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63122-123">Remarks</span></span>  
 <span data-ttu-id="63122-124">El comportamiento predeterminado proporcionado a través <xref:System.Security.Claims.ClaimsAuthenticationManager> de la clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="63122-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="63122-125">Si no `type` se especifica ningún atributo o si `type` el atributo especifica <xref:System.Security.Claims.ClaimsAuthenticationManager> la clase, `<claimsAuthenticationManager>` el elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="63122-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="63122-126">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="63122-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="63122-127">Las clases derivadas pueden admitir la configuración a través `<claimsAuthenticationManager>` de elementos secundarios del elemento <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> invalidando el método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="63122-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="63122-128">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="63122-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="63122-129">El `<claimsAuthenticationManager>` elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="63122-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63122-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63122-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

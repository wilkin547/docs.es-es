---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152754"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="0bb17-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="0bb17-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="0bb17-102">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="0bb17-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="0bb17-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0bb17-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0bb17-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0bb17-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0bb17-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0bb17-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0bb17-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span><span class="sxs-lookup"><span data-stu-id="0bb17-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb17-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bb17-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bb17-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0bb17-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0bb17-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0bb17-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bb17-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0bb17-110">Attributes</span></span>  
  
|<span data-ttu-id="0bb17-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0bb17-111">Attribute</span></span>|<span data-ttu-id="0bb17-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bb17-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bb17-113">type</span><span class="sxs-lookup"><span data-stu-id="0bb17-113">type</span></span>|<span data-ttu-id="0bb17-114">Especifica un tipo personalizado que <xref:System.Security.Claims.ClaimsAuthenticationManager> deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="0bb17-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="0bb17-115">Para obtener más información `type` acerca de cómo especificar el atributo, vea [Referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="0bb17-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bb17-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0bb17-116">Child Elements</span></span>  
 <span data-ttu-id="0bb17-117">Si no `type` hay ningún atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthenticationManager> las clases derivadas de pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="0bb17-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bb17-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0bb17-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0bb17-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0bb17-119">Element</span></span>|<span data-ttu-id="0bb17-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bb17-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bb17-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0bb17-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="0bb17-122">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="0bb17-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bb17-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0bb17-123">Remarks</span></span>  
 <span data-ttu-id="0bb17-124">El comportamiento predeterminado <xref:System.Security.Claims.ClaimsAuthenticationManager> proporcionado a través de la clase se hace eco de las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="0bb17-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="0bb17-125">Si `type` no se especifica ningún `type` atributo o <xref:System.Security.Claims.ClaimsAuthenticationManager> si `<claimsAuthenticationManager>` el atributo especifica la clase, el elemento no toma elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="0bb17-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="0bb17-126">Puede especificar `type` el atributo para registrar un <xref:System.Security.Claims.ClaimsAuthenticationManager> tipo derivado de la clase para implementar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="0bb17-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="0bb17-127">Las clases derivadas pueden admitir `<claimsAuthenticationManager>` la configuración a <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> través de elementos secundarios del elemento reemplazando el método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="0bb17-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="0bb17-128">El esquema definido para los elementos secundarios depende del diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="0bb17-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="0bb17-129">El `<claimsAuthenticationManager>` elemento <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> establece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0bb17-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bb17-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0bb17-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

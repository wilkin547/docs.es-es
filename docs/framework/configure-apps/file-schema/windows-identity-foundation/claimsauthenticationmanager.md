---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158479"
---
# \<claimsAuthenticationManager>

<span data-ttu-id="ccc3d-101">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="ccc3d-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccc3d-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccc3d-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ccc3d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ccc3d-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccc3d-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="ccc3d-105">Attributes</span></span>  
  
|<span data-ttu-id="ccc3d-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="ccc3d-106">Attribute</span></span>|<span data-ttu-id="ccc3d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccc3d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccc3d-108">type</span><span class="sxs-lookup"><span data-stu-id="ccc3d-108">type</span></span>|<span data-ttu-id="ccc3d-109">Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="ccc3d-110">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="ccc3d-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccc3d-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ccc3d-111">Child Elements</span></span>  

 <span data-ttu-id="ccc3d-112">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccc3d-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ccc3d-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ccc3d-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccc3d-114">Element</span></span>|<span data-ttu-id="ccc3d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccc3d-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="ccc3d-116">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccc3d-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccc3d-117">Remarks</span></span>  

 <span data-ttu-id="ccc3d-118">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="ccc3d-119">Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="ccc3d-120">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="ccc3d-121">Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="ccc3d-122">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="ccc3d-123">El `<claimsAuthenticationManager>` elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ccc3d-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccc3d-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccc3d-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

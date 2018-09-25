---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074958"
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="d95b8-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="d95b8-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="d95b8-103">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="d95b8-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="d95b8-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d95b8-104">\<system.identityModel></span></span>  
<span data-ttu-id="d95b8-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d95b8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d95b8-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="d95b8-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d95b8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d95b8-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d95b8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d95b8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d95b8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d95b8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d95b8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d95b8-110">Attributes</span></span>  
  
|<span data-ttu-id="d95b8-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d95b8-111">Attribute</span></span>|<span data-ttu-id="d95b8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d95b8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d95b8-113">type</span><span class="sxs-lookup"><span data-stu-id="d95b8-113">type</span></span>|<span data-ttu-id="d95b8-114">Especifica un tipo personalizado que deriva la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="d95b8-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="d95b8-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado].</span><span class="sxs-lookup"><span data-stu-id="d95b8-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d95b8-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d95b8-116">Child Elements</span></span>  
 <span data-ttu-id="d95b8-117">Si no hay ningún `type` atributo, o si el `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> puede definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="d95b8-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d95b8-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d95b8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d95b8-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d95b8-119">Element</span></span>|<span data-ttu-id="d95b8-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d95b8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d95b8-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d95b8-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="d95b8-122">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="d95b8-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d95b8-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d95b8-123">Remarks</span></span>  
 <span data-ttu-id="d95b8-124">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="d95b8-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="d95b8-125">Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d95b8-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="d95b8-126">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="d95b8-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="d95b8-127">Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="d95b8-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="d95b8-128">El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="d95b8-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="d95b8-129">El `<claimsAuthenticationManager>` conjuntos de elementos del <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d95b8-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d95b8-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d95b8-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```

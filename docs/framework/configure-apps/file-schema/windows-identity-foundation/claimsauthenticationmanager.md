---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941827"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="adf5d-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="adf5d-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="adf5d-102">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="adf5d-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="adf5d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="adf5d-103">\<system.identityModel></span></span>  
<span data-ttu-id="adf5d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="adf5d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="adf5d-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="adf5d-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf5d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adf5d-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adf5d-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="adf5d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="adf5d-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="adf5d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adf5d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="adf5d-109">Attributes</span></span>  
  
|<span data-ttu-id="adf5d-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="adf5d-110">Attribute</span></span>|<span data-ttu-id="adf5d-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="adf5d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="adf5d-112">type</span><span class="sxs-lookup"><span data-stu-id="adf5d-112">type</span></span>|<span data-ttu-id="adf5d-113">Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="adf5d-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="adf5d-114">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="adf5d-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adf5d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="adf5d-115">Child Elements</span></span>  
 <span data-ttu-id="adf5d-116">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia <xref:System.Security.Claims.ClaimsAuthenticationManager> a la clase `<claimsAuthenticationManager>` , el elemento no toma los elementos secundarios; sin embargo, <xref:System.Security.Claims.ClaimsAuthenticationManager> las clases derivadas de pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="adf5d-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adf5d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="adf5d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="adf5d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="adf5d-118">Element</span></span>|<span data-ttu-id="adf5d-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="adf5d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adf5d-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="adf5d-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="adf5d-121">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="adf5d-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adf5d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adf5d-122">Remarks</span></span>  
 <span data-ttu-id="adf5d-123">El comportamiento predeterminado proporcionado a través <xref:System.Security.Claims.ClaimsAuthenticationManager> de la clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="adf5d-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="adf5d-124">Si no `type` se especifica ningún atributo o si `type` el atributo especifica <xref:System.Security.Claims.ClaimsAuthenticationManager> la clase, `<claimsAuthenticationManager>` el elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="adf5d-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="adf5d-125">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="adf5d-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="adf5d-126">Las clases derivadas pueden admitir la configuración a través `<claimsAuthenticationManager>` de elementos secundarios del elemento <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> invalidando el método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="adf5d-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="adf5d-127">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="adf5d-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="adf5d-128">El `<claimsAuthenticationManager>` elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="adf5d-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adf5d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adf5d-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

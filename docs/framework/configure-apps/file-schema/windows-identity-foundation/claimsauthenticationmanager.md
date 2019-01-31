---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255190"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="fe0b1-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="fe0b1-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="fe0b1-102">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="fe0b1-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fe0b1-103">\<system.identityModel></span></span>  
<span data-ttu-id="fe0b1-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fe0b1-104">\<identityConfiguration></span></span>  
<span data-ttu-id="fe0b1-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="fe0b1-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe0b1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe0b1-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe0b1-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fe0b1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fe0b1-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe0b1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="fe0b1-109">Attributes</span></span>  
  
|<span data-ttu-id="fe0b1-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="fe0b1-110">Attribute</span></span>|<span data-ttu-id="fe0b1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe0b1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe0b1-112">type</span><span class="sxs-lookup"><span data-stu-id="fe0b1-112">type</span></span>|<span data-ttu-id="fe0b1-113">Especifica un tipo personalizado que deriva la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="fe0b1-114">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado].</span><span class="sxs-lookup"><span data-stu-id="fe0b1-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe0b1-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fe0b1-115">Child Elements</span></span>  
 <span data-ttu-id="fe0b1-116">Si no hay ningún `type` atributo, o si el `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> puede definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fe0b1-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fe0b1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fe0b1-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe0b1-118">Element</span></span>|<span data-ttu-id="fe0b1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe0b1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe0b1-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fe0b1-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="fe0b1-121">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe0b1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe0b1-122">Remarks</span></span>  
 <span data-ttu-id="fe0b1-123">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="fe0b1-124">Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="fe0b1-125">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="fe0b1-126">Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="fe0b1-127">El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="fe0b1-128">El `<claimsAuthenticationManager>` conjuntos de elementos del <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fe0b1-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe0b1-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe0b1-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

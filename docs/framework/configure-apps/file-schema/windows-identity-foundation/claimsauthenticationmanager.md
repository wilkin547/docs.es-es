---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="b0caa-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="b0caa-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="b0caa-103">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="b0caa-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="b0caa-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b0caa-104">\<system.identityModel></span></span>  
<span data-ttu-id="b0caa-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b0caa-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b0caa-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="b0caa-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0caa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0caa-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0caa-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0caa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b0caa-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0caa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0caa-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0caa-110">Attributes</span></span>  
  
|<span data-ttu-id="b0caa-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0caa-111">Attribute</span></span>|<span data-ttu-id="b0caa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0caa-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0caa-113">type</span><span class="sxs-lookup"><span data-stu-id="b0caa-113">type</span></span>|<span data-ttu-id="b0caa-114">Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="b0caa-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="b0caa-115">Para obtener más información sobre cómo especificar el `type` atributo, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="b0caa-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0caa-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0caa-116">Child Elements</span></span>  
 <span data-ttu-id="b0caa-117">Si no hay ningún `type` atributo, o si la `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> puede definir los elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="b0caa-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0caa-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0caa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b0caa-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0caa-119">Element</span></span>|<span data-ttu-id="b0caa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0caa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0caa-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b0caa-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="b0caa-122">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="b0caa-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0caa-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0caa-123">Remarks</span></span>  
 <span data-ttu-id="b0caa-124">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase eco de las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="b0caa-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="b0caa-125">Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthenticationManager>` elemento no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b0caa-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="b0caa-126">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="b0caa-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b0caa-127">Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="b0caa-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b0caa-128">El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="b0caa-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="b0caa-129">El `<claimsAuthenticationManager>` conjuntos de elementos del <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b0caa-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0caa-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0caa-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```

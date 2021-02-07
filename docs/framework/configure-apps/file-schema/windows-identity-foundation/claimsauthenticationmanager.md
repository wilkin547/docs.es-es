---
description: 'Más información acerca de: <claimsAuthenticationManager>'
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 5a94861d6b2684b9f66c7d5e14f72aa419a0c66f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664254"
---
# \<claimsAuthenticationManager>

<span data-ttu-id="10b93-102">Registra un administrador de autenticación de notificaciones para las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="10b93-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="10b93-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10b93-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10b93-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="10b93-104">Attributes and Elements</span></span>  

 <span data-ttu-id="10b93-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="10b93-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10b93-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="10b93-106">Attributes</span></span>  
  
|<span data-ttu-id="10b93-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="10b93-107">Attribute</span></span>|<span data-ttu-id="10b93-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="10b93-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10b93-109">type</span><span class="sxs-lookup"><span data-stu-id="10b93-109">type</span></span>|<span data-ttu-id="10b93-110">Especifica un tipo personalizado que deriva de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase.</span><span class="sxs-lookup"><span data-stu-id="10b93-110">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="10b93-111">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="10b93-111">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10b93-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="10b93-112">Child Elements</span></span>  

 <span data-ttu-id="10b93-113">Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthenticationManager> pueden definir elementos de configuración secundarios.</span><span class="sxs-lookup"><span data-stu-id="10b93-113">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10b93-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="10b93-114">Parent Elements</span></span>  
  
|<span data-ttu-id="10b93-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="10b93-115">Element</span></span>|<span data-ttu-id="10b93-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="10b93-116">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="10b93-117">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="10b93-117">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10b93-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10b93-118">Remarks</span></span>  

 <span data-ttu-id="10b93-119">El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase repite las notificaciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="10b93-119">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="10b93-120">Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthenticationManager>` elemento no toma los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="10b93-120">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="10b93-121">Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase para implementar el comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="10b93-121">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="10b93-122">Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthenticationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> método para controlar estos elementos.</span><span class="sxs-lookup"><span data-stu-id="10b93-122">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="10b93-123">El esquema definido para los elementos secundarios es hasta el diseñador de la clase.</span><span class="sxs-lookup"><span data-stu-id="10b93-123">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="10b93-124">El `<claimsAuthenticationManager>` elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="10b93-124">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10b93-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10b93-125">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

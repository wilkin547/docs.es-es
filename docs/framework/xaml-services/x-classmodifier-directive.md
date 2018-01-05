---
title: x:ClassModifier (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: "22"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a4918e23a915ee07eace388ea2cea512c2e479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="71276-102">x:ClassModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="71276-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="71276-103">Modifica el comportamiento de compilación de XAML cuando `x:Class` también se proporciona.</span><span class="sxs-lookup"><span data-stu-id="71276-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="71276-104">En concreto, en lugar de crear un parcial `class` que tiene un `Public` (valor predeterminado), nivel de acceso proporcionado `x:Class` se crea con un `NotPublic` nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="71276-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="71276-105">Este comportamiento afecta al nivel de acceso para la clase en los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="71276-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="71276-106">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="71276-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="71276-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="71276-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71276-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="71276-108">*NotPublic*</span></span>|<span data-ttu-id="71276-109">La cadena exacta debe pasar para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía según el lenguaje de programación de código subyacente que usa.</span><span class="sxs-lookup"><span data-stu-id="71276-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="71276-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="71276-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="71276-111">Dependencias</span><span class="sxs-lookup"><span data-stu-id="71276-111">Dependencies</span></span>  
 <span data-ttu-id="71276-112">[x: Class](../../../docs/framework/xaml-services/x-class-directive.md) también se debe proporcionar en el mismo elemento, y ese elemento debe ser el elemento raíz en una página.</span><span class="sxs-lookup"><span data-stu-id="71276-112">[x:Class](../../../docs/framework/xaml-services/x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="71276-113">Para obtener más información, consulte [ \[MS-XAML\] sección 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="71276-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71276-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71276-114">Remarks</span></span>  
 <span data-ttu-id="71276-115">El valor de `x:ClassModifier` en los servicios XAML de .NET Framework uso varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="71276-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="71276-116">La cadena que se va a utilizar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, y si ese idioma distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="71276-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="71276-117">Para [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], la cadena para pasar para designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `internal`.</span><span class="sxs-lookup"><span data-stu-id="71276-117">For [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="71276-118">Para [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], la cadena para pasar para designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `Friend`.</span><span class="sxs-lookup"><span data-stu-id="71276-118">For [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)], the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="71276-119">Para [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], ningún destino existe compatibles con la compilación XAML; por lo tanto, el valor para pasar no está especificado.</span><span class="sxs-lookup"><span data-stu-id="71276-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="71276-120">También puede especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` en [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); sin embargo, especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> con poca frecuencia se hace así porque <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ya es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="71276-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], `Public` in [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="71276-121">Otros valores con el código de usuario equivalente-nivel de acceso de las restricciones, como `private` en [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], no son relevantes para `x:ClassModifier` porque no se admiten referencias de clase anidada en XAML y por lo tanto, la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificador tiene el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="71276-121">Other values with equivalent user code access-level restrictions, such as `private` in [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)], are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="71276-122">Notas de seguridad</span><span class="sxs-lookup"><span data-stu-id="71276-122">Security Notes</span></span>  
 <span data-ttu-id="71276-123">El nivel de acceso, tal y como declara en `x:ClassModifier` sigue estando sujeto a interpretación por marcos determinados y sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="71276-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="71276-124">WPF incluye funciones para cargar y crear instancias de tipos donde `x:ClassModifier` es `internal`, si se hace referencia a esa clase desde un recurso WPF a través de una referencia de URI de paquete.</span><span class="sxs-lookup"><span data-stu-id="71276-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="71276-125">Como consecuencia de este caso y potencialmente otros similares implementado por otros marcos, no debe confiar exclusivamente en `x:ClassModifier` para bloquear la creación de instancias de todas las posibles intentos.</span><span class="sxs-lookup"><span data-stu-id="71276-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71276-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="71276-126">See Also</span></span>  
 [<span data-ttu-id="71276-127">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="71276-127">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="71276-128">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="71276-128">Code-Behind and XAML in WPF</span></span>](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [<span data-ttu-id="71276-129">x:FieldModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="71276-129">x:FieldModifier Directive</span></span>](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)  
 [<span data-ttu-id="71276-130">Seguridad (WPF)</span><span class="sxs-lookup"><span data-stu-id="71276-130">Security (WPF)</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="71276-131">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="71276-131">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)

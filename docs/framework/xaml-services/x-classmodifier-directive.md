---
title: x:ClassModifier (Directiva)
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837238"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="9a994-102">x:ClassModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="9a994-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="9a994-103">Modifica el comportamiento de la compilación de XAML cuando también se proporciona `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="9a994-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="9a994-104">En concreto, en lugar de crear una `class` parcial que tenga un nivel de acceso `Public` (valor predeterminado), el `x:Class` proporcionado se crea con un nivel de acceso `NotPublic`.</span><span class="sxs-lookup"><span data-stu-id="9a994-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="9a994-105">Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="9a994-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9a994-106">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="9a994-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9a994-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="9a994-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a994-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="9a994-108">*NotPublic*</span></span>|<span data-ttu-id="9a994-109">La cadena exacta que se va a pasar para especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> frente a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varía en función del lenguaje de programación de código subyacente que se use.</span><span class="sxs-lookup"><span data-stu-id="9a994-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="9a994-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="9a994-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="9a994-111">Dependencias</span><span class="sxs-lookup"><span data-stu-id="9a994-111">Dependencies</span></span>  
 <span data-ttu-id="9a994-112">[x:Class](x-class-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página.</span><span class="sxs-lookup"><span data-stu-id="9a994-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="9a994-113">Para obtener más información, vea [\[sección de\] MS-XAML 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="9a994-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a994-114">Notas</span><span class="sxs-lookup"><span data-stu-id="9a994-114">Remarks</span></span>  
 <span data-ttu-id="9a994-115">El valor de `x:ClassModifier` en .NET Framework uso de servicios XAML varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="9a994-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="9a994-116">La cadena que se va a usar depende de cómo implementa cada lenguaje su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, y si ese idioma distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9a994-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="9a994-117">En C#, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `internal`.</span><span class="sxs-lookup"><span data-stu-id="9a994-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="9a994-118">En el caso de Microsoft Visual Basic .NET, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `Friend`.</span><span class="sxs-lookup"><span data-stu-id="9a994-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="9a994-119">Para C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.</span><span class="sxs-lookup"><span data-stu-id="9a994-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="9a994-120">También puede especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` en C#, `Public` en Visual Basic); sin embargo, la especificación de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se realiza con poca frecuencia porque <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ya es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9a994-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="9a994-121">Otros valores con restricciones de nivel de acceso del código de usuario equivalentes, C#como `private` en, no son relevantes para `x:ClassModifier` porque las referencias de clase anidadas no se admiten en XAML y, por tanto, el modificador <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> tiene el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="9a994-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="9a994-122">Notas de seguridad</span><span class="sxs-lookup"><span data-stu-id="9a994-122">Security Notes</span></span>  
 <span data-ttu-id="9a994-123">El nivel de acceso tal y como se declara en `x:ClassModifier` sigue sujeto a la interpretación de los marcos concretos y sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="9a994-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="9a994-124">WPF incluye funcionalidades para cargar y crear instancias de tipos donde se `internal``x:ClassModifier`, si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de Pack URI.</span><span class="sxs-lookup"><span data-stu-id="9a994-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="9a994-125">Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se basa exclusivamente en `x:ClassModifier` para bloquear todos los intentos de creación de instancias posibles.</span><span class="sxs-lookup"><span data-stu-id="9a994-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a994-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a994-126">See also</span></span>

- [<span data-ttu-id="9a994-127">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="9a994-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="9a994-128">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="9a994-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="9a994-129">x:FieldModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="9a994-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="9a994-130">Seguridad (WPF)</span><span class="sxs-lookup"><span data-stu-id="9a994-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="9a994-131">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="9a994-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)

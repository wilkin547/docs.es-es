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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484746"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="54b38-102">x:ClassModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="54b38-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="54b38-103">Modifica el comportamiento de la compilación `x:Class` de XAML cuando también se proporciona.</span><span class="sxs-lookup"><span data-stu-id="54b38-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="54b38-104">En concreto, en lugar de crear una `class` parcial que tenga `Public` un nivel de acceso (valor predeterminado), `x:Class` el proporcionado se crea `NotPublic` con un nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="54b38-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="54b38-105">Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="54b38-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="54b38-106">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="54b38-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="54b38-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="54b38-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54b38-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="54b38-108">*NotPublic*</span></span>|<span data-ttu-id="54b38-109">Cadena exacta que se va a pasar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , en función del lenguaje de programación de código subyacente que se utilice.</span><span class="sxs-lookup"><span data-stu-id="54b38-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="54b38-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="54b38-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="54b38-111">Dependencias</span><span class="sxs-lookup"><span data-stu-id="54b38-111">Dependencies</span></span>  
 <span data-ttu-id="54b38-112">[x:Class](x-class-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página.</span><span class="sxs-lookup"><span data-stu-id="54b38-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="54b38-113">Para obtener más información, vea [ \[la sección\] MS-XAML 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="54b38-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54b38-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54b38-114">Remarks</span></span>  
 <span data-ttu-id="54b38-115">El valor de `x:ClassModifier` en .NET Framework uso de servicios XAML varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="54b38-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="54b38-116">La cadena que se va a usar depende de cómo cada lenguaje <xref:System.CodeDom.Compiler.CodeDomProvider> implementa su y los convertidores de tipos que devuelve para definir <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> los <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>significados para y, y si ese idioma distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="54b38-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="54b38-117">Para C#, la cadena que <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> se va a pasar a Designate es. `internal`</span><span class="sxs-lookup"><span data-stu-id="54b38-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="54b38-118">Para Microsoft Visual Basic .net, la cadena que <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> se va a pasar a Design es. `Friend`</span><span class="sxs-lookup"><span data-stu-id="54b38-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="54b38-119">Para C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.</span><span class="sxs-lookup"><span data-stu-id="54b38-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="54b38-120"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> También puede especificar (`public` en C#, `Public` en Visual Basic); sin embargo, la especificación <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> de se realiza con poca frecuencia <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> porque ya es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="54b38-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="54b38-121">Otros valores con restricciones de nivel de acceso del código de usuario `private` equivalentes C#, como en, no `x:ClassModifier` son pertinentes para porque las referencias de clase anidadas no se admiten en <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> XAML y, por lo tanto, el modificador tiene el mismo efecto .</span><span class="sxs-lookup"><span data-stu-id="54b38-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="54b38-122">Notas de seguridad</span><span class="sxs-lookup"><span data-stu-id="54b38-122">Security Notes</span></span>  
 <span data-ttu-id="54b38-123">El nivel de acceso tal y `x:ClassModifier` como se declara en todavía está sujeto a la interpretación de los marcos concretos y sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="54b38-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="54b38-124">WPF incluye funcionalidades para cargar y crear instancias de tipos `x:ClassModifier` donde `internal`es, si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de pack uri.</span><span class="sxs-lookup"><span data-stu-id="54b38-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="54b38-125">Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se base `x:ClassModifier` exclusivamente en bloquear todos los intentos de creación de instancias posibles.</span><span class="sxs-lookup"><span data-stu-id="54b38-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b38-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b38-126">See also</span></span>

- [<span data-ttu-id="54b38-127">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="54b38-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="54b38-128">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="54b38-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="54b38-129">x:FieldModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="54b38-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="54b38-130">Seguridad (WPF)</span><span class="sxs-lookup"><span data-stu-id="54b38-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="54b38-131">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="54b38-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)

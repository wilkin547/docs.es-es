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
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433275"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="6b628-102">x:ClassModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="6b628-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="6b628-103">Modifica el comportamiento `x:Class` de compilación XAML cuando también se proporciona.</span><span class="sxs-lookup"><span data-stu-id="6b628-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="6b628-104">Específicamente, en lugar `class` de crear `Public` un parcial que tenga `x:Class` un nivel `NotPublic` de acceso (el valor predeterminado), el proporcionado se crea con un nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="6b628-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="6b628-105">Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="6b628-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="6b628-106">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="6b628-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="6b628-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="6b628-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="6b628-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="6b628-108">*NotPublic*</span></span>|<span data-ttu-id="6b628-109">La cadena exacta que <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> va a pasar para especificar la cadena varíe, en función del lenguaje de programación de código subyacente que utilice.</span><span class="sxs-lookup"><span data-stu-id="6b628-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="6b628-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="6b628-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="6b628-111">Dependencias</span><span class="sxs-lookup"><span data-stu-id="6b628-111">Dependencies</span></span>

<span data-ttu-id="6b628-112">[x:Class](xclass-directive.md) también debe proporcionarse en el mismo elemento y ese elemento debe ser el elemento raíz de una página.</span><span class="sxs-lookup"><span data-stu-id="6b628-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="6b628-113">Para obtener más información, consulte [ \[MS-XAML\] Sección 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="6b628-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="6b628-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b628-114">Remarks</span></span>

<span data-ttu-id="6b628-115">El valor `x:ClassModifier` del uso de los servicios XAML de .NET varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="6b628-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="6b628-116">La cadena que se va a <xref:System.CodeDom.Compiler.CodeDomProvider> usar depende de cómo cada lenguaje implementa <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>su y los convertidores de tipos que devuelve para definir los significados para y , y si ese lenguaje distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6b628-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="6b628-117">Para C- , la cadena <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `internal`que se va a pasar para designar es .</span><span class="sxs-lookup"><span data-stu-id="6b628-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="6b628-118">Para Microsoft Visual Basic .NET, la <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`cadena que se va a pasar para designar es .</span><span class="sxs-lookup"><span data-stu-id="6b628-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="6b628-119">Para C++/CLI, no existen destinos que admitan la compilación de XAML; por lo tanto, el valor que se debe pasar no está especificado.</span><span class="sxs-lookup"><span data-stu-id="6b628-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="6b628-120">También puede <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> especificar`public` ( en `Public` C-, en Visual Basic); sin embargo, especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> hace con poca frecuencia porque ya es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6b628-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="6b628-121">Otros valores con restricciones de nivel de `private` acceso de código de `x:ClassModifier` usuario equivalentes, como en C-, <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> no son relevantes para porque las referencias de clase anidadas no se admiten en XAML y, por lo tanto, el modificador tiene el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="6b628-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="6b628-122">Notas de seguridad</span><span class="sxs-lookup"><span data-stu-id="6b628-122">Security Notes</span></span>

<span data-ttu-id="6b628-123">El nivel de `x:ClassModifier` acceso declarado en sigue estando sujeto a la interpretación de marcos particulares y sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="6b628-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="6b628-124">WPFWPF incluye capacidades para `x:ClassModifier` `internal`cargar y crear instancias de tipos donde está , si se hace referencia a esa clase desde un recurso WPFWPF a través de una referencia URI de paquete.</span><span class="sxs-lookup"><span data-stu-id="6b628-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="6b628-125">Como consecuencia de este caso y potencialmente otros como él implementados por `x:ClassModifier` otros marcos, no se basan exclusivamente en bloquear todos los posibles intentos de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="6b628-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b628-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b628-126">See also</span></span>

- [<span data-ttu-id="6b628-127">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="6b628-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="6b628-128">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="6b628-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="6b628-129">x:FieldModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="6b628-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="6b628-130">Seguridad (WPF)</span><span class="sxs-lookup"><span data-stu-id="6b628-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="6b628-131">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="6b628-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)

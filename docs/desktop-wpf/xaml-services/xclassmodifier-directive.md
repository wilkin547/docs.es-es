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
ms.openlocfilehash: 73732a06029cca3a4c6c6d82762d5263c5b8c955
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544822"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="e23ce-102">x:ClassModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="e23ce-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="e23ce-103">Modifica el comportamiento de la compilación de XAML cuando `x:Class` también se proporciona.</span><span class="sxs-lookup"><span data-stu-id="e23ce-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="e23ce-104">En concreto, en lugar de crear una parcial `class` que tenga un `Public` nivel de acceso (valor predeterminado), el proporcionado `x:Class` se crea con un `NotPublic` nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="e23ce-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="e23ce-105">Este comportamiento afecta al nivel de acceso de la clase en los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="e23ce-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="e23ce-106">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="e23ce-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="e23ce-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="e23ce-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="e23ce-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="e23ce-108">*NotPublic*</span></span>|<span data-ttu-id="e23ce-109">Cadena exacta que se va a pasar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> a <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , en función del lenguaje de programación de código subyacente que se utilice.</span><span class="sxs-lookup"><span data-stu-id="e23ce-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="e23ce-110">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="e23ce-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="e23ce-111">Dependencias</span><span class="sxs-lookup"><span data-stu-id="e23ce-111">Dependencies</span></span>

<span data-ttu-id="e23ce-112">[x:Class](xclass-directive.md) también debe proporcionarse en el mismo elemento y dicho elemento debe ser el elemento raíz de una página.</span><span class="sxs-lookup"><span data-stu-id="e23ce-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="e23ce-113">Para obtener más información, vea [ \[ la \] sección MS-XAML 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="e23ce-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="e23ce-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e23ce-114">Remarks</span></span>

<span data-ttu-id="e23ce-115">El valor de `x:ClassModifier` en el uso de los servicios XAML de .net varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="e23ce-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="e23ce-116">La cadena que se va a usar depende de cómo cada lenguaje implementa su <xref:System.CodeDom.Compiler.CodeDomProvider> y los convertidores de tipos que devuelve para definir los significados para <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> y <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> , y si ese idioma distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e23ce-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="e23ce-117">En C#, la cadena que se va a pasar a designar <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `internal` .</span><span class="sxs-lookup"><span data-stu-id="e23ce-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="e23ce-118">Para Microsoft Visual Basic .NET, la cadena que se va a pasar a Design <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> es `Friend` .</span><span class="sxs-lookup"><span data-stu-id="e23ce-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="e23ce-119">En C++/CLI, no existe ningún destino que admita la compilación de XAML. por lo tanto, el valor que se va a pasar no está especificado.</span><span class="sxs-lookup"><span data-stu-id="e23ce-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="e23ce-120">También puede especificar <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ( `public` en C#, `Public` en Visual Basic); sin embargo, la especificación de <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> se realiza con poca frecuencia porque <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> ya es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e23ce-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="e23ce-121">Otros valores con restricciones de nivel de acceso del código de usuario equivalentes, como `private` en C#, no son pertinentes para `x:ClassModifier` porque las referencias de clase anidadas no se admiten en XAML y, por lo tanto, el <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modificador tiene el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="e23ce-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="e23ce-122">Notas de seguridad</span><span class="sxs-lookup"><span data-stu-id="e23ce-122">Security Notes</span></span>

<span data-ttu-id="e23ce-123">El nivel de acceso tal y como se declara en `x:ClassModifier` todavía está sujeto a la interpretación de los marcos concretos y sus capacidades.</span><span class="sxs-lookup"><span data-stu-id="e23ce-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="e23ce-124">WPF incluye funcionalidades para cargar y crear instancias de tipos donde `x:ClassModifier` es `internal` , si se hace referencia a esa clase desde un recurso de WPF a través de una referencia de pack uri.</span><span class="sxs-lookup"><span data-stu-id="e23ce-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="e23ce-125">Como consecuencia de este caso, y potencialmente otros como el que implementan otros marcos de trabajo, no se base exclusivamente en `x:ClassModifier` bloquear todos los intentos de creación de instancias posibles.</span><span class="sxs-lookup"><span data-stu-id="e23ce-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e23ce-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e23ce-126">See also</span></span>

- [<span data-ttu-id="e23ce-127">x:Class (Directiva)</span><span class="sxs-lookup"><span data-stu-id="e23ce-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="e23ce-128">Código subyacente y XAML en WPF</span><span class="sxs-lookup"><span data-stu-id="e23ce-128">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="e23ce-129">x:FieldModifier (Directiva)</span><span class="sxs-lookup"><span data-stu-id="e23ce-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="e23ce-130">Seguridad (WPF)</span><span class="sxs-lookup"><span data-stu-id="e23ce-130">Security (WPF)</span></span>](/dotnet/desktop/wpf/security-wpf)
- [<span data-ttu-id="e23ce-131">Tipos migrados de WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="e23ce-131">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)

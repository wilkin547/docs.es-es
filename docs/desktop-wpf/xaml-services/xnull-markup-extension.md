---
title: x:Null (Extensión de marcado)
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: f4971d61d11ec14eaeac2d2f202353e4921b9325
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549449"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="a0001-102">x:Null (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="a0001-102">x:Null Markup Extension</span></span>

<span data-ttu-id="a0001-103">Especifica `null` como un valor para un miembro XAML.</span><span class="sxs-lookup"><span data-stu-id="a0001-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="a0001-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="a0001-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="a0001-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0001-105">Remarks</span></span>

<span data-ttu-id="a0001-106">La palabra clave para una referencia nula en C# y C++ es NULL.</span><span class="sxs-lookup"><span data-stu-id="a0001-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="a0001-107">La palabra clave de Microsoft Visual Basic para una referencia nula es `Nothing` , pero siempre se usa `{x:Null}` como el uso de XAML independientemente del lenguaje de código subyacente que se ASOCIE a XAML.</span><span class="sxs-lookup"><span data-stu-id="a0001-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="a0001-108">La `x:Null` extensión de marcado no tiene propiedades que se puedan establecer.</span><span class="sxs-lookup"><span data-stu-id="a0001-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="a0001-109">Un uso nulo suele estar asociado a la exposición de miembro XAML de un <xref:System.Nullable%601> valor CLR.</span><span class="sxs-lookup"><span data-stu-id="a0001-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="a0001-110">La `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, utiliza llaves ( `{,}` ) para escapar el control de los valores de atributo para que no sean literales o referencias del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a0001-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="a0001-111">La sintaxis de atributo es la sintaxis que se usa con más frecuencia con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="a0001-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="a0001-112">Técnicamente, una sintaxis de elementos `<x:Null />` de objeto es posible, pero rara vez se usa porque la `x:Null` extensión de marcado no tiene ningún parámetro posicional o de construcción.</span><span class="sxs-lookup"><span data-stu-id="a0001-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="a0001-113">Para obtener información sobre las extensiones de marcado, vea [extensiones de marcado y XAML de WPF](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span><span class="sxs-lookup"><span data-stu-id="a0001-113">For information about markup extensions, see [Markup Extensions and WPF XAML](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml).</span></span>

<span data-ttu-id="a0001-114">En los servicios XAML de .NET, el control de esta extensión de marcado se define mediante la <xref:System.Windows.Markup.NullExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="a0001-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a0001-115">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="a0001-115">WPF Usage Notes</span></span>

<span data-ttu-id="a0001-116">Tenga en cuenta que `null` no es necesariamente el valor no establecido inicial para una propiedad de dependencia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="a0001-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="a0001-117">El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en metadatos específicos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0001-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="a0001-118">Muchas propiedades de dependencia no aceptan `null` como valor, ya sea a través de marcado o código debido a sus implementaciones de devolución de llamada de validación.</span><span class="sxs-lookup"><span data-stu-id="a0001-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="a0001-119">Para obtener más información sobre las propiedades de dependencia, vea [Introducción a las propiedades de dependencia](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span><span class="sxs-lookup"><span data-stu-id="a0001-119">For more information about dependency properties, see [Dependency Properties Overview](/dotnet/desktop/wpf/advanced/dependency-properties-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0001-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0001-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="a0001-121">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a0001-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="a0001-122">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="a0001-122">Markup Extensions and WPF XAML</span></span>](/dotnet/desktop/wpf/advanced/markup-extensions-and-wpf-xaml)

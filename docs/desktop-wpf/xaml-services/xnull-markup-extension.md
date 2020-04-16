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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432699"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="d4a26-102">x:Null (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="d4a26-102">x:Null Markup Extension</span></span>

<span data-ttu-id="d4a26-103">Especifica `null` como un valor para un miembro XAML.</span><span class="sxs-lookup"><span data-stu-id="d4a26-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="d4a26-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="d4a26-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="d4a26-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4a26-105">Remarks</span></span>

<span data-ttu-id="d4a26-106">La palabra clave para una referencia nula en C- y C++ es null.</span><span class="sxs-lookup"><span data-stu-id="d4a26-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="d4a26-107">La palabra clave de Microsoft `Nothing`Visual Basic para `{x:Null}` una referencia nula es , pero siempre se usa como el uso XAML independientemente del lenguaje de código subyacente que asocie con el XAML.</span><span class="sxs-lookup"><span data-stu-id="d4a26-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="d4a26-108">La `x:Null` extensión de marcado no tiene propiedades configurables.</span><span class="sxs-lookup"><span data-stu-id="d4a26-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="d4a26-109">Un uso nulo a menudo se asocia <xref:System.Nullable%601> con la exposición de miembroXAML de un valor CLR.</span><span class="sxs-lookup"><span data-stu-id="d4a26-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="d4a26-110">La `x:Null` extensión de marcado, como todas las`{,}`extensiones de marcado XAML, usa las llaves ( ) para escapar del control de los valores de atributo que no sean literales o referencias de controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="d4a26-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="d4a26-111">Sintaxis de atributo es la sintaxis más utilizada con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="d4a26-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="d4a26-112">Una sintaxis `<x:Null />` de elemento de objeto es técnicamente posible, pero rara vez se utiliza porque la `x:Null` extensión de marcado no tiene parámetros posicionales ni argumentos de construcción.</span><span class="sxs-lookup"><span data-stu-id="d4a26-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="d4a26-113">Para obtener información acerca de las extensiones de marcado, vea [Extensiones](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)de marcado y XAML de WPF .</span><span class="sxs-lookup"><span data-stu-id="d4a26-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="d4a26-114">En los servicios XAML de .NET, la <xref:System.Windows.Markup.NullExtension> clase define el control de esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="d4a26-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="d4a26-115">Notas de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="d4a26-115">WPF Usage Notes</span></span>

<span data-ttu-id="d4a26-116">Tenga `null` en cuenta que no es necesariamente el valor inicial de unset para una propiedad de dependencia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="d4a26-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="d4a26-117">El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en metadatos específicos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d4a26-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="d4a26-118">Muchas propiedades de `null` dependencia no se aceptan como un valor, ya sea a través de marcado o código debido a sus implementaciones de devolución de llamada de validación.</span><span class="sxs-lookup"><span data-stu-id="d4a26-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="d4a26-119">Para obtener más información acerca de las propiedades de dependencia, vea [Información general sobre propiedades](../../framework/wpf/advanced/dependency-properties-overview.md)de dependencia .</span><span class="sxs-lookup"><span data-stu-id="d4a26-119">For more information about dependency properties, see [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4a26-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4a26-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="d4a26-121">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d4a26-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="d4a26-122">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="d4a26-122">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

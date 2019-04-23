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
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100813"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="2e7a4-102">x:Null (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="2e7a4-102">x:Null Markup Extension</span></span>
<span data-ttu-id="2e7a4-103">Especifica `null` como un valor para un miembro XAML.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2e7a4-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="2e7a4-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="2e7a4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e7a4-105">Remarks</span></span>  
 <span data-ttu-id="2e7a4-106">La palabra clave para una referencia nula en C# y [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] es null.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="2e7a4-107">La palabra clave de Microsoft Visual Basic para una referencia nula es `Nothing`, pero siempre usar `{x:Null}` como el uso XAML sin tener en cuenta qué lenguaje de código subyacente asocie con el XAML.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="2e7a4-108">El `x:Null` extensión de marcado no tiene ninguna propiedad configurable.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="2e7a4-109">Un uso null suele asociarse con la exposición de miembro XAML de un CLR <xref:System.Nullable%601> valor.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="2e7a4-110">El `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, usa las llaves (`{,}`) para el tratamiento de los valores de atributo no es literales o referencias de controlador de eventos de secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="2e7a4-111">Sintaxis de atributo es la sintaxis que se usan frecuentemente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="2e7a4-112">Una sintaxis de elemento de objeto `<x:Null />` es técnicamente posible, pero rara vez se usa porque el `x:Null` extensión de marcado no tiene parámetros posicionales o argumentos de construcción.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="2e7a4-113">Para obtener información acerca de las extensiones de marcado, vea [extensiones de marcado y WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2e7a4-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="2e7a4-114">En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.NullExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="2e7a4-115">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="2e7a4-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="2e7a4-116">Tenga en cuenta que `null` no es necesariamente el valor inicial no establecido para una propiedad de dependencia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="2e7a4-117">El valor predeterminado inicial puede variar para cada propiedad de dependencia y puede basarse en los metadatos específicos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="2e7a4-118">Muchas propiedades de dependencia no los acepta `null` como un valor, ya sea a través de marcado o el código debido a sus implementaciones de devolución de llamada de validación.</span><span class="sxs-lookup"><span data-stu-id="2e7a4-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="2e7a4-119">Para obtener más información acerca de las propiedades de dependencia, consulte [información general sobre las propiedades de dependencia](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e7a4-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7a4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e7a4-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="2e7a4-121">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="2e7a4-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="2e7a4-122">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="2e7a4-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)

---
title: "x:Null (Extensión de marcado)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b10d759a4f79eabe973a0fcd60736428e46f659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="a9bea-102">x:Null (Extensión de marcado)</span><span class="sxs-lookup"><span data-stu-id="a9bea-102">x:Null Markup Extension</span></span>
<span data-ttu-id="a9bea-103">Especifica `null` como un valor para un miembro XAML.</span><span class="sxs-lookup"><span data-stu-id="a9bea-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a9bea-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="a9bea-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="a9bea-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9bea-105">Remarks</span></span>  
 <span data-ttu-id="a9bea-106">La palabra clave para una referencia nula en [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] es null.</span><span class="sxs-lookup"><span data-stu-id="a9bea-106">The keyword for a null reference in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="a9bea-107">El [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] palabra clave para una referencia nula es `Nothing`, pero siempre utilizar `{x:Null}` como el uso XAML sin tener en cuenta qué lenguaje de código subyacente se asocia con el código XAML.</span><span class="sxs-lookup"><span data-stu-id="a9bea-107">The [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="a9bea-108">El `x:Null` extensión de marcado no tiene ninguna propiedad configurable.</span><span class="sxs-lookup"><span data-stu-id="a9bea-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="a9bea-109">Un uso null a menudo está asociado a la exposición de miembro XAML de un CLR <xref:System.Nullable%601> valor.</span><span class="sxs-lookup"><span data-stu-id="a9bea-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="a9bea-110">El `x:Null` extensión de marcado, al igual que todas las extensiones de marcado XAML, utiliza las llaves (`{,}`) para la administración de los valores de atributo de literales o referencias de controlador de eventos de secuencia de escape.</span><span class="sxs-lookup"><span data-stu-id="a9bea-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="a9bea-111">La sintaxis de atributo es la sintaxis que se usan con mayor frecuencia con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="a9bea-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="a9bea-112">Una sintaxis de elemento de objeto `<x:Null />` es técnicamente posible, pero se usa con poca frecuencia porque el `x:Null` extensión de marcado no tiene parámetros posicionales o argumentos de construcción.</span><span class="sxs-lookup"><span data-stu-id="a9bea-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="a9bea-113">Para obtener información acerca de las extensiones de marcado, vea [las extensiones de marcado y XAML de WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="a9bea-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="a9bea-114">En los servicios XAML de .NET Framework, el control para esta extensión de marcado se define por la <xref:System.Windows.Markup.NullExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="a9bea-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="a9bea-115">Notas de uso WPF</span><span class="sxs-lookup"><span data-stu-id="a9bea-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="a9bea-116">Tenga en cuenta que `null` no es necesariamente el valor inicial no establecido para una propiedad de dependencia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="a9bea-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="a9bea-117">El valor predeterminado inicial puede variar para cada propiedad de dependencia y se puede basar en metadatos específicos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9bea-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="a9bea-118">Muchas propiedades de dependencia no aceptan `null` como un valor, ya sea a través de marcado o el código debido a sus implementaciones de devolución de llamada de validación.</span><span class="sxs-lookup"><span data-stu-id="a9bea-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="a9bea-119">Para obtener más información acerca de las propiedades de dependencia, vea [información general sobre propiedades de dependencia](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9bea-119">For more information about dependency properties, see [Dependency Properties Overview](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bea-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9bea-120">See Also</span></span>  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [<span data-ttu-id="a9bea-121">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a9bea-121">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="a9bea-122">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="a9bea-122">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

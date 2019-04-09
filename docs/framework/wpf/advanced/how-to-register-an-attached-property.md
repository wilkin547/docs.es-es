---
title: Filtrar Registrar una propiedad adjunta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4c678a64b62b8f4db24cf39ffbafac52e56c9982
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137636"
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="76bd9-102">Filtrar Registrar una propiedad adjunta</span><span class="sxs-lookup"><span data-stu-id="76bd9-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="76bd9-103">En este ejemplo se muestra cómo registrar una propiedad adjunta y se proporcionan descriptores de acceso públicos para que pueda usar la propiedad en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y en el código.</span><span class="sxs-lookup"><span data-stu-id="76bd9-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="76bd9-104">Las propiedades adjuntas son un concepto de sintaxis que define [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76bd9-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="76bd9-105">La mayoría de propiedades adjuntas para los tipos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también se implementan como propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="76bd9-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="76bd9-106">Puede usar las propiedades de dependencia en cualquier <xref:System.Windows.DependencyObject> tipos.</span><span class="sxs-lookup"><span data-stu-id="76bd9-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76bd9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76bd9-107">Example</span></span>  
 <span data-ttu-id="76bd9-108">El ejemplo siguiente muestra cómo registrar una propiedad adjunta como una propiedad de dependencia, mediante el <xref:System.Windows.DependencyProperty.RegisterAttached%2A> método.</span><span class="sxs-lookup"><span data-stu-id="76bd9-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="76bd9-109">La clase de proveedor tiene la opción de proporcionar metadatos predeterminados para la propiedad que se aplica cuando la propiedad se usa en otra clase, a menos que esa clase invalide los metadatos.</span><span class="sxs-lookup"><span data-stu-id="76bd9-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="76bd9-110">En este ejemplo, el valor predeterminado de la propiedad `IsBubbleSource` está establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="76bd9-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="76bd9-111">La clase de proveedor para una propiedad adjunta (incluso si no está registrada como una propiedad de dependencia) debe proporcionar descriptores de acceso get y set estáticos que siguen la convención de nomenclatura `Set`*[AttachedPropertyName]* y `Get`*[AttachedPropertyName]*.</span><span class="sxs-lookup"><span data-stu-id="76bd9-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="76bd9-112">Estos descriptores de acceso son necesarios para que el lector [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pueda reconocer la propiedad como un atributo en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y resolver los tipos pertinentes.</span><span class="sxs-lookup"><span data-stu-id="76bd9-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="76bd9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="76bd9-113">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="76bd9-114">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="76bd9-114">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="76bd9-115">Propiedades de dependencia personalizadas</span><span class="sxs-lookup"><span data-stu-id="76bd9-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="76bd9-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="76bd9-116">How-to Topics</span></span>](properties-how-to-topics.md)

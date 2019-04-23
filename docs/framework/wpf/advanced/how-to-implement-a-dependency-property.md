---
title: Procedimiento Implementar una propiedad de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: e2f18cb3941be2ebf4315a844c05b91ff49c6aa2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223806"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="c7066-102">Procedimiento Implementar una propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="c7066-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="c7066-103">En este ejemplo se muestra cómo realizar una copia de un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] propiedad con un <xref:System.Windows.DependencyProperty> campo, definiendo así una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="c7066-103">This example shows how to back a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="c7066-104">Si define sus propias propiedades y quiere que admitan muchos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="c7066-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7066-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7066-105">Example</span></span>  
 <span data-ttu-id="c7066-106">En primer lugar, el ejemplo siguiente registra una propiedad de dependencia mediante una llamada a la <xref:System.Windows.DependencyProperty.Register%2A> método.</span><span class="sxs-lookup"><span data-stu-id="c7066-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="c7066-107">El nombre del campo de identificador que se utiliza para almacenar el nombre y las características de la propiedad de dependencia deben ser el <xref:System.Windows.DependencyProperty.Name%2A> que eligió para la propiedad de dependencia como parte de la <xref:System.Windows.DependencyProperty.Register%2A> llamada, seguido de la cadena literal `Property`.</span><span class="sxs-lookup"><span data-stu-id="c7066-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="c7066-108">Por ejemplo, si se registra una propiedad de dependencia con un <xref:System.Windows.DependencyProperty.Name%2A> de `Location`, a continuación, el campo de identificador que defina para la propiedad de dependencia debe denominarse `LocationProperty`.</span><span class="sxs-lookup"><span data-stu-id="c7066-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="c7066-109">En este ejemplo, el nombre de la propiedad de dependencia y su [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] descriptor de acceso es `State`; el campo de identificador es `StateProperty`; es el tipo de la propiedad <xref:System.Boolean>; y el tipo que registra la propiedad de dependencia es `MyStateControl`.</span><span class="sxs-lookup"><span data-stu-id="c7066-109">In this example, the name of the dependency property and its [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="c7066-110">Si no sigue este patrón de nomenclatura, es posible que los diseñadores no puedan notificar la propiedad correctamente y que ciertos aspectos de la aplicación de estilos del sistema de propiedades no funcionen según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="c7066-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="c7066-111">También puede especificar los metadatos predeterminados de una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="c7066-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="c7066-112">En este ejemplo se registra el valor predeterminado de la propiedad de dependencia `State` para que sea `false`.</span><span class="sxs-lookup"><span data-stu-id="c7066-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="c7066-113">Para obtener más información acerca de cómo y por qué se debe implementar una propiedad de dependencia, en lugar de respaldar simplemente una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] con un campo privado, consulte [Información general sobre las propiedades de dependencia](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c7066-113">For more information about how and why to implement a dependency property, as opposed to just backing a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7066-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7066-114">See also</span></span>

- [<span data-ttu-id="c7066-115">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="c7066-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="c7066-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="c7066-116">How-to Topics</span></span>](properties-how-to-topics.md)

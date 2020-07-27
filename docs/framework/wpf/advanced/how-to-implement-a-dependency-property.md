---
title: 'Cómo: Implementar una propiedad de dependencia'
description: Defina una propiedad de dependencia en Windows Presentation Foundation, mediante la copia de seguridad de una propiedad de Common Language Runtime con un campo DependencyProperty.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165098"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="bd66f-103">Cómo: Implementar una propiedad de dependencia</span><span class="sxs-lookup"><span data-stu-id="bd66f-103">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="bd66f-104">En este ejemplo se muestra cómo hacer una copia de seguridad de una propiedad de Common Language Runtime (CLR) con un <xref:System.Windows.DependencyProperty> campo, con lo que se define una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="bd66f-104">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="bd66f-105">Si define sus propias propiedades y quiere que admitan muchos aspectos de la funcionalidad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], incluidos los estilos, el enlace de datos, la herencia, la animación y los valores predeterminados, debe implementarlas como una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="bd66f-105">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd66f-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd66f-106">Example</span></span>  
 <span data-ttu-id="bd66f-107">En el ejemplo siguiente, primero se registra una propiedad de dependencia mediante una llamada al <xref:System.Windows.DependencyProperty.Register%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bd66f-107">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="bd66f-108">El nombre del campo de identificador que se usa para almacenar el nombre y las características de la propiedad de dependencia debe ser el <xref:System.Windows.DependencyProperty.Name%2A> elegido para la propiedad de dependencia como parte de la <xref:System.Windows.DependencyProperty.Register%2A> llamada, anexado por la cadena literal `Property` .</span><span class="sxs-lookup"><span data-stu-id="bd66f-108">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="bd66f-109">Por ejemplo, si registra una propiedad de dependencia con un <xref:System.Windows.DependencyProperty.Name%2A> de `Location` , el campo de identificador que defina para la propiedad de dependencia debe denominarse `LocationProperty` .</span><span class="sxs-lookup"><span data-stu-id="bd66f-109">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="bd66f-110">En este ejemplo, el nombre de la propiedad de dependencia y su descriptor de acceso CLR es `State` ; el campo de identificador es `StateProperty` ; el tipo de la propiedad es <xref:System.Boolean> ; y el tipo que registra la propiedad de dependencia es `MyStateControl` .</span><span class="sxs-lookup"><span data-stu-id="bd66f-110">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="bd66f-111">Si no sigue este patrón de nomenclatura, es posible que los diseñadores no puedan notificar la propiedad correctamente y que ciertos aspectos de la aplicación de estilos del sistema de propiedades no funcionen según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="bd66f-111">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="bd66f-112">También puede especificar los metadatos predeterminados de una propiedad de dependencia.</span><span class="sxs-lookup"><span data-stu-id="bd66f-112">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="bd66f-113">En este ejemplo se registra el valor predeterminado de la propiedad de dependencia `State` para que sea `false`.</span><span class="sxs-lookup"><span data-stu-id="bd66f-113">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="bd66f-114">Para obtener más información sobre cómo y por qué implementar una propiedad de dependencia, en lugar de hacer una copia de seguridad de una propiedad de CLR con un campo privado, vea [información general sobre las propiedades de dependencia](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bd66f-114">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd66f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd66f-115">See also</span></span>

- [<span data-ttu-id="bd66f-116">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="bd66f-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="bd66f-117">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="bd66f-117">How-to Topics</span></span>](properties-how-to-topics.md)

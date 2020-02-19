---
title: 'Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453057"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="15d4f-102">Cómo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada</span><span class="sxs-lookup"><span data-stu-id="15d4f-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="15d4f-103">En este ejemplo se muestra cómo obtener el objeto de enlace desde una propiedad de destino enlazada a datos.</span><span class="sxs-lookup"><span data-stu-id="15d4f-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>

## <a name="example"></a><span data-ttu-id="15d4f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15d4f-104">Example</span></span>
 <span data-ttu-id="15d4f-105">Puede hacer lo siguiente para obtener el objeto de <xref:System.Windows.Data.Binding>:</span><span class="sxs-lookup"><span data-stu-id="15d4f-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> <span data-ttu-id="15d4f-106">Debe especificar la propiedad de dependencia para el enlace que desee porque es posible que más de una propiedad del objeto de destino esté usando el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="15d4f-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>

 <span data-ttu-id="15d4f-107">Como alternativa, puede obtener el <xref:System.Windows.Data.BindingExpression> y, a continuación, obtener el valor de la propiedad <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d4f-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>

 <span data-ttu-id="15d4f-108">Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="15d4f-108">For the complete example see [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>

> [!NOTE]
> <span data-ttu-id="15d4f-109">Si el enlace es un <xref:System.Windows.Data.MultiBinding>, utilice <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d4f-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="15d4f-110">Si es un <xref:System.Windows.Data.PriorityBinding>, utilice <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d4f-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="15d4f-111">Si no está seguro de si la propiedad de destino está enlazada mediante un <xref:System.Windows.Data.Binding>, un <xref:System.Windows.Data.MultiBinding>o un <xref:System.Windows.Data.PriorityBinding>, puede utilizar <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15d4f-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="15d4f-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15d4f-112">See also</span></span>

- [<span data-ttu-id="15d4f-113">Crear un enlace mediante código</span><span class="sxs-lookup"><span data-stu-id="15d4f-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="15d4f-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="15d4f-114">How-to Topics</span></span>](data-binding-how-to-topics.md)

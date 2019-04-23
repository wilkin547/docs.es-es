---
title: Procedimiento Obtener el objeto de enlace a partir de una propiedad de destino enlazada
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 7c7392bc11af57b2e9f27e2302f36efb59d40e9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083119"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a><span data-ttu-id="2a83c-102">Procedimiento Obtener el objeto de enlace a partir de una propiedad de destino enlazada</span><span class="sxs-lookup"><span data-stu-id="2a83c-102">How to: Get the Binding Object from a Bound Target Property</span></span>
<span data-ttu-id="2a83c-103">En este ejemplo se muestra cómo obtener el objeto de enlace desde una propiedad de destino enlazada a datos.</span><span class="sxs-lookup"><span data-stu-id="2a83c-103">This example shows how to obtain the binding object from a data-bound target property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a83c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a83c-104">Example</span></span>  
 <span data-ttu-id="2a83c-105">Puede hacer lo siguiente para obtener el <xref:System.Windows.Data.Binding> objeto:</span><span class="sxs-lookup"><span data-stu-id="2a83c-105">You can do the following to get the <xref:System.Windows.Data.Binding> object:</span></span>  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  <span data-ttu-id="2a83c-106">Debe especificar la propiedad de dependencia para el enlace que desee porque es posible que más de una propiedad del objeto de destino esté usando el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="2a83c-106">You must specify the dependency property for the binding you want because it is possible that more than one property of the target object is using data binding.</span></span>  
  
 <span data-ttu-id="2a83c-107">Como alternativa, puede obtener el <xref:System.Windows.Data.BindingExpression> y, a continuación, obtener el valor de la <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a83c-107">Alternatively, you can get the <xref:System.Windows.Data.BindingExpression> and then get the value of the <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> property.</span></span>  
  
 <span data-ttu-id="2a83c-108">Para obtener el ejemplo completo, vea [Enlace de ejemplo de validación](https://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="2a83c-108">For the complete example see [Binding Validation Sample](https://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a83c-109">Si el enlace es un <xref:System.Windows.Data.MultiBinding>, utilice <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a83c-109">If your binding is a <xref:System.Windows.Data.MultiBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.</span></span> <span data-ttu-id="2a83c-110">Si es un <xref:System.Windows.Data.PriorityBinding>, utilice <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a83c-110">If it is a <xref:System.Windows.Data.PriorityBinding>, use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.</span></span> <span data-ttu-id="2a83c-111">Si no está seguro de si la propiedad de destino está enlazada con un <xref:System.Windows.Data.Binding>, un <xref:System.Windows.Data.MultiBinding>, o un <xref:System.Windows.Data.PriorityBinding>, puede usar <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a83c-111">If you are uncertain whether the target property is bound using a <xref:System.Windows.Data.Binding>, a <xref:System.Windows.Data.MultiBinding>, or a <xref:System.Windows.Data.PriorityBinding>, you can use <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a83c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a83c-112">See also</span></span>

- [<span data-ttu-id="2a83c-113">Crear un enlace mediante código</span><span class="sxs-lookup"><span data-stu-id="2a83c-113">Create a Binding in Code</span></span>](how-to-create-a-binding-in-code.md)
- [<span data-ttu-id="2a83c-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="2a83c-114">How-to Topics</span></span>](data-binding-how-to-topics.md)

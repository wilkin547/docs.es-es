---
title: Procedimiento Crear un enlace mediante código
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 57ec845c5c9a5bddb801428b9ecde035a97cf447
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089268"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="c47f3-102">Procedimiento Crear un enlace mediante código</span><span class="sxs-lookup"><span data-stu-id="c47f3-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="c47f3-103">En este ejemplo se muestra cómo crear y establecer un <xref:System.Windows.Data.Binding> en el código.</span><span class="sxs-lookup"><span data-stu-id="c47f3-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c47f3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c47f3-104">Example</span></span>  
 <span data-ttu-id="c47f3-105">El <xref:System.Windows.FrameworkElement> clase y el <xref:System.Windows.FrameworkContentElement> clase ambas exponer un `SetBinding` método.</span><span class="sxs-lookup"><span data-stu-id="c47f3-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="c47f3-106">Si va a enlazar un elemento que hereda de cualquiera de estas clases, puede llamar a la <xref:System.Windows.FrameworkElement.SetBinding%2A> método directamente.</span><span class="sxs-lookup"><span data-stu-id="c47f3-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="c47f3-107">En el ejemplo siguiente se crea una clase denominada, `MyData`, que contiene una propiedad denominada `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="c47f3-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="c47f3-108">El ejemplo siguiente muestra cómo crear un objeto de enlace para establecer el origen del enlace.</span><span class="sxs-lookup"><span data-stu-id="c47f3-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="c47f3-109">El ejemplo se utiliza <xref:System.Windows.FrameworkElement.SetBinding%2A> para enlazar el <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de `myText`, que es un <xref:System.Windows.Controls.TextBlock> controlar, `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="c47f3-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="c47f3-110">El ejemplo de código completo, vea [solo código de ejemplo de enlace](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c47f3-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="c47f3-111">En lugar de llamar <xref:System.Windows.FrameworkElement.SetBinding%2A>, puede usar el <xref:System.Windows.Data.BindingOperations.SetBinding%2A> método estático de la <xref:System.Windows.Data.BindingOperations> clase.</span><span class="sxs-lookup"><span data-stu-id="c47f3-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="c47f3-112">El siguiente ejemplo, las llamadas <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> en lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="c47f3-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="c47f3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c47f3-113">See also</span></span>

- [<span data-ttu-id="c47f3-114">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="c47f3-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="c47f3-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="c47f3-115">How-to Topics</span></span>](data-binding-how-to-topics.md)

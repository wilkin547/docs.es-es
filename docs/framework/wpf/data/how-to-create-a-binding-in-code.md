---
title: 'Cómo: Crear un enlace en código'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 616487a16ebbe6e23fe067fb7ce72644aa3f919f
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458851"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="38ebc-102">Cómo: Crear un enlace en código</span><span class="sxs-lookup"><span data-stu-id="38ebc-102">How to: Create a Binding in Code</span></span>
<span data-ttu-id="38ebc-103">En este ejemplo se muestra cómo crear y establecer un <xref:System.Windows.Data.Binding> en el código.</span><span class="sxs-lookup"><span data-stu-id="38ebc-103">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ebc-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38ebc-104">Example</span></span>  
 <span data-ttu-id="38ebc-105">La clase <xref:System.Windows.FrameworkElement> y la clase <xref:System.Windows.FrameworkContentElement> exponen un método `SetBinding`.</span><span class="sxs-lookup"><span data-stu-id="38ebc-105">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="38ebc-106">Si enlaza un elemento que hereda cualquiera de estas clases, puede llamar al método <xref:System.Windows.FrameworkElement.SetBinding%2A> directamente.</span><span class="sxs-lookup"><span data-stu-id="38ebc-106">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="38ebc-107">En el ejemplo siguiente se crea una clase denominada, `MyData`, que contiene una propiedad denominada `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38ebc-107">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="38ebc-108">En el ejemplo siguiente se muestra cómo crear un objeto de enlace para establecer el origen del enlace.</span><span class="sxs-lookup"><span data-stu-id="38ebc-108">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="38ebc-109">En el ejemplo se usa <xref:System.Windows.FrameworkElement.SetBinding%2A> para enlazar la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> de `myText`, que es un control <xref:System.Windows.Controls.TextBlock>, a `MyDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38ebc-109">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="38ebc-110">Para obtener el ejemplo de código completo, vea [ejemplo de enlace de solo código](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="38ebc-110">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="38ebc-111">En lugar de llamar a <xref:System.Windows.FrameworkElement.SetBinding%2A>, puede utilizar el método estático <xref:System.Windows.Data.BindingOperations.SetBinding%2A> de la clase <xref:System.Windows.Data.BindingOperations>.</span><span class="sxs-lookup"><span data-stu-id="38ebc-111">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="38ebc-112">En el ejemplo siguiente, se llama a <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> en lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty`.</span><span class="sxs-lookup"><span data-stu-id="38ebc-112">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="38ebc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="38ebc-113">See also</span></span>

- [<span data-ttu-id="38ebc-114">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="38ebc-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="38ebc-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="38ebc-115">How-to Topics</span></span>](data-binding-how-to-topics.md)

---
title: 'Cómo: Crear un enlace en código'
description: Aprenda a crear un enlace en el código en una aplicación Windows Presentation Foundation llamando directamente al método SetBinding.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165809"
---
# <a name="how-to-create-a-binding-in-code"></a><span data-ttu-id="49bdc-103">Cómo: Crear un enlace en código</span><span class="sxs-lookup"><span data-stu-id="49bdc-103">How to: Create a Binding in Code</span></span>
<span data-ttu-id="49bdc-104">En este ejemplo se muestra cómo crear y establecer <xref:System.Windows.Data.Binding> en código.</span><span class="sxs-lookup"><span data-stu-id="49bdc-104">This example shows how to create and set a <xref:System.Windows.Data.Binding> in code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49bdc-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49bdc-105">Example</span></span>  
 <span data-ttu-id="49bdc-106">La <xref:System.Windows.FrameworkElement> clase y la <xref:System.Windows.FrameworkContentElement> clase exponen un `SetBinding` método.</span><span class="sxs-lookup"><span data-stu-id="49bdc-106">The <xref:System.Windows.FrameworkElement> class and the <xref:System.Windows.FrameworkContentElement> class both expose a `SetBinding` method.</span></span> <span data-ttu-id="49bdc-107">Si enlaza un elemento que hereda cualquiera de estas clases, puede llamar al <xref:System.Windows.FrameworkElement.SetBinding%2A> método directamente.</span><span class="sxs-lookup"><span data-stu-id="49bdc-107">If you are binding an element that inherits either of these classes, you can call the <xref:System.Windows.FrameworkElement.SetBinding%2A> method directly.</span></span>  
  
 <span data-ttu-id="49bdc-108">En el ejemplo siguiente se crea una clase denominada, `MyData` que contiene una propiedad denominada `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="49bdc-108">The following example creates a class named, `MyData`, which contains a property named `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 <span data-ttu-id="49bdc-109">En el ejemplo siguiente se muestra cómo crear un objeto de enlace para establecer el origen del enlace.</span><span class="sxs-lookup"><span data-stu-id="49bdc-109">The following example shows how to create a binding object to set the source of the binding.</span></span>  <span data-ttu-id="49bdc-110">En el ejemplo <xref:System.Windows.FrameworkElement.SetBinding%2A> se utiliza para enlazar la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad de `myText` , que es un <xref:System.Windows.Controls.TextBlock> control, a `MyDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="49bdc-110">The example uses <xref:System.Windows.FrameworkElement.SetBinding%2A> to bind the <xref:System.Windows.Controls.TextBlock.Text%2A> property of `myText`, which is a <xref:System.Windows.Controls.TextBlock> control, to `MyDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 <span data-ttu-id="49bdc-111">Para obtener el ejemplo de código completo, vea [ejemplo de enlace de solo código](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="49bdc-111">For the complete code sample, see [Code-only Binding Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).</span></span>  
  
 <span data-ttu-id="49bdc-112">En lugar de llamar a <xref:System.Windows.FrameworkElement.SetBinding%2A> , puede utilizar el <xref:System.Windows.Data.BindingOperations.SetBinding%2A> método estático de la <xref:System.Windows.Data.BindingOperations> clase.</span><span class="sxs-lookup"><span data-stu-id="49bdc-112">Instead of calling <xref:System.Windows.FrameworkElement.SetBinding%2A>, you can use the <xref:System.Windows.Data.BindingOperations.SetBinding%2A> static method of the <xref:System.Windows.Data.BindingOperations> class.</span></span> <span data-ttu-id="49bdc-113">En el ejemplo siguiente, se llama a en <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> lugar de <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> para enlazar `myText` a `myDataProperty` .</span><span class="sxs-lookup"><span data-stu-id="49bdc-113">The following example, calls <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> instead of <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> to bind `myText` to `myDataProperty`.</span></span>  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a><span data-ttu-id="49bdc-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49bdc-114">See also</span></span>

- [<span data-ttu-id="49bdc-115">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="49bdc-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="49bdc-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="49bdc-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

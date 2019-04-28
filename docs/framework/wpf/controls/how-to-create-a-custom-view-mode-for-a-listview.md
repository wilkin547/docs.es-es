---
title: Procedimiento Crear un modo de vista personalizado para un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: de11250a2e7529fba3b262e42b6714262738fa90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910915"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="0f0e5-102">Procedimiento Crear un modo de vista personalizado para un control ListView</span><span class="sxs-lookup"><span data-stu-id="0f0e5-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="0f0e5-103">En este ejemplo se muestra cómo crear una personalizada <xref:System.Windows.Controls.ListView.View%2A> modo para un <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f0e5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f0e5-104">Example</span></span>  
 <span data-ttu-id="0f0e5-105">Debe usar el <xref:System.Windows.Controls.ViewBase> clase cuando se crea una vista personalizada para el <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="0f0e5-106">El ejemplo siguiente muestra un modo de vista que se llama `PlainView`, que se deriva el <xref:System.Windows.Controls.ViewBase> clase.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="0f0e5-107">Para aplicar un estilo a la vista personalizada, use la <xref:System.Windows.Style> clase.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="0f0e5-108">En el ejemplo siguiente se define un <xref:System.Windows.Style> para el `PlainView` modo de vista.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="0f0e5-109">En el ejemplo anterior, este estilo se establece como valor de la <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> propiedad que se define para `PlainView`.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="0f0e5-110">Para definir el diseño de datos en un modo de vista personalizada, defina un <xref:System.Windows.DataTemplate> objeto.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="0f0e5-111">En el ejemplo siguiente se define un <xref:System.Windows.DataTemplate> que puede utilizarse para mostrar datos en el `PlainView` modo de vista.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="0f0e5-112">El ejemplo siguiente muestra cómo definir un <xref:System.Windows.ResourceKey> para el `PlainView` modo de vista que usa el <xref:System.Windows.DataTemplate> que se define en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="0f0e5-113">Un <xref:System.Windows.Controls.ListView> control puede usar una vista personalizada si establece la <xref:System.Windows.Controls.ListView.View%2A> propiedad a la clave de recurso.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="0f0e5-114">El ejemplo siguiente muestra cómo especificar `PlainView` como el modo de vista para un <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="0f0e5-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="0f0e5-115">Para obtener un ejemplo completo, vea [ListView con varias vistas (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con varias Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="0f0e5-115">For the complete sample, see [ListView with Multiple Views(C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f0e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f0e5-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="0f0e5-117">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0f0e5-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="0f0e5-118">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="0f0e5-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="0f0e5-119">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="0f0e5-119">GridView Overview</span></span>](gridview-overview.md)

---
title: 'Cómo: Crear un modo de vista personalizado para un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243224"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="face7-102">Cómo: Crear un modo de vista personalizado para un ListView</span><span class="sxs-lookup"><span data-stu-id="face7-102">How to: Create a custom view mode for a ListView</span></span>

<span data-ttu-id="face7-103">En este ejemplo se <xref:System.Windows.Controls.ListView.View%2A> muestra cómo <xref:System.Windows.Controls.ListView> crear un modo personalizado para un control.</span><span class="sxs-lookup"><span data-stu-id="face7-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="face7-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="face7-104">Example</span></span>  
 <span data-ttu-id="face7-105">Debe usar <xref:System.Windows.Controls.ViewBase> la clase al crear una <xref:System.Windows.Controls.ListView> vista personalizada para el control.</span><span class="sxs-lookup"><span data-stu-id="face7-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="face7-106">En el ejemplo siguiente `PlainView` se muestra un modo <xref:System.Windows.Controls.ViewBase> de vista denominado que se deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="face7-106">The following example shows a view mode called `PlainView` that's derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="face7-107">Para aplicar un estilo a la <xref:System.Windows.Style> vista personalizada, utilice la clase.</span><span class="sxs-lookup"><span data-stu-id="face7-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="face7-108">En el ejemplo <xref:System.Windows.Style> siguiente `PlainView` se define un para el modo de vista.</span><span class="sxs-lookup"><span data-stu-id="face7-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="face7-109">En el ejemplo anterior, este estilo se <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> establece como el `PlainView`valor de la propiedad definida para .</span><span class="sxs-lookup"><span data-stu-id="face7-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that's defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="face7-110">Para definir el diseño de datos en <xref:System.Windows.DataTemplate> un modo de vista personalizado, defina un objeto.</span><span class="sxs-lookup"><span data-stu-id="face7-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="face7-111">En el ejemplo <xref:System.Windows.DataTemplate> siguiente se define un `PlainView` que se puede utilizar para mostrar datos en el modo de vista.</span><span class="sxs-lookup"><span data-stu-id="face7-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="face7-112">En el ejemplo siguiente <xref:System.Windows.ResourceKey> se `PlainView` muestra cómo definir <xref:System.Windows.DataTemplate> un para el modo de vista que utiliza el que se define en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="face7-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="face7-113">Un <xref:System.Windows.Controls.ListView> control puede usar una vista <xref:System.Windows.Controls.ListView.View%2A> personalizada si establece la propiedad en la clave de recurso.</span><span class="sxs-lookup"><span data-stu-id="face7-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="face7-114">En el ejemplo siguiente `PlainView` se muestra cómo <xref:System.Windows.Controls.ListView>especificar como modo de vista para un archivo .</span><span class="sxs-lookup"><span data-stu-id="face7-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="face7-115">Para obtener el ejemplo completo, vea [ListView con varias vistas (C)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con varias vistas (Visual Basic).](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)</span><span class="sxs-lookup"><span data-stu-id="face7-115">For the complete sample, see [ListView with Multiple Views (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) or [ListView with Multiple Views (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="face7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="face7-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="face7-117">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="face7-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="face7-118">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="face7-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="face7-119">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="face7-119">GridView Overview</span></span>](gridview-overview.md)

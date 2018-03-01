---
title: "Cómo: Cambiar la alineación horizontal de una columna en un control ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7a465ae44d3b8a4c43e5e34eaeedcd739d328bff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a><span data-ttu-id="b353e-102">Cómo: Cambiar la alineación horizontal de una columna en un control ListView</span><span class="sxs-lookup"><span data-stu-id="b353e-102">How to: Change the Horizontal Alignment of a Column in a ListView</span></span>
<span data-ttu-id="b353e-103">De forma predeterminada, el contenido de cada columna en un <xref:System.Windows.Controls.ListViewItem> está alineado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b353e-103">By default, the content of each column in a <xref:System.Windows.Controls.ListViewItem> is left-aligned.</span></span> <span data-ttu-id="b353e-104">Puede cambiar la alineación de cada columna, proporcionando un <xref:System.Windows.DataTemplate> y estableciendo el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad del elemento dentro de la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="b353e-104">You can change the alignment of each column by providing a <xref:System.Windows.DataTemplate> and setting the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property on the element within the <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="b353e-105">Este tema se muestra cómo un <xref:System.Windows.Controls.ListView> alinea su contenido de forma predeterminada y cómo cambiar la alineación de una columna en un <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="b353e-105">This topic shows how a <xref:System.Windows.Controls.ListView> aligns its content by default and how to change the alignment of one column in a <xref:System.Windows.Controls.ListView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b353e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b353e-106">Example</span></span>  
 <span data-ttu-id="b353e-107">En el ejemplo siguiente, los datos de la `Title` y `ISBN` columnas está alineado a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="b353e-107">In the following example, the data in the `Title` and `ISBN` columns is left-aligned.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="b353e-108">Para cambiar la alineación de la `ISBN` columna, debe especificar que el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedad de cada <xref:System.Windows.Controls.ListViewItem> es <xref:System.Windows.HorizontalAlignment.Stretch>, de modo que los elementos de cada uno de ellos <xref:System.Windows.Controls.ListViewItem> puede abarcar o colocarse a lo largo de todo el ancho de cada columna.</span><span class="sxs-lookup"><span data-stu-id="b353e-108">To change the alignment of the `ISBN` column, you need to specify that the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> property of each <xref:System.Windows.Controls.ListViewItem> is <xref:System.Windows.HorizontalAlignment.Stretch>, so that the elements in each <xref:System.Windows.Controls.ListViewItem> can span or be positioned along the entire width of each column.</span></span> <span data-ttu-id="b353e-109">Dado que la <xref:System.Windows.Controls.ListView> está enlazado a un origen de datos, deberá crear un estilo que establece el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="b353e-109">Because the <xref:System.Windows.Controls.ListView> is bound to a data source, you need to create a style that sets the <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>.</span></span> <span data-ttu-id="b353e-110">A continuación, debe usar un <xref:System.Windows.DataTemplate> para mostrar el contenido en lugar de utilizar el <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b353e-110">Next, you need to use a <xref:System.Windows.DataTemplate> to display the content instead of using the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property.</span></span> <span data-ttu-id="b353e-111">Para mostrar la `ISBN` de cada plantilla, el <xref:System.Windows.DataTemplate> solo puede contener una <xref:System.Windows.Controls.TextBlock> que tiene su <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad establecida en <xref:System.Windows.HorizontalAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="b353e-111">To display the `ISBN` of each template, the <xref:System.Windows.DataTemplate> can just contain a <xref:System.Windows.Controls.TextBlock> that has its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property set to <xref:System.Windows.HorizontalAlignment.Right>.</span></span>  
  
 <span data-ttu-id="b353e-112">En el ejemplo siguiente se define el estilo y <xref:System.Windows.DataTemplate> necesarios para realizar la `ISBN` columna alineado a la derecha y los cambios el <xref:System.Windows.Controls.GridViewColumn> para hacer referencia a la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="b353e-112">The following example defines the style and <xref:System.Windows.DataTemplate> necessary to make the `ISBN` column right-aligned, and changes the <xref:System.Windows.Controls.GridViewColumn> to reference the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b353e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b353e-113">See Also</span></span>  
 [<span data-ttu-id="b353e-114">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="b353e-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="b353e-115">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="b353e-115">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="b353e-116">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="b353e-116">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [<span data-ttu-id="b353e-117">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="b353e-117">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)

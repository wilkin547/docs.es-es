---
title: 'Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733540"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="f3cf9-102">Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView</span><span class="sxs-lookup"><span data-stu-id="f3cf9-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="f3cf9-103">En este ejemplo se muestra cómo aplicar un estilo a una fila en un control <xref:System.Windows.Controls.ListView> que implementa un modo de <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cf9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3cf9-104">Example</span></span>  
 <span data-ttu-id="f3cf9-105">Puede aplicar un estilo a una fila en un control <xref:System.Windows.Controls.ListView> estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el control <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="f3cf9-106">Establezca el estilo de los elementos que se representan como objetos de <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="f3cf9-107">El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> hace referencia a los objetos <xref:System.Windows.Controls.ControlTemplate> que se usan para mostrar el contenido de la fila.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="f3cf9-108">El ejemplo completo, del que se extraen los ejemplos siguientes, muestra una colección de información de la canción almacenada en una base de datos XML.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="f3cf9-109">Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="f3cf9-110">En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para los objetos <xref:System.Windows.Controls.ListViewItem> que representan las canciones de la colección Song.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="f3cf9-111">El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> hace referencia a <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="f3cf9-112">En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="f3cf9-113">Se hace referencia a esta plantilla en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco).</span><span class="sxs-lookup"><span data-stu-id="f3cf9-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="f3cf9-114">El <xref:System.Windows.Controls.ControlTemplate> incluye un objeto <xref:System.Windows.Controls.GridViewRowPresenter> que coloca el contenido de la fila en columnas tal y como se define en el modo de vista <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="f3cf9-115">En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="f3cf9-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="f3cf9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3cf9-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="f3cf9-117">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="f3cf9-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="f3cf9-118">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="f3cf9-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="f3cf9-119">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f3cf9-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)

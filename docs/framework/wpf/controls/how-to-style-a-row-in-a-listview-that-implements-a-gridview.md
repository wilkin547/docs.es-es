---
title: Filtrar Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 0c8806c399959fdc1466e0839ba469881718092b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361634"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="a6c38-102">Filtrar Aplicar un estilo a una fila en un control ListView que implementa una clase GridView</span><span class="sxs-lookup"><span data-stu-id="a6c38-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="a6c38-103">En este ejemplo se muestra cómo aplicar un estilo una fila en un <xref:System.Windows.Controls.ListView> control que implementa un <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modo.</span><span class="sxs-lookup"><span data-stu-id="a6c38-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6c38-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6c38-104">Example</span></span>  
 <span data-ttu-id="a6c38-105">Puedes aplicar estilo a una fila en un <xref:System.Windows.Controls.ListView> control estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="a6c38-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="a6c38-106">Establecer el estilo de sus elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="a6c38-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="a6c38-107">El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias el <xref:System.Windows.Controls.ControlTemplate> objetos que se usan para mostrar el contenido de la fila.</span><span class="sxs-lookup"><span data-stu-id="a6c38-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="a6c38-108">En el ejemplo completo, del cual se extraen los siguientes, se muestra una colección de información de la canción que se almacena en una base de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6c38-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="a6c38-109">Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="a6c38-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="a6c38-110">El ejemplo siguiente muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para el <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección de canciones.</span><span class="sxs-lookup"><span data-stu-id="a6c38-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="a6c38-111">El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="a6c38-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="a6c38-112">El ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila.</span><span class="sxs-lookup"><span data-stu-id="a6c38-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="a6c38-113">Esta plantilla se hace referencia en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco).</span><span class="sxs-lookup"><span data-stu-id="a6c38-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="a6c38-114">El <xref:System.Windows.Controls.ControlTemplate> incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que distribuye el contenido de la fila en columnas tal como se define por el <xref:System.Windows.Controls.GridView> modo de vista.</span><span class="sxs-lookup"><span data-stu-id="a6c38-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="a6c38-115">En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="a6c38-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="a6c38-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6c38-116">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="a6c38-117">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="a6c38-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="a6c38-118">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="a6c38-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="a6c38-119">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a6c38-119">Styling and Templating</span></span>](styling-and-templating.md)

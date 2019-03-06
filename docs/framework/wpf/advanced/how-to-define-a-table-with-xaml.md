---
title: Procedimiento Definir una tabla con XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 7398af6fddae56238e1af3ee4e726420c01ab7ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376941"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="25c0b-102">Procedimiento Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="25c0b-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="25c0b-103">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Documents.Table> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25c0b-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="25c0b-104">La tabla de ejemplo tiene cuatro columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y varias filas (representados por <xref:System.Windows.Documents.TableRow> elementos) que contiene los datos, así como el título, encabezado y pie de página información.</span><span class="sxs-lookup"><span data-stu-id="25c0b-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="25c0b-105">Las filas deben encontrarse en un <xref:System.Windows.Documents.TableRowGroup> elemento.</span><span class="sxs-lookup"><span data-stu-id="25c0b-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="25c0b-106">Cada fila de la tabla está formado por una o varias celdas (representado por <xref:System.Windows.Documents.TableCell> elementos).</span><span class="sxs-lookup"><span data-stu-id="25c0b-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="25c0b-107">Contenido en una celda de tabla debe estar incluido en un <xref:System.Windows.Documents.Block> elemento; en este caso <xref:System.Windows.Documents.Paragraph> se usan los elementos.</span><span class="sxs-lookup"><span data-stu-id="25c0b-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="25c0b-108">La tabla también hospeda un hipervínculo (representado por la <xref:System.Windows.Documents.Hyperlink> elemento) en la fila de pie de página.</span><span class="sxs-lookup"><span data-stu-id="25c0b-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25c0b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25c0b-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="25c0b-110">En la ilustración siguiente se muestra cómo se representa la tabla definida en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="25c0b-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="25c0b-111">![Tabla representada.](./media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="25c0b-111">![Rendered table.](./media/tableeg.png "TableEG")</span></span>

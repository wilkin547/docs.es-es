---
title: Procedimiento Definir una tabla con XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 011f612527f0c9e89ec05643edbb95b2d908488c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776589"
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="adfe3-102">Procedimiento Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="adfe3-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="adfe3-103">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Documents.Table> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adfe3-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="adfe3-104">La tabla de ejemplo tiene cuatro columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y varias filas (representados por <xref:System.Windows.Documents.TableRow> elementos) que contiene los datos, así como el título, encabezado y pie de página información.</span><span class="sxs-lookup"><span data-stu-id="adfe3-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="adfe3-105">Las filas deben encontrarse en un <xref:System.Windows.Documents.TableRowGroup> elemento.</span><span class="sxs-lookup"><span data-stu-id="adfe3-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="adfe3-106">Cada fila de la tabla está formado por una o varias celdas (representado por <xref:System.Windows.Documents.TableCell> elementos).</span><span class="sxs-lookup"><span data-stu-id="adfe3-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="adfe3-107">Contenido en una celda de tabla debe estar incluido en un <xref:System.Windows.Documents.Block> elemento; en este caso <xref:System.Windows.Documents.Paragraph> se usan los elementos.</span><span class="sxs-lookup"><span data-stu-id="adfe3-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="adfe3-108">La tabla también hospeda un hipervínculo (representado por la <xref:System.Windows.Documents.Hyperlink> elemento) en la fila de pie de página.</span><span class="sxs-lookup"><span data-stu-id="adfe3-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adfe3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="adfe3-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="adfe3-110">En la siguiente ilustración se muestra cómo se representa la tabla definida en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="adfe3-110">The following figure shows how the table defined in this example renders:</span></span>  
  
 ![Captura de pantalla de una tabla definida con XAML.](./media/how-to-define-a-table-with-xaml/planetary-information-xaml-table.png)

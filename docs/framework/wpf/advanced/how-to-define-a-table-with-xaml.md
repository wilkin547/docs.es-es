---
title: "Cómo: Definir una tabla con XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b932c7df822edabc5626f20af2bfc1eb3a7f93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-table-with-xaml"></a><span data-ttu-id="e186f-102">Cómo: Definir una tabla con XAML</span><span class="sxs-lookup"><span data-stu-id="e186f-102">How to: Define a Table with XAML</span></span>
<span data-ttu-id="e186f-103">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Documents.Table> con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e186f-103">The following example demonstrates how to define a <xref:System.Windows.Documents.Table> using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  <span data-ttu-id="e186f-104">La tabla de ejemplo tiene cuatro columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y varias filas (representados por <xref:System.Windows.Documents.TableRow> elementos) que contiene los datos, así como el título, encabezado y pie de página información.</span><span class="sxs-lookup"><span data-stu-id="e186f-104">The example table has four columns (represented by <xref:System.Windows.Documents.TableColumn> elements) and several rows (represented by <xref:System.Windows.Documents.TableRow> elements) containing data as well as title, header, and footer information.</span></span>  <span data-ttu-id="e186f-105">Filas deben estar contenidas en un <xref:System.Windows.Documents.TableRowGroup> elemento.</span><span class="sxs-lookup"><span data-stu-id="e186f-105">Rows must be contained in a <xref:System.Windows.Documents.TableRowGroup> element.</span></span>  <span data-ttu-id="e186f-106">Cada fila de la tabla está formada por una o varias celdas (representado por <xref:System.Windows.Documents.TableCell> elementos).</span><span class="sxs-lookup"><span data-stu-id="e186f-106">Each row in the table is comprised of one or more cells (represented by <xref:System.Windows.Documents.TableCell> elements).</span></span>  <span data-ttu-id="e186f-107">El contenido de una celda de tabla debe estar contenido en un <xref:System.Windows.Documents.Block> elemento; en este caso <xref:System.Windows.Documents.Paragraph> se utilizan elementos.</span><span class="sxs-lookup"><span data-stu-id="e186f-107">Content in a table cell must be contained in a <xref:System.Windows.Documents.Block> element; in this case <xref:System.Windows.Documents.Paragraph> elements are used.</span></span>  <span data-ttu-id="e186f-108">La tabla también hospeda un hipervínculo (representado por la <xref:System.Windows.Documents.Hyperlink> elemento) en la fila de pie de página.</span><span class="sxs-lookup"><span data-stu-id="e186f-108">The table also hosts a hyperlink (represented by the <xref:System.Windows.Documents.Hyperlink> element) in the footer row.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e186f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e186f-109">Example</span></span>  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 <span data-ttu-id="e186f-110">En la ilustración siguiente se muestra cómo se representa la tabla definida en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e186f-110">The following figure shows how the table defined in this example renders.</span></span>  
  
 <span data-ttu-id="e186f-111">![Tabla representada.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span><span class="sxs-lookup"><span data-stu-id="e186f-111">![Rendered table.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")</span></span>

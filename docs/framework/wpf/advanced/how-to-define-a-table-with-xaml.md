---
title: 'Cómo: Definir una tabla con XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], defining tables
- documents [WPF], defining tables with XAML
- tables [WPF], defining with XAML
ms.assetid: 83f2dc58-437e-4cdc-b5dd-0019810c7a85
ms.openlocfilehash: 2a35a27567d962fc125cb3c408ccab95afa222af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-table-with-xaml"></a>Cómo: Definir una tabla con XAML
En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Documents.Table> con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabla de ejemplo tiene cuatro columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y varias filas (representados por <xref:System.Windows.Documents.TableRow> elementos) que contiene los datos, así como el título, encabezado y pie de página información.  Filas deben estar contenidas en un <xref:System.Windows.Documents.TableRowGroup> elemento.  Cada fila de la tabla está formada por una o varias celdas (representado por <xref:System.Windows.Documents.TableCell> elementos).  El contenido de una celda de tabla debe estar contenido en un <xref:System.Windows.Documents.Block> elemento; en este caso <xref:System.Windows.Documents.Paragraph> se utilizan elementos.  La tabla también hospeda un hipervínculo (representado por la <xref:System.Windows.Documents.Hyperlink> elemento) en la fila de pie de página.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TableSnippetsXAML#_TableXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 En la ilustración siguiente se muestra cómo se representa la tabla definida en este ejemplo.  
  
 ![Tabla representada.](../../../../docs/framework/wpf/advanced/media/tableeg.png "TableEG")

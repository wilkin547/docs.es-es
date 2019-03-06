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
# <a name="how-to-define-a-table-with-xaml"></a>Procedimiento Definir una tabla con XAML
En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Documents.Table> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  La tabla de ejemplo tiene cuatro columnas (representado por <xref:System.Windows.Documents.TableColumn> elementos) y varias filas (representados por <xref:System.Windows.Documents.TableRow> elementos) que contiene los datos, así como el título, encabezado y pie de página información.  Las filas deben encontrarse en un <xref:System.Windows.Documents.TableRowGroup> elemento.  Cada fila de la tabla está formado por una o varias celdas (representado por <xref:System.Windows.Documents.TableCell> elementos).  Contenido en una celda de tabla debe estar incluido en un <xref:System.Windows.Documents.Block> elemento; en este caso <xref:System.Windows.Documents.Paragraph> se usan los elementos.  La tabla también hospeda un hipervínculo (representado por la <xref:System.Windows.Documents.Hyperlink> elemento) en la fila de pie de página.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TableSnippetsXAML#_TableXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippetsXAML/CS/Window1.xaml#_tablexaml)]  
  
 En la ilustración siguiente se muestra cómo se representa la tabla definida en este ejemplo.  
  
 ![Tabla representada.](./media/tableeg.png "TableEG")

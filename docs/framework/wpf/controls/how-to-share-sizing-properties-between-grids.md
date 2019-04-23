---
title: Procedimiento Compartir propiedades de ajuste de tamaño entre elementos Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190345"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Procedimiento Compartir propiedades de ajuste de tamaño entre elementos Grid
En este ejemplo se muestra cómo compartir los datos de ajuste de tamaño de columnas y filas entre <xref:System.Windows.Controls.Grid> elementos con el fin de mantener un tamaño coherente.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo presentan dos <xref:System.Windows.Controls.Grid> elementos como elementos secundarios de un elemento primario <xref:System.Windows.Controls.DockPanel>. El <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> adjunta la propiedad de <xref:System.Windows.Controls.Grid> se define en el elemento primario <xref:System.Windows.Controls.DockPanel>.  
  
 En el ejemplo se manipula el valor de propiedad mediante dos <xref:System.Windows.Controls.Button> elementos; cada elemento representa uno de los valores de propiedad booleana. Cuando el <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> el valor de propiedad se establece en `true`, cada miembro de columna o fila de una <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> comparte la información de ajuste de tamaño, independientemente del contenido de una fila o columna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 El siguiente ejemplo de código subyacente controla los métodos que el botón <xref:System.Windows.Controls.Primitives.ButtonBase.Click> provoca el evento. El ejemplo escribe los resultados de estas llamadas a método <xref:System.Windows.Controls.TextBlock> elementos que uso relacionados con métodos get para los nuevos valores de propiedad como cadenas de salida.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Información general sobre elementos Panel](panels-overview.md)

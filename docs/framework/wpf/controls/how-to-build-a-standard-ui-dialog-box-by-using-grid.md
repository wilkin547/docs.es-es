---
title: Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 68c9653e616388374aad2ad33ac7dab68446241d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923414"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid
En este ejemplo se muestra cómo crear un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cuadro de diálogo estándar mediante <xref:System.Windows.Controls.Grid> el elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un cuadro de diálogo como el cuadro de diálogo **Ejecutar** en el sistema operativo Windows.  
  
 En el ejemplo se <xref:System.Windows.Controls.Grid> crea un y <xref:System.Windows.Controls.ColumnDefinition> se <xref:System.Windows.Controls.RowDefinition> usan las clases y para definir cinco columnas y cuatro filas.  
  
 A continuación, el ejemplo agrega y <xref:System.Windows.Controls.Image>coloca `RunIcon.png`un,, para representar la imagen que se encuentra en el cuadro de diálogo. La imagen se coloca en la primera columna y fila de <xref:System.Windows.Controls.Grid> (la esquina superior izquierda).  
  
 A continuación, el ejemplo agrega <xref:System.Windows.Controls.TextBlock> un elemento a la primera columna, que abarca las columnas restantes de la primera fila. Agrega otro <xref:System.Windows.Controls.TextBlock> elemento a la segunda fila de la primera columna para representar el cuadro de texto **abrir** . A <xref:System.Windows.Controls.TextBlock> continuación, que representa el área de entrada de datos.  
  
 Por último, en el ejemplo <xref:System.Windows.Controls.Button> se agregan tres elementos a la fila final, que representan los eventos **OK**, **Cancel**y **Browse** .  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Información general sobre elementos Panel](panels-overview.md)
- [Temas "Cómo..."](grid-how-to-topics.md)

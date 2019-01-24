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
ms.openlocfilehash: 893b3f7fda3314b158f7c67392a0913e30a92c09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650527"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedimiento Crear un cuadro de diálogo estándar de interfaz de usuario mediante Grid
En este ejemplo se muestra cómo crear un estándar [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] cuadro de diálogo mediante el uso de la <xref:System.Windows.Controls.Grid> elemento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un cuadro de diálogo como el **ejecutar** cuadro de diálogo en el [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] del sistema operativo.  
  
 El ejemplo se crea un <xref:System.Windows.Controls.Grid> y usa el <xref:System.Windows.Controls.ColumnDefinition> y <xref:System.Windows.Controls.RowDefinition> las clases para definir las cinco columnas y cuatro filas.  
  
 En el ejemplo, a continuación, agrega y coloca un <xref:System.Windows.Controls.Image>, `RunIcon.png`, para representar la imagen que se encuentra en el cuadro de diálogo. La imagen se coloca en la primera columna y fila de la <xref:System.Windows.Controls.Grid> (la esquina superior izquierda).  
  
 A continuación, en el ejemplo se agrega un <xref:System.Windows.Controls.TextBlock> elemento a la primera columna, que abarca las columnas restantes de la primera fila. También agrega otro <xref:System.Windows.Controls.TextBlock> elemento a la segunda fila de la primera columna, para representar el **abierto** cuadro de texto. Un <xref:System.Windows.Controls.TextBlock> siguiente, que representa el área de entrada de datos.  
  
 Por último, el ejemplo agrega tres <xref:System.Windows.Controls.Button> elementos a la fila final, que representan el **Aceptar**, **cancelar**, y **examinar** eventos.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/controls/grid-how-to-topics.md)

---
title: 'Cómo: Abarcar filas y columnas en un control TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 5363e7a7def8d2593d3ac474deb9d3d7b77d3912
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44136516"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Cómo: Abarcar filas y columnas en un control TableLayoutPanel
Los controles en un <xref:System.Windows.Forms.TableLayoutPanel> control puede abarcar filas y columnas adyacentes.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-span-columns-and-rows"></a>Para abarcar filas y columnas  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
2.  Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la celda superior izquierda de la <xref:System.Windows.Forms.TableLayoutPanel> control.  
  
3.  Establecer el <xref:System.Windows.Forms.Button> del control **ColumnSpan** propiedad **2**. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control abarca la primera y segunda columna.  
  
4.  Establecer el <xref:System.Windows.Forms.Button> del control **RowSpan** propiedad **2**. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control abarca la primera y segunda fila.  
  
5.  Establecer el <xref:System.Windows.Forms.Button> del control **ColumnSpan** propiedad **1**. Tenga en cuenta que el <xref:System.Windows.Forms.Button> control pasa a la primera columna y abarca la primera y segunda fila.  
  
## <a name="see-also"></a>Vea también  
 [Control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)

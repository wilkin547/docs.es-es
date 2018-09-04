---
title: 'Cómo: Editar columnas y filas en un control TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: 820d2f98290650bfaf377bd2d4b863dfb2e6e704
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500789"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Cómo: Editar columnas y filas en un control TableLayoutPanel
Puede usar el editor de colecciones de la <xref:System.Windows.Forms.TableLayoutPanel> control, denominado el **estilos de columna y fila** cuadro de diálogo, para editar las filas y columnas de los controles.  
  
> [!NOTE]
>  Si desea un control para abarcar varias filas o columnas, establezca el `RowSpan` y `ColumnSpan` las propiedades del control. Para obtener más información, consulta [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Si desea alinear un control dentro de una celda, o si desea que un control se ajuste dentro de una celda, use el control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad. Para obtener más información, consulta [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-edit-rows-and-columns"></a>Para editar filas y columnas  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** hasta su formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.TableLayoutPanel> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **Editar filas y columnas** para abrir el  **Estilos de columna y fila** cuadro de diálogo. También puede hacer a la derecha clic en el <xref:System.Windows.Forms.TableLayoutPanel> control y seleccione **Editar filas y columnas** en el menú contextual.  
  
3.  Para agregar o quitar columnas, seleccione **columnas** desde el **tipo de miembro** cuadro de lista desplegable.  
  
4.  Para agregar o quitar filas, seleccione **filas** desde el **tipo de miembro** cuadro de lista desplegable.  
  
5.  Haga clic en el **agregar** para agregar una fila o columna al final de la **miembro** lista.  
  
6.  Haga clic en el **insertar** para agregar una fila o columna delante del elemento actualmente seleccionado en la lista.  
  
7.  Si va a agregar una fila o columna, seleccione el **tipo tamaño** para la nueva fila o columna. Para obtener más información, consulta <xref:System.Windows.Forms.SizeType>.  
  
8.  Para quitar una fila o columna, haga clic en el **quitar** botón para eliminar el elemento actualmente seleccionado en el **miembro** lista.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SizeType>  
 [Control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)

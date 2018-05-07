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
ms.openlocfilehash: 763d5df6c49d45f7ee305f4a3be0a1f0a2539872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Cómo: Editar columnas y filas en un control TableLayoutPanel
Puede usar el editor de colecciones de la <xref:System.Windows.Forms.TableLayoutPanel> control, denominado el **estilos de columna y fila** cuadro de diálogo para editar las filas y columnas de los controles.  
  
> [!NOTE]
>  Si desea que un control abarque varias filas o columnas, establezca la `RowSpan` y `ColumnSpan` propiedades en el control. Para obtener más información, consulta [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Si desea alinear un control dentro de una celda, o si desea que un control se ajuste dentro de una celda, use el control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad. Para obtener más información, consulta [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-edit-rows-and-columns"></a>Para editar filas y columnas  
  
1.  Arrastre un <xref:System.Windows.Forms.TableLayoutPanel> controlar desde la **cuadro de herramientas** al formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.TableLayoutPanel> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **Editar filas y columnas** para abrir el  **Estilos de columna y fila** cuadro de diálogo. También puede hacer haga clic en el <xref:System.Windows.Forms.TableLayoutPanel> control y seleccione **Editar filas y columnas** en el menú contextual.  
  
3.  Para agregar o quitar columnas, seleccione **columnas** desde el **tipo de miembro** cuadro de lista desplegable.  
  
4.  Para agregar o quitar filas, seleccione **filas** desde el **tipo de miembro** cuadro de lista desplegable.  
  
5.  Haga clic en el **agregar** botón para agregar una fila o columna al final de la **miembro** lista.  
  
6.  Haga clic en el **insertar** botón para agregar una fila o columna antes del elemento actualmente seleccionado en la lista.  
  
7.  Si va a agregar una fila o columna, seleccione la **tipo de tamaño** para la nueva fila o columna. Para obtener más información, consulta <xref:System.Windows.Forms.SizeType>.  
  
8.  Para quitar una fila o columna, haga clic en el **quitar** botón para eliminar el elemento actualmente seleccionado en el **miembro** lista.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SizeType>  
 [Control TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)

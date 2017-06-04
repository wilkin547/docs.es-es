---
title: "C&#243;mo: Editar columnas y filas en un control TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "columnas [Windows Forms], editar"
  - "filas [Windows Forms], editar"
  - "TableLayoutPanel (control) [Windows Forms], editar"
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Editar columnas y filas en un control TableLayoutPanel
Puede utilizar el editor de colecciones del control <xref:System.Windows.Forms.TableLayoutPanel>, en el cuadro de diálogo **Estilos de columna y fila**, para editar las filas y columnas de los controles.  
  
> [!NOTE]
>  Si desea que un control abarque varias filas o columnas, establezca las propiedades `RowSpan` y `ColumnSpan` en el control.  Para obtener más información, vea [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Si desea alinear un control dentro de una celda, o si desea que un control se ajuste dentro de una celda, utilice la propiedad <xref:System.Windows.Forms.Control.Anchor%2A> del control.  Para obtener más información, vea [Tutorial: Organizar controles en formularios Windows Forms mediante TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para editar filas y columnas  
  
1.  Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> desde el **Cuadro de herramientas** al formulario.  
  
2.  Haga clic en el glifo \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) de la etiqueta inteligente del control <xref:System.Windows.Forms.TableLayoutPanel> y seleccione **Editar filas y columnas** para abrir el cuadro de diálogo **Estilos de columna y fila**.  También puede hacer clic con el botón secundario del mouse en el control <xref:System.Windows.Forms.TableLayoutPanel> y seleccionar **Editar filas y columnas** en el menú contextual.  
  
3.  Para agregar o quitar columnas, seleccione **Columnas** en el cuadro de lista desplegable **Tipo de miembro**.  
  
4.  Para agregar o quitar filas, seleccione **Filas** en el cuadro de lista desplegable **Tipo de miembro**.  
  
5.  Haga clic en el botón **Agregar** para agregar una fila o columna al final de la lista **Miembro**.  
  
6.  Haga clic en el botón **Insertar** para agregar una fila o columna antes del elemento seleccionado en la lista.  
  
7.  Si está agregando una fila o columna, seleccione el **Tamaño** para la nueva fila o columna.  Para obtener más información, vea <xref:System.Windows.Forms.SizeType>.  
  
8.  Para quitar una fila o columna, haga clic en el botón **Quitar** para eliminar el elemento seleccionado de la lista **Miembro**.  
  
## Vea también  
 <xref:System.Windows.Forms.SizeType>   
 [TableLayoutPanel \(Control\)](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
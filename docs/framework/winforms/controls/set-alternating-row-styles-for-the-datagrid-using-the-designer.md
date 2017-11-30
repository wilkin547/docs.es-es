---
title: "Cómo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8d78509a7d088511096d2e02e8e6603ba5fe5c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador
Datos tabulares a menudo se presentan en un formato de carta donde las filas alternas tienen distintos colores de fondo. Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.  
  
 Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas. Puede utilizar las características de estilo como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas. Para obtener más información, consulte [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="define-styles-for-alternating-rows"></a>Definir estilos para filas alternas  
  
1.  Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.  
  
2.  En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> propiedad.  
  
3.  En el **generador de CellStyle** definir el estilo estableciendo las propiedades de cuadro de diálogo y usar el **vista previa** panel para confirmar las opciones seleccionadas. Los estilos que especifique se usan para todas las demás filas mostrado en el control, a partir de la otra.  
  
4.  Para definir estilos para las filas restantes, repita los pasos 2 y 3 mediante la <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> propiedad.  
  
    > [!NOTE]
    >  Las celdas se muestran mediante estilos heredados de varias propiedades. Para obtener más información acerca de la herencia de estilo, consulte [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Utilizar el Diseñador con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)  
 [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)

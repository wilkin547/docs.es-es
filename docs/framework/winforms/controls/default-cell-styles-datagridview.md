---
title: 'Cómo: Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 47e15afe71ed3497b634e965c96badcee2fe3ed4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529943"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el diseñador
El <xref:System.Windows.Forms.DataGridView> control le permite especificar los estilos de celda predeterminados y formatos de datos para todo el control, para determinadas columnas, para los encabezados de fila y columna y para filas alternas para crear un efecto de libro de contabilidad de celda. Los estilos predeterminados establecidos para todo el control se reemplazan por los estilos predeterminados establecidos para las columnas y las filas alternas. Además, los estilos que se establecen en el código para filas y celdas individuales reemplazan los estilos predeterminados.  
  
 Para obtener más información sobre los estilos de celda, vea [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Para establecer los estilos para las filas alternas, vea [Cómo: establecer estilos de fila alternos para el Control Windows Forms DataGridView mediante el diseñador](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 También puede establecer estilos mediante la <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad afecta a todas las filas que se agregarán al control. Para obtener más información acerca de la plantilla de fila, vea [Cómo: usar la plantilla de filas para personalizar filas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Los procedimientos siguientes requieren un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Para establecer los estilos predeterminados para todas las celdas en el control  
  
1.  Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.  
  
2.  En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> propiedad. El **generador de CellStyle** aparece el cuadro de diálogo.  
  
3.  Definir el estilo estableciendo las propiedades, mediante la **vista previa** panel para confirmar las opciones seleccionadas.  
  
> [!NOTE]
>  Si se habilitan estilos visuales, los encabezados de fila y columna (excepto para la <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) reciben automáticamente el estilo del tema actual, reemplazar el <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> valores de propiedad.  
>   
>  Puede establecer estilos de celda para varios elementos seleccionados <xref:System.Windows.Forms.DataGridView> controla mediante el diseñador, pero solo si tienen valores idénticos para la propiedad de estilo de celda que desea modificar. Si difieren de los estilos de celda para esa propiedad, el **propiedades** windows de la **generador de CellStyle** cuadro de diálogo estará en blanco.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Para establecer los estilos predeterminados para las celdas en columnas individuales  
  
1.  Haga clic en el <xref:System.Windows.Forms.DataGridView> en el Diseñador de control y elija **Editar columnas**.  
  
2.  Seleccione una columna en la **columnas seleccionadas** lista.  
  
3.  En el **propiedades de columna** cuadrícula, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad. El **generador de CellStyle** aparece el cuadro de diálogo.  
  
4.  Definir el estilo estableciendo las propiedades, mediante la **vista previa** panel para confirmar las opciones seleccionadas.  
  
### <a name="to-format-data-in-cells"></a>Dar formato a datos en celdas  
  
1.  Utilice uno de los procedimientos anteriores para mostrar un **generador de CellStyle** cuadro de diálogo relacionados con una propiedad de estilo de celda predeterminado.  
  
2.  En el **generador de CellStyle** diálogo cuadro, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> propiedad. El **cadena de formato** aparece el cuadro de diálogo.  
  
3.  Seleccione un tipo de formato, a continuación, modifique los detalles del tipo (por ejemplo, el número de posiciones decimales que se van a mostrar), mediante el **ejemplo** cuadro para confirmar las opciones.  
  
4.  Si va a enlazar la <xref:System.Windows.Forms.DataGridView> control a un origen de datos que es probable que contengan valores nulos, rellene el **valor Null** cuadro de texto. Este valor se muestra cuando el valor de celda es igual a una referencia nula (`Nothing` en Visual Basic) o <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)

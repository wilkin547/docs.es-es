---
title: Crear un control DataGridView sin enlazar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740178"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a>Tutorial: Crear un control DataGridView sin enlazar en formularios Windows Forms
Con frecuencia, es posible que desee Mostrar datos tabulares que no se originen en una base de datos. Por ejemplo, puede que desee mostrar el contenido de una matriz bidimensional de cadenas. La clase <xref:System.Windows.Forms.DataGridView> proporciona una manera fácil y muy personalizable de Mostrar datos sin enlazar a un origen de datos. En este tutorial se muestra cómo rellenar un control de <xref:System.Windows.Forms.DataGridView> y administrar la adición y eliminación de filas en modo "sin enlazar". De forma predeterminada, el usuario puede agregar nuevas filas. Para evitar la adición de filas, establezca la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> es `false`.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: crear un control DataGridView de Windows Forms independiente](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-use-an-unbound-datagridview-control"></a>Para usar un control DataGridView sin enlazar  
  
1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga las siguientes declaraciones de variable y `Main` método.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. Implemente un método `SetupLayout` en la definición de clase del formulario para configurar el diseño del formulario.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. Cree un método `SetupDataGridView` para configurar las columnas y propiedades de <xref:System.Windows.Forms.DataGridView>.  
  
     Este método agrega primero el control <xref:System.Windows.Forms.DataGridView> a la colección <xref:System.Windows.Forms.Control.Controls%2A> del formulario. A continuación, se establece el número de columnas que se van a mostrar mediante la propiedad <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>. El estilo predeterminado de los encabezados de columna se establece mediante el establecimiento de las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>y <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> de la <xref:System.Windows.Forms.DataGridViewCellStyle> devuelta por la propiedad <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>.  
  
     Se establecen las propiedades de diseño y apariencia, y se asignan los nombres de columna. Cuando este método finaliza, el control de <xref:System.Windows.Forms.DataGridView> está listo para rellenarse.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. Cree un método `PopulateDataGridView` para agregar filas al control <xref:System.Windows.Forms.DataGridView>.  
  
     Cada fila representa una canción y su información asociada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. Con los métodos de utilidad en su lugar, puede adjuntar controladores de eventos.  
  
     Controlará los eventos de <xref:System.Windows.Forms.Control.Click> de los botones **Agregar** y **eliminar** , el evento de <xref:System.Windows.Forms.Form.Load> del formulario y el evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del control <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se genera el evento <xref:System.Windows.Forms.Control.Click> del botón **Agregar** , se agrega una nueva fila vacía al <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se genera el evento <xref:System.Windows.Forms.Control.Click> del botón **eliminar** , se elimina la fila seleccionada, a menos que sea la fila de los nuevos registros, lo que permite al usuario agregar nuevas filas. Esta fila siempre es la última fila del control <xref:System.Windows.Forms.DataGridView>.  
  
     Cuando se genera el evento de <xref:System.Windows.Forms.Form.Load> del formulario, se llama a los métodos de utilidad `SetupLayout`, `SetupDataGridView`y `PopulateDataGridView`.  
  
     Cuando se genera el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>, se da formato a cada celda de la columna `Date` como una fecha larga, a menos que no se pueda analizar el valor de la celda.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
- Presione F5 para ejecutar la aplicación.  
  
     Verá un control de <xref:System.Windows.Forms.DataGridView> que muestra las canciones enumeradas en `PopulateDataGridView`. Puede agregar nuevas filas con el botón **Agregar fila** y puede eliminar las filas seleccionadas con el botón **Eliminar fila** . El control de <xref:System.Windows.Forms.DataGridView> sin enlazar es el almacén de datos y sus datos son independientes de cualquier origen externo, como un <xref:System.Data.DataSet> o una matriz.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación ofrece una descripción básica de las capacidades del control de <xref:System.Windows.Forms.DataGridView>. Puede personalizar la apariencia y el comportamiento del control de <xref:System.Windows.Forms.DataGridView> de varias maneras:  
  
- Cambiar los estilos de borde y encabezado. Para obtener más información, vea [Cómo: cambiar los estilos de borde y de línea de cuadrícula en el control DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Habilitar o restringir la entrada del usuario al control de <xref:System.Windows.Forms.DataGridView>. Para obtener más información, vea [Cómo: impedir la adición y eliminación de filas en el control datagridview Windows Forms](prevent-row-addition-and-deletion-datagridview.md)y [Cómo: crear columnas de solo lectura en el control DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Compruebe la entrada del usuario para ver si hay errores relacionados con la base de datos. Para obtener más información, vea [Tutorial: controlar los errores que se producen durante la entrada de datos en el control DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
- Administrar conjuntos de datos muy grandes mediante el modo virtual. Para obtener más información, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Personalizar la apariencia de las celdas. Para obtener más información, vea [Cómo: personalizar la apariencia de las celdas en el control datagridview Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Crear un control DataGridView no enlazado en formularios Windows Forms](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)

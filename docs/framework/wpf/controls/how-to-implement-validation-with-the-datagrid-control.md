---
title: Procedimiento para implementar la validación con el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 38b4c9cd7679f0d8da9b18fb5bd6bb729d33ed54
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646097"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a>Procedimiento para implementar la validación con el control DataGrid
El <xref:System.Windows.Controls.DataGrid> control le permite realizar la validación en el nivel de celda y fila. Con la validación de nivel de celda, se validan las propiedades individuales de un objeto de datos enlazado cuando un usuario actualiza un valor. Con la validación de nivel de fila, se validan objetos de datos completos cuando un usuario confirma los cambios en una fila. También puede proporcionar comentarios visuales personalizados para errores <xref:System.Windows.Controls.DataGrid> de validación o usar los comentarios visuales predeterminados que proporciona el control.  
  
 Los procedimientos siguientes describen <xref:System.Windows.Controls.DataGrid> cómo aplicar reglas de validación a los enlaces y personalizar los comentarios visuales.  
  
### <a name="to-validate-individual-cell-values"></a>Para validar valores de celda individuales  
  
- Especifique una o varias reglas de validación en el enlace utilizado con una columna. Esto es similar a la validación de datos en controles simples, como se describe en Información general sobre [el enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .  
  
     En el ejemplo <xref:System.Windows.Controls.DataGrid> siguiente se muestra un control con cuatro columnas enlazadas a diferentes propiedades de un objeto de negocio. Tres de las <xref:System.Windows.Controls.ExceptionValidationRule> columnas especifican <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> el `true`estableciendo la propiedad en .  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Cuando un usuario escribe un valor no válido (por ejemplo, un no entero en la columna ID de curso), aparece un borde rojo alrededor de la celda. Puede cambiar estos comentarios de validación predeterminados como se describe en el siguiente procedimiento.  
  
### <a name="to-customize-cell-validation-feedback"></a>Para personalizar los comentarios de validación de celdas  
  
- Establezca la propiedad <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> de la columna en un estilo adecuado para el control de edición de la columna. Dado que los controles de edición se <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> crean en tiempo de ejecución, no puede usar la propiedad adjunta como lo haría con controles simples.  
  
     En el ejemplo siguiente se actualiza el ejemplo anterior agregando un estilo de error compartido por las tres columnas con reglas de validación. Cuando un usuario escribe un valor no válido, el estilo cambia el color de fondo de la celda y agrega una información sobre herramientas. Tenga en cuenta el uso de un desencadenador para determinar si hay un error de validación. Esto es necesario porque actualmente no hay ninguna plantilla de error dedicada para las celdas.  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Puede implementar una personalización más <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> amplia reemplazando el utilizado por la columna.  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a>Para validar varios valores en una sola fila  
  
1. Implemente <xref:System.Windows.Controls.ValidationRule> una subclase que compruebe varias propiedades del objeto de datos enlazado. En <xref:System.Windows.Controls.ValidationRule.Validate%2A> la implementación `value` del método, <xref:System.Windows.Data.BindingGroup> convierta el valor del parámetro en una instancia. A continuación, puede tener <xref:System.Windows.Data.BindingGroup.Items%2A> acceso al objeto de datos a través de la propiedad.  
  
     En el ejemplo siguiente se muestra `StartDate` este proceso `Course` para validar si `EndDate` el valor de propiedad de un objeto es anterior a su valor de propiedad.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. Agregue la regla <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> de validación a la colección. La <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> propiedad proporciona acceso <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> directo <xref:System.Windows.Data.BindingGroup> a la propiedad de una instancia que agrupa todos los enlaces utilizados por el control.  
  
     En el ejemplo <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> siguiente se establece la propiedad en XAML. La <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> propiedad se <xref:System.Windows.Controls.ValidationStep.UpdatedValue> establece para que la validación se produzca solo después de actualizar el objeto de datos enlazado.  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Cuando un usuario especifica una fecha de finalización anterior a la fecha de inicio, aparece un signo de exclamación rojo (!) en el encabezado de fila. Puede cambiar estos comentarios de validación predeterminados como se describe en el siguiente procedimiento.  
  
### <a name="to-customize-row-validation-feedback"></a>Para personalizar los comentarios de validación de filas  
  
- Establecer la propiedad <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType>. Esta propiedad le permite personalizar los <xref:System.Windows.Controls.DataGrid> comentarios de validación de fila para controles individuales. También puede afectar a varios controles mediante un <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> estilo de fila implícito para establecer la propiedad.  
  
     En el ejemplo siguiente se reemplazan los comentarios de validación de fila predeterminados por un indicador más visible. Cuando un usuario escribe un valor no válido, aparece un círculo rojo con un signo de exclamación blanco en el encabezado de fila. Esto ocurre para los errores de validación de fila y celda. El mensaje de error asociado se muestra en una información sobre herramientas.  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se proporciona una demostración completa para la validación de celdas y filas. La `Course` clase proporciona un objeto <xref:System.ComponentModel.IEditableObject> de datos de ejemplo que se implementa para admitir transacciones. El <xref:System.Windows.Controls.DataGrid> control interactúa <xref:System.ComponentModel.IEditableObject> con para permitir a los usuarios revertir los cambios presionando ESC.  
  
> [!NOTE]
> Si usa Visual Basic, en la primera línea de `x:Class="DataGridValidation.MainWindow"` `x:Class="MainWindow"`MainWindow.xaml, reemplace por .  
  
 Para probar la validación, pruebe lo siguiente:  
  
- En la columna ID del curso, escriba un valor que no sea entero.  
  
- En la columna Fecha de finalización, especifique una fecha anterior a la Fecha de inicio.  
  
- Elimine el valor de ID de curso, Fecha de inicio o Fecha de finalización.  
  
- Para deshacer un valor de celda no válido, vuelva a colocar el cursor en la celda y presione la tecla ESC.  
  
- Para deshacer los cambios de una fila completa cuando la celda actual está en modo de edición, presione la tecla ESC dos veces.  
  
- Cuando se produce un error de validación, mueva el puntero del mouse sobre el indicador en el encabezado de fila para ver el mensaje de error asociado.  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.DataGrid>
- [DataGrid](datagrid.md)
- [Enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Implementar validación de enlace](../data/how-to-implement-binding-validation.md)
- [Implementar lógica de validación en objetos personalizados](../data/how-to-implement-validation-logic-on-custom-objects.md)

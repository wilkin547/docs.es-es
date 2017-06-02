---
title: "C&#243;mo: Implementar la validaci&#243;n con el control DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], validación"
  - "validación [WPF], DataGrid"
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Implementar la validaci&#243;n con el control DataGrid
El control <xref:System.Windows.Controls.DataGrid> permite realizar la validación en el nivel de celda y de fila.  Con la validación de nivel de celda, se validan las propiedades individuales de un objeto de datos enlazado cuando un usuario actualiza un valor.  Con la validación de nivel de fila, se validan los objetos de datos completos cuando un usuario confirma los cambios en una fila.  También puede proporcionar comentarios visuales personalizados para los errores de validación o usar los comentarios visuales predeterminados que ofrece el control <xref:System.Windows.Controls.DataGrid>.  
  
 En los siguientes procedimientos se describe cómo aplicar las reglas de validación a los enlaces <xref:System.Windows.Controls.DataGrid> y personalizar los comentarios visuales.  
  
### Para validar los valores de celdas individuales  
  
-   Especifique una o más reglas de validación en el enlace que se usa con una columna.  Esto es similar a validar los datos de controles simples, tal y como se describe en [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
     En el siguiente ejemplo se muestra un control <xref:System.Windows.Controls.DataGrid> con cuatro columnas enlazadas a distintas propiedades de un objeto de negocio.  Tres de las columnas especifican <xref:System.Windows.Controls.ExceptionValidationRule> estableciendo la propiedad <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> en `true`.  
  
     [!code-xml[DataGrid_Validation#BasicXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     Cuando un usuario escribe un valor no válido \(como un valor no entero en la columna del identificador del curso\), aparece un borde rojo alrededor de la celda.  Se pueden cambiar estos comentarios de validación predeterminados, tal como se describe en el siguiente procedimiento.  
  
### Para personalizar los comentarios de validación de celda  
  
-   Establezca la propiedad <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> de la columna en un estilo adecuado para el control de edición de la columna.  Dado que los controles de edición se crean en tiempo de ejecución, no puede usar la propiedad adjunta <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=fullName> como lo haría con los controles simples.  
  
     En el siguiente ejemplo se actualiza el ejemplo anterior agregando un estilo de error compartido por las tres columnas con reglas de validación.  Cuando un usuario escribe un valor no válido, el estilo cambia el color de fondo de la celda y agrega información sobre herramientas.  Observe que se usa un desencadenador para determinar si hay un error de validación.  Es necesario, ya que actualmente no hay ninguna plantilla de error dedicada para las celdas.  
  
     [!code-xml[DataGrid_Validation#CellValidationXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     Puede implementar una personalización más extensa reemplazando la propiedad <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> que usa la columna.  
  
### Para validar varios valores en una sola fila  
  
1.  Implemente una subclase <xref:System.Windows.Controls.ValidationRule> que compruebe varias propiedades del objeto de datos enlazado.  En su implementación del método <xref:System.Windows.Controls.ValidationRule.Validate%2A>, convierta el valor del parámetro `value` a una instancia de <xref:System.Windows.Data.BindingGroup>.  Después, podrá tener acceso al objeto de datos a través de la propiedad <xref:System.Windows.Data.BindingGroup.Items%2A>.  
  
     En el siguiente ejemplo se muestra este proceso para validar si el valor de propiedad `StartDate` de un objeto `Course` es anterior al valor de propiedad `EndDate`.  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2.  Agregue la regla de validación a la colección <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=fullName>.  La propiedad <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> proporciona acceso directo a la propiedad <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> de una instancia de <xref:System.Windows.Data.BindingGroup> que agrupa todos los enlaces que usa el control.  
  
     En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> en XAML.  La propiedad <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> se establece en <xref:System.Windows.Controls.ValidationStep> para que la validación se produzca únicamente después de que se actualice el objeto de datos enlazado.  
  
     [!code-xml[DataGrid_Validation#RowValidationRulesXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     Cuando un usuario especifica una fecha de finalización que es anterior a la fecha de inicio, aparece un signo de admiración rojo \(\!\) en el encabezado de fila.  Se pueden cambiar estos comentarios de validación predeterminados, tal como se describe en el siguiente procedimiento.  
  
### Para personalizar los comentarios de validación de fila  
  
-   Establezca la propiedad <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=fullName>.  Esta propiedad permite personalizar los comentarios de validación de fila de controles <xref:System.Windows.Controls.DataGrid> individuales.  También puede afectar a varios controles utilizando un estilo de fila implícito para establecer la propiedad <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=fullName>.  
  
     En el siguiente ejemplo se reemplazan los comentarios de validación de fila predeterminados con un indicador más visible.  Cuando un usuario escribe un valor no válido, aparece un círculo rojo con un signo de admiración blanco en el encabezado de fila.  Esto se produce para los errores de validación de fila y de celda.  El mensaje de error asociado se muestra en una información sobre herramientas.  
  
     [!code-xml[DataGrid_Validation#RowValidationFeedbackXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## Ejemplo  
 En el siguiente ejemplo se proporciona una demostración completa de la validación de celda y fila.  La clase `Course` proporciona un objeto de datos de ejemplo que implementa <xref:System.ComponentModel.IEditableObject> para admitir las transacciones.  El control <xref:System.Windows.Controls.DataGrid> interactúa con <xref:System.ComponentModel.IEditableObject> para permitir a los usuarios revertir los cambios presionando ESC.  
  
> [!NOTE]
>  Si usa Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="DataGridValidation.MainWindow"` con `x:Class="MainWindow"`.  
  
 Para probar la validación, intente lo siguiente:  
  
-   En la columna del identificador del curso, especifique un valor no entero.  
  
-   En la columna de la fecha de finalización, escriba una fecha que sea anterior a la fecha de inicio.  
  
-   Elimine el valor del identificador de curso, fecha de inicio o fecha de finalización.  
  
-   Para deshacer un valor de celda no válido, vuelva a poner el cursor en la celda y presione la tecla ESC.  
  
-   Para deshacer los cambios de una fila completa cuando la celda actual está en modo de edición, presione la tecla ESC dos veces.  
  
-   Cuando se produzca un error de validación, mueva el puntero del mouse sobre el indicador del encabezado de fila para ver el mensaje de error asociado.  
  
 [!code-csharp[DataGrid_Validation#FullCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xml[DataGrid_Validation#FullXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## Vea también  
 <xref:System.Windows.Controls.DataGrid>   
 [DataGrid](../../../../docs/framework/wpf/controls/datagrid.md)   
 [Enlace de datos](../../../../docs/framework/wpf/data/data-binding-wpf.md)   
 [Implementar la validación de enlaces](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [Implementar lógica de validación en objetos personalizados](../../../../docs/framework/wpf/data/how-to-implement-validation-logic-on-custom-objects.md)
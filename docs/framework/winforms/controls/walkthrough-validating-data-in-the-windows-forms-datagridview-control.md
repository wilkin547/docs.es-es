---
title: "Tutorial: Validar datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "datos [Windows Forms], validación"
  - "cuadrículas de datos, validar datos"
  - "validación de datos, Windows Forms"
  - "DataGridView (control) [Windows Forms], validación de datos"
  - "validar datos, Windows Forms"
  - "tutoriales [Windows Forms], DataGridView (control)"
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Tutorial: Validar datos en el control DataGridView de formularios Windows Forms
Cuando muestra funciones de entrada de datos a los usuarios, a menudo tiene que validar los datos escritos en el formulario.  La clase <xref:System.Windows.Forms.DataGridView> proporciona una manera cómoda de realizar la validación antes de que los datos se confirmen en el almacén de datos.  Puede validar los datos controlando el evento <xref:System.Windows.Forms.DataGridView.CellValidating>, que lo provoca <xref:System.Windows.Forms.DataGridView> cuando cambia la celda actual.  
  
 En este tutorial, recuperará filas de la tabla `Customers` de la base de datos de ejemplo Northwind y las mostrará en un control <xref:System.Windows.Forms.DataGridView>.  Cuando un usuario edita una celda de la columna `CompanyName` e intenta abandonar la celda, el controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValidating> examinará la cadena del nuevo nombre de empresa para asegurarse de que no está vacía; si el nuevo valor es una cadena vacía, <xref:System.Windows.Forms.DataGridView> impedirá que el cursor del usuario abandone la celda hasta que no se especifique una cadena que no esté vacía.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Acceso a un servidor con la base de datos de ejemplo Northwind de SQL Server.  
  
## Crear el formulario  
  
#### Para validar datos escritos en un DataGridView  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un control <xref:System.Windows.Forms.DataGridView> y un componente <xref:System.Windows.Forms.BindingSource>.  
  
     En el ejemplo de código siguiente se proporciona la inicialización básica y se incluye un método `Main`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implemente un método en la definición de clase del formulario para controlar los detalles de conexión con la base de datos.  
  
     En este ejemplo de código se utiliza un método  `GetData`  que devuelve un objeto <xref:System.Data.DataTable> rellenado.  Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  
  
    > [!IMPORTANT]
    >  El hecho de almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows, también conocida como seguridad integrada, es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, vea [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.BindingSource> y configura el enlace de datos.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implemente los controladores para los eventos <xref:System.Windows.Forms.DataGridView.CellValidating> y <xref:System.Windows.Forms.DataGridView.CellEndEdit> del control <xref:System.Windows.Forms.DataGridView>.  
  
     El controlador de eventos <xref:System.Windows.Forms.DataGridView.CellValidating> es donde se determina si el valor de una celda de la columna `CompanyName` está vacío.  Si el valor de celda no supera la validación, establezca la propiedad <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> de la clase <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=fullName> en `true`.  Esto hace que el control <xref:System.Windows.Forms.DataGridView> evite que el cursor abandone la celda.  Establezca la propiedad <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> en la fila en una cadena explicativa.  Esto muestra un icono de error con la información sobre herramientas que contiene el texto del error.  En el controlador de eventos <xref:System.Windows.Forms.DataGridView.CellEndEdit>, establezca la propiedad <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> en la fila en la cadena vacía.  El evento <xref:System.Windows.Forms.DataGridView.CellEndEdit> sólo aparece cuando la celda sale del modo de edición, que no puede hacerlo si no se supera la validación.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> rellenado con datos de la tabla `Customers`.  Si hace doble clic en una celda de la columna `CompanyName`, puede editar el valor.  Si elimina todos los caracteres y presiona la tecla TAB para salir de la celda, <xref:System.Windows.Forms.DataGridView> impide que salga.  Cuando escribe una cadena no vacía en la celda, el control <xref:System.Windows.Forms.DataGridView> le permite salir de la celda.  
  
## Pasos siguientes  
 Esta aplicación proporciona conocimientos básicos sobre las funciones del control <xref:System.Windows.Forms.DataGridView>.  Puede personalizar la apariencia y el comportamiento del control <xref:System.Windows.Forms.DataGridView> de varias formas:  
  
-   Cambie los estilos de borde y encabezado.  Para obtener más información, vea [Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Permita o restringa los datos proporcionados por el usuario al control <xref:System.Windows.Forms.DataGridView>.  Para obtener más información, vea [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) y [Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Compruebe si los datos proporcionados por el usuario tienen errores relacionados con base de datos.  Para obtener más información, vea [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Controle conjuntos de grandes volúmenes de datos utilizando el modo virtual.  Para obtener más información, vea [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalice la apariencia de las celdas.  Para obtener más información, vea [Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) y [Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)   
 [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)
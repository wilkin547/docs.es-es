---
title: "C&#243;mo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms | Microsoft Docs"
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
  - "mensajes de error, ver en conjuntos de datos"
  - "ErrorProvider (componente) [Windows Forms], errores del conjunto de datos"
  - "errores [Windows Forms], errores del conjunto de datos"
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms
Se puede utilizar el componente <xref:System.Windows.Forms.ErrorProvider> de formularios Windows Forms para ver los errores de cada columna dentro de un conjunto de datos o en otro origen de datos.  Para que un componente <xref:System.Windows.Forms.ErrorProvider> muestre errores de datos en un formulario, no es necesario que esté directamente asociado a un control.  Una vez enlazado a un origen de datos, puede mostrar un icono de error junto a cualquier control que esté enlazado al mismo origen de datos.  
  
> [!NOTE]
>  Si se cambian las propiedades <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> y <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> del proveedor de errores en tiempo de ejecución, se debe utilizar el método <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> para evitar conflictos.  
  
### Para mostrar errores de datos  
  
1.  Enlace el componente a una columna específica dentro de una tabla de datos.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
  
    ```  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> en el formulario.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
  
    ```  
  
3.  Establezca la posición del registro actual en una fila que contenga un error de columna.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
  
    ```  
  
## Vea también  
 [Información general del componente ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
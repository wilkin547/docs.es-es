---
title: "C&#243;mo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos | Microsoft Docs"
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
  - "controles enlazados, cuadros combinados"
  - "cuadros combinados, enlace de datos"
  - "ComboBox (control) [Windows Forms], enlace de datos"
  - "datos [Windows Forms], enlazar a controles"
  - "enlace de datos, cuadros combinados"
  - "controles enlazados a datos, Windows Forms"
  - "cuadros de lista, enlace de datos"
  - "ListBox (control) [Windows Forms], enlace de datos"
  - "controles de Windows Forms, enlace de datos"
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos
Puede enlazar el control <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> a datos para realizar tareas como examinar datos de una base de datos, introducir nuevos datos o editar datos existentes.  
  
### Para enlazar un control ComboBox o ListBox  
  
1.  Establezca un objeto de origen de datos como el valor de la propiedad `DataSource` .  Entre los posibles orígenes de datos se encuentran los <xref:System.Windows.Forms.BindingSource> enlazados a datos, las tablas de datos, las vistas de datos, los conjuntos de datos, los administradores de vistas de datos, las matrices o cualquier clase que implemente la interfaz <xref:System.Collections.IList>.  Para obtener más información, vea [Orígenes de datos compatibles con formularios Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  Si enlaza con una tabla, establezca la propiedad `DisplayMember`  en el nombre de una columna del origen de datos.  
  
     \-O bien\-  
  
     Si enlaza con <xref:System.Collections.IList>, establezca el miembro de presentación en una propiedad pública del tipo de la lista.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
  
    ```  
  
    > [!NOTE]
    >  Si enlaza con un origen de datos que no implementa la interfaz <xref:System.ComponentModel.IBindingList>, como un objeto <xref:System.Collections.ArrayList>, no se actualizarán los datos del control enlazado cuando se actualice el origen de datos.  Por ejemplo, si tiene un cuadro combinado enlazado a un objeto <xref:System.Collections.ArrayList> y se agregan datos a <xref:System.Collections.ArrayList>, estos nuevos elementos no aparecerán en el cuadro combinado.  Sin embargo, puede forzar la actualización del cuadro combinado llamando a los métodos <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> y <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> de la instancia de la clase <xref:System.Windows.Forms.BindingContext> a la que está enlazado el control.  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Enlace de datos y formularios Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
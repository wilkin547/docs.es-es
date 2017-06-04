---
title: "C&#243;mo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms | Microsoft Docs"
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
  - "controles [formularios Windows Forms], manipular"
  - "Control BindingNavigator [formularios Windows Forms], agregar botones"
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms
El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> de propósito especial pensado para navegar y manipular controles enlazados a datos en el formulario.  
  
 Dado que es un control <xref:System.Windows.Forms.ToolStrip>, el componente <xref:System.Windows.Forms.BindingNavigator> se puede modificar con facilidad para incluir comandos adicionales o alternativos para el usuario.  
  
 En el procedimiento siguiente, el control <xref:System.Windows.Forms.TextBox> está enlazado a datos, y el control <xref:System.Windows.Forms.ToolStrip> que se agrega al formulario se modifica para incluir los botones Cargar, Guardar y Cancelar.  
  
### Para agregar los botones Cargar, Guardar y Cancelar al componente BindingNavigator  
  
1.  Agregue el control <xref:System.Windows.Forms.TextBox> al formulario.  
  
2.  Enlácelo a un <xref:System.Windows.Forms.BindingSource>, que se enlaza a un origen de datos.  En este ejemplo, <xref:System.Windows.Forms.BindingSource> se enlaza a una base de datos.  
  
3.  Después de generar el conjunto de datos y el adaptador de la tabla, arrastre un control <xref:System.Windows.Forms.BindingNavigator> hacia el formulario.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> del control <xref:System.Windows.Forms.BindingNavigator> en <xref:System.Windows.Forms.BindingSource> en el formulario que se enlaza a los controles.  
  
5.  Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) para que aparezca el cuadro de diálogo **Tareas de BindingNavigator** y seleccione **Editar elementos**.  
  
     Aparecerá el **Editor de la colección de elementos**.  
  
7.  En el **Editor de la colección de elementos**, complete lo siguiente:  
  
    1.  Agregue un <xref:System.Windows.Forms.ToolStripSeparator> y tres elementos <xref:System.Windows.Forms.ToolStripButton> seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haciendo clic en el botón **Agregar**.  
  
    2.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Name%2A> de los botones en `` LoadButton, `` SaveButton y `` CancelButton, respectivamente.  
  
    3.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> de los botones en  ``  Load`,` Save y `` Cancel.  
  
    4.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> para cada uno de los botones en  `` Text.  Otra opción es establecer esta propiedad en `` Image `` o `` ImageAndText `` y establecer la imagen para que aparezca en la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A>.  
  
    5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Los botones se agregan a <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Haga clic con el botón secundario del mouse en el formulario y elija **Ver código**.  
  
9. En el Editor de código, busque la línea de código que carga los datos en el adaptador de la tabla.  Este código se generó cuando configuró el enlace de datos en el paso 2.  El código puede ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)` Probablemente estará en el evento <xref:System.Windows.Forms.Form.Load> del formulario.  
  
10. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del `` <xref:System.Windows.Forms.ToolStripButton> `` **Load** que creó anteriormente y pásele todo el código de carga de datos.  
  
     El código ahora debe ser similar al siguiente:  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del  `T:System.Windows.Forms.ToolStripButton`**Save** que creó anteriormente y escriba código para actualizar los datos de la tabla a la que está enlazado el control.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  En algunos casos, el componente <xref:System.Windows.Forms.BindingNavigator> ya tendrá un botón `` **Guardar**, pero el Diseñador de Windows Forms no habrá generado ningún código.  En este caso, puede colocar el código anterior en el controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para ese botón, en lugar de crear un botón totalmente nuevo en <xref:System.Windows.Forms.ToolStrip>.  Sin embargo, el botón está deshabilitado de forma predeterminada, por tanto debe establecer la propiedad <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> del botón en `true` para que el botón funcione correctamente.  
  
12. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del `` <xref:System.Windows.Forms.ToolStripButton> `` **Cancel** que creó anteriormente y escriba código para cancelar los cambios del registro de datos que aparece.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  El método <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> está en el ámbito de la fila de datos.  Guarde los cambios que haya realizado al ver el registro concreto antes de navegar hasta el registro siguiente.  
  
## Vea también  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.ToolStrip>   
 [BindingNavigator \(Control\)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Información general sobre el componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
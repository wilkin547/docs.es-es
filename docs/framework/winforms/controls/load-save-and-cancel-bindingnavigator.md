---
title: "Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4bc4f53c404e3767b9f98ca5ab46b19db31f9c6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms
El <xref:System.Windows.Forms.BindingNavigator> control es un propósito especial <xref:System.Windows.Forms.ToolStrip> control que está pensado para navegar y manipular los controles en el formulario que están enlazados a datos.  
  
 Porque es un <xref:System.Windows.Forms.ToolStrip> (control), el <xref:System.Windows.Forms.BindingNavigator> componente puede modificarse fácilmente para incluir comandos adicionales o alternativos para el usuario.  
  
 En el siguiente procedimiento, un <xref:System.Windows.Forms.TextBox> control se enlaza a datos y el <xref:System.Windows.Forms.ToolStrip> control que se agrega al formulario se modifica para incluir cargar, guardar y cancelar botones.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Para agregar una carga, guardar, botones y Cancelar al componente BindingNavigator  
  
1.  Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
2.  Enlazar a un <xref:System.Windows.Forms.BindingSource>, que está enlazado a un origen de datos. En este ejemplo, el <xref:System.Windows.Forms.BindingSource> está enlazado a una base de datos.  
  
3.  Después de generar el adaptador de conjunto de datos y tabla, arrastre un <xref:System.Windows.Forms.BindingNavigator> control al formulario.  
  
4.  Establecer el <xref:System.Windows.Forms.BindingNavigator> del control <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> propiedad a la <xref:System.Windows.Forms.BindingSource> en el formulario que se enlaza a los controles.  
  
5.  Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) por lo que la **tareas BindingNavigator** cuadro de diálogo aparece y seleccione **editar elementos**.  
  
     El **Editor de la colección de elementos** aparece.  
  
7.  En el **Editor de la colección de elementos**, realice los pasos siguientes:  
  
    1.  Agregar un <xref:System.Windows.Forms.ToolStripSeparator> y tres <xref:System.Windows.Forms.ToolStripButton> elementos seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haga clic en el **agregar** botón.  
  
    2.  Establecer el <xref:System.Windows.Forms.ToolStripItem.Name%2A> propiedad de los botones para**LoadButton**,**SaveButton**, y**CancelButton**, respectivamente.  
  
    3.  Establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad de los botones para**carga** `,` **guardar**, y**cancelar**.  
  
    4.  Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad para cada uno de los botones para**texto**. Como alternativa, puede establecer esta propiedad en**imagen**o**ImageAndText**y establecer la imagen que se mostrará en el <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad.  
  
    5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Los botones se agregan a la <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Haga clic en el formulario y elija **ver código**.  
  
9. En el Editor de código, busque la línea de código que carga datos en el adaptador de la tabla. Este código se generó cuando se configura el enlace de datos en el paso 2. El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)`. Hará lo más probable es que tener el formato <xref:System.Windows.Forms.Form.Load> eventos.  
  
10. Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la**carga** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y muévalos a este código de carga de datos.  
  
     El código debe ser ahora similar al siguiente:  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la **guardar** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escribe código para actualizar los datos dentro de la tabla, el control se enlaza a.  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  En algunos casos, el <xref:System.Windows.Forms.BindingNavigator> componente ya tendrá un**guardar** botón, pero ningún código se habrán generado por el Diseñador de Windows Forms. En este caso, puede colocar el código anterior en el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para ese botón, en lugar de crear un botón totalmente nuevo en la <xref:System.Windows.Forms.ToolStrip>. Sin embargo, el botón está deshabilitado de forma predeterminada, por lo que debe establecer el <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad del botón en `true` para que el botón funcione correctamente.  
  
12. Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la**cancelar** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para cancelar los cambios realizados en el registro de datos que se muestra.  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  El <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> método tiene un ámbito para la fila de datos. Guarde los cambios que realice al ver el registro concreto antes de navegar hasta el siguiente registro.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [BindingNavigator (control)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Información general sobre el componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)

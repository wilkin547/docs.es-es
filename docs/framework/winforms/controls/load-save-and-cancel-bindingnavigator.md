---
title: Agregar los botones cargar, guardar y cancelar al control BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 0305df5e7566f9441ce09fa3346a8b2dc67c8943
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627973"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms

El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> de propósito especial que está pensado para navegar por los controles del formulario que están enlazados a datos y manipularlos.

Dado que se trata de un control de <xref:System.Windows.Forms.ToolStrip>, el componente de <xref:System.Windows.Forms.BindingNavigator> se puede modificar fácilmente para incluir comandos adicionales o alternativos para el usuario.

En el procedimiento siguiente, se enlaza un control <xref:System.Windows.Forms.TextBox> a los datos y el control <xref:System.Windows.Forms.ToolStrip> que se agrega al formulario se modifica para incluir los botones cargar, guardar y cancelar.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Agregar los botones cargar, guardar y cancelar al componente BindingNavigator

1. En Visual Studio, agregue un control de <xref:System.Windows.Forms.TextBox> al formulario.

2. Enlácelo a un <xref:System.Windows.Forms.BindingSource>, que está enlazado a un origen de datos. En este ejemplo, el <xref:System.Windows.Forms.BindingSource> se enlaza a una base de datos.

3. Una vez que se hayan generado el adaptador de tabla y el conjunto de informes, arrastre un control <xref:System.Windows.Forms.BindingNavigator> al formulario.

4. Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> del control <xref:System.Windows.Forms.BindingNavigator> en el <xref:System.Windows.Forms.BindingSource> del formulario que está enlazado a los controles.

5. Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.

6. Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) para que aparezca el cuadro de diálogo **tareas de BindingNavigator** y seleccione **Editar elementos**.

     Aparece el editor de la **colección de elementos** .

7. En el **Editor**de la colección de elementos, realice lo siguiente:

    1. Agregue un <xref:System.Windows.Forms.ToolStripSeparator> y tres elementos <xref:System.Windows.Forms.ToolStripButton> seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haciendo clic en el botón **Agregar** .

    2. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Name%2A> de los botones en **LoadButton**, **SaveButton**y **CancelButton**, respectivamente.

    3. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> de los botones para **cargar**, **Guardar**y **Cancelar**.

    4. Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> de cada uno de los botones en **texto**. Como alternativa, puede establecer esta propiedad en **Image** o **ImageAndText**, y establecer la imagen que se va a mostrar en la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A>.

    5. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Los botones se agregan a la <xref:System.Windows.Forms.ToolStrip>.

8. Haga clic con el botón secundario en el formulario y elija **Ver código**.

9. En el editor de código, busque la línea de código que carga los datos en el adaptador de tabla. Este código se generó al configurar el enlace de datos en el paso 2. El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)`. Lo más probable es que esté en el evento <xref:System.Windows.Forms.Form.Load> del formulario.

10. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del <xref:System.Windows.Forms.ToolStripButton> de **carga** que creó anteriormente y mueva el código de carga de datos a él.

     El código debería tener ahora un aspecto similar al siguiente:

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

11. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del<xref:System.Windows.Forms.ToolStripButton> de **almacenamiento** que creó anteriormente y escriba código para actualizar los datos de la tabla a la que está enlazado el control.

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
    > En algunos casos, el componente de <xref:System.Windows.Forms.BindingNavigator> ya tiene un botón **Guardar** , pero el diseñador de Windows Forms no ha generado ningún código. En este caso, puede colocar el código anterior en el controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para ese botón, en lugar de crear un botón completamente nuevo en el <xref:System.Windows.Forms.ToolStrip>. Sin embargo, el botón está deshabilitado de forma predeterminada, por lo que debe establecer la propiedad <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> del botón en `true` para que el botón funcione correctamente.

12. Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del <xref:System.Windows.Forms.ToolStripButton> **Cancelar** que creó anteriormente y escriba código para cancelar los cambios realizados en el registro de datos que se muestra.

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
    > El ámbito del método <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> es la fila de datos. Guarde los cambios que realice mientras ve ese registro individual antes de ir al siguiente registro.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
- [Información general sobre el componente BindingSource](bindingsource-component-overview.md)

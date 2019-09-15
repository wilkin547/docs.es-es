---
title: Procedimiento para agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991734"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Procedimiento para agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms

El <xref:System.Windows.Forms.BindingNavigator> control es un control de propósito <xref:System.Windows.Forms.ToolStrip> especial diseñado para navegar por los controles del formulario que están enlazados a datos y manipularlos.

Dado que es un <xref:System.Windows.Forms.ToolStrip> control, el <xref:System.Windows.Forms.BindingNavigator> componente se puede modificar fácilmente para incluir comandos adicionales o alternativos para el usuario.

En el procedimiento siguiente, se <xref:System.Windows.Forms.TextBox> enlaza un control a los datos y el <xref:System.Windows.Forms.ToolStrip> control que se agrega al formulario se modifica para incluir los botones cargar, guardar y cancelar.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Agregar los botones cargar, guardar y cancelar al componente BindingNavigator

1. En Visual Studio, agregue un <xref:System.Windows.Forms.TextBox> control al formulario.

2. Enlácelo a un <xref:System.Windows.Forms.BindingSource>, que está enlazado a un origen de datos. En este ejemplo, <xref:System.Windows.Forms.BindingSource> se enlaza a una base de datos.

3. Una vez que se hayan generado el adaptador de tabla y <xref:System.Windows.Forms.BindingNavigator> el conjunto de informes, arrastre un control al formulario.

4. Establezca la <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> propiedad<xref:System.Windows.Forms.BindingSource> del control en el en el formulario que está enlazado a los controles.

5. Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.

6. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) para que aparezca el cuadro de diálogo **tareas de BindingNavigator** y seleccione **Editar elementos**.

     Aparece el editor de la **colección de elementos** .

7. En el **Editor**de la colección de elementos, realice lo siguiente:

    1. Agregue un <xref:System.Windows.Forms.ToolStripSeparator> y tres <xref:System.Windows.Forms.ToolStripButton> elementos seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haciendo clic en el botón **Agregar** .

    2. Establezca la <xref:System.Windows.Forms.ToolStripItem.Name%2A> propiedad de los botones en **LoadButton**, **SaveButton**y **CancelButton**, respectivamente.

    3. Establezca la <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad de los botones para **cargar**, **Guardar**y **Cancelar**.

    4. Establezca la <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad de cada uno de los botones en **texto**. Como alternativa, puede establecer esta propiedad en **Image** o **ImageAndText**y establecer la imagen que se va a mostrar en la <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad.

    5. Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Los botones se agregan a <xref:System.Windows.Forms.ToolStrip>.

8. Haga clic con el botón secundario en el formulario y elija **Ver código**.

9. En el editor de código, busque la línea de código que carga los datos en el adaptador de tabla. Este código se generó al configurar el enlace de datos en el paso 2. El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)`. Lo más probable es que esté en el evento <xref:System.Windows.Forms.Form.Load> del formulario.

10. Cree un controlador de eventos para <xref:System.Windows.Forms.ToolStripItem.Click> el evento de la **carga** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y mueva el código de carga de datos a él.

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

11. Cree un controlador de eventos para <xref:System.Windows.Forms.ToolStripItem.Click> el evento del **guardado** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para actualizar los datos de la tabla a la que está enlazado el control.

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
    > En algunos casos, el <xref:System.Windows.Forms.BindingNavigator> componente ya tiene un botón **Guardar** , pero el diseñador de Windows Forms no ha generado ningún código. En este caso, puede colocar el código anterior en el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para ese botón, en lugar de crear un botón completamente nuevo en el. <xref:System.Windows.Forms.ToolStrip> Sin embargo, el botón está deshabilitado de forma predeterminada, por <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> lo que debe establecer la `true` propiedad del botón en para que el botón funcione correctamente.

12. Cree un controlador de eventos para <xref:System.Windows.Forms.ToolStripItem.Click> el evento de **cancelación** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para cancelar cualquier cambio en el registro de datos que se muestra.

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
    > El <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> ámbito del método es la fila de datos. Guarde los cambios que realice mientras ve ese registro individual antes de ir al siguiente registro.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
- [Información general sobre el componente BindingSource](bindingsource-component-overview.md)

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
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="42de2-102">Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42de2-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="42de2-103">El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> de propósito especial que está pensado para navegar por los controles del formulario que están enlazados a datos y manipularlos.</span><span class="sxs-lookup"><span data-stu-id="42de2-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="42de2-104">Dado que se trata de un control de <xref:System.Windows.Forms.ToolStrip>, el componente de <xref:System.Windows.Forms.BindingNavigator> se puede modificar fácilmente para incluir comandos adicionales o alternativos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="42de2-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="42de2-105">En el procedimiento siguiente, se enlaza un control <xref:System.Windows.Forms.TextBox> a los datos y el control <xref:System.Windows.Forms.ToolStrip> que se agrega al formulario se modifica para incluir los botones cargar, guardar y cancelar.</span><span class="sxs-lookup"><span data-stu-id="42de2-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="42de2-106">Agregar los botones cargar, guardar y cancelar al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="42de2-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="42de2-107">En Visual Studio, agregue un control de <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="42de2-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="42de2-108">Enlácelo a un <xref:System.Windows.Forms.BindingSource>, que está enlazado a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42de2-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="42de2-109">En este ejemplo, el <xref:System.Windows.Forms.BindingSource> se enlaza a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="42de2-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="42de2-110">Una vez que se hayan generado el adaptador de tabla y el conjunto de informes, arrastre un control <xref:System.Windows.Forms.BindingNavigator> al formulario.</span><span class="sxs-lookup"><span data-stu-id="42de2-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="42de2-111">Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> del control <xref:System.Windows.Forms.BindingNavigator> en el <xref:System.Windows.Forms.BindingSource> del formulario que está enlazado a los controles.</span><span class="sxs-lookup"><span data-stu-id="42de2-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="42de2-112">Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="42de2-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="42de2-113">Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) para que aparezca el cuadro de diálogo **tareas de BindingNavigator** y seleccione **Editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="42de2-113">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="42de2-114">Aparece el editor de la **colección de elementos** .</span><span class="sxs-lookup"><span data-stu-id="42de2-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="42de2-115">En el **Editor**de la colección de elementos, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42de2-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="42de2-116">Agregue un <xref:System.Windows.Forms.ToolStripSeparator> y tres elementos <xref:System.Windows.Forms.ToolStripButton> seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haciendo clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="42de2-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="42de2-117">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Name%2A> de los botones en **LoadButton**, **SaveButton**y **CancelButton**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="42de2-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="42de2-118">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Text%2A> de los botones para **cargar**, **Guardar**y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="42de2-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="42de2-119">Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> de cada uno de los botones en **texto**.</span><span class="sxs-lookup"><span data-stu-id="42de2-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="42de2-120">Como alternativa, puede establecer esta propiedad en **Image** o **ImageAndText**, y establecer la imagen que se va a mostrar en la propiedad <xref:System.Windows.Forms.ToolStripItem.Image%2A>.</span><span class="sxs-lookup"><span data-stu-id="42de2-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="42de2-121">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="42de2-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="42de2-122">Los botones se agregan a la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="42de2-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="42de2-123">Haga clic con el botón secundario en el formulario y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="42de2-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="42de2-124">En el editor de código, busque la línea de código que carga los datos en el adaptador de tabla.</span><span class="sxs-lookup"><span data-stu-id="42de2-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="42de2-125">Este código se generó al configurar el enlace de datos en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="42de2-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="42de2-126">El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="42de2-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="42de2-127">Lo más probable es que esté en el evento <xref:System.Windows.Forms.Form.Load> del formulario.</span><span class="sxs-lookup"><span data-stu-id="42de2-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="42de2-128">Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del <xref:System.Windows.Forms.ToolStripButton> de **carga** que creó anteriormente y mueva el código de carga de datos a él.</span><span class="sxs-lookup"><span data-stu-id="42de2-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="42de2-129">El código debería tener ahora un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="42de2-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="42de2-130">Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del<xref:System.Windows.Forms.ToolStripButton> de **almacenamiento** que creó anteriormente y escriba código para actualizar los datos de la tabla a la que está enlazado el control.</span><span class="sxs-lookup"><span data-stu-id="42de2-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="42de2-131">En algunos casos, el componente de <xref:System.Windows.Forms.BindingNavigator> ya tiene un botón **Guardar** , pero el diseñador de Windows Forms no ha generado ningún código.</span><span class="sxs-lookup"><span data-stu-id="42de2-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="42de2-132">En este caso, puede colocar el código anterior en el controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> para ese botón, en lugar de crear un botón completamente nuevo en el <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="42de2-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="42de2-133">Sin embargo, el botón está deshabilitado de forma predeterminada, por lo que debe establecer la propiedad <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> del botón en `true` para que el botón funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="42de2-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="42de2-134">Cree un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click> del <xref:System.Windows.Forms.ToolStripButton> **Cancelar** que creó anteriormente y escriba código para cancelar los cambios realizados en el registro de datos que se muestra.</span><span class="sxs-lookup"><span data-stu-id="42de2-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="42de2-135">El ámbito del método <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> es la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="42de2-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="42de2-136">Guarde los cambios que realice mientras ve ese registro individual antes de ir al siguiente registro.</span><span class="sxs-lookup"><span data-stu-id="42de2-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="42de2-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42de2-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="42de2-138">BindingNavigator (control)</span><span class="sxs-lookup"><span data-stu-id="42de2-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="42de2-139">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="42de2-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)

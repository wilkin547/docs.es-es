---
title: Agregar los botones cargar, guardar y cancelar al control BindingNavigator
description: Obtenga información sobre cómo agregar los botones cargar, guardar y cancelar al control Windows Forms BindingNavigator.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: d4db91b8cfaf2df253d0c4cf5d8a66e9157d4986
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173424"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="b233a-103">Procedimiento para agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b233a-103">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="b233a-104">El <xref:System.Windows.Forms.BindingNavigator> control es un control de propósito especial <xref:System.Windows.Forms.ToolStrip> diseñado para navegar por los controles del formulario que están enlazados a datos y manipularlos.</span><span class="sxs-lookup"><span data-stu-id="b233a-104">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="b233a-105">Dado que es un <xref:System.Windows.Forms.ToolStrip> control, el <xref:System.Windows.Forms.BindingNavigator> componente se puede modificar fácilmente para incluir comandos adicionales o alternativos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b233a-105">Because it's a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="b233a-106">En el procedimiento siguiente, <xref:System.Windows.Forms.TextBox> se enlaza un control a los datos y el <xref:System.Windows.Forms.ToolStrip> control que se agrega al formulario se modifica para incluir los botones cargar, guardar y cancelar.</span><span class="sxs-lookup"><span data-stu-id="b233a-106">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="b233a-107">Agregar los botones cargar, guardar y cancelar al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="b233a-107">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="b233a-108">En Visual Studio, agregue un <xref:System.Windows.Forms.TextBox> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="b233a-108">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="b233a-109">Enlácelo a un <xref:System.Windows.Forms.BindingSource> , que está enlazado a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b233a-109">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="b233a-110">En este ejemplo, <xref:System.Windows.Forms.BindingSource> se enlaza a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="b233a-110">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="b233a-111">Una vez que se hayan generado el adaptador de tabla y el conjunto de informes, arrastre un <xref:System.Windows.Forms.BindingNavigator> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="b233a-111">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="b233a-112">Establezca la <xref:System.Windows.Forms.BindingNavigator> propiedad del control en el <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> <xref:System.Windows.Forms.BindingSource> en el formulario que está enlazado a los controles.</span><span class="sxs-lookup"><span data-stu-id="b233a-112">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="b233a-113">Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="b233a-113">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="b233a-114">Haga clic en el glifo de acciones del diseñador ( ![ flecha negra pequeña ](./media/designer-actions-glyph.gif) ) para que aparezca el cuadro de diálogo **tareas de BindingNavigator** y seleccione **Editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="b233a-114">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="b233a-115">Aparece el editor de la **colección de elementos** .</span><span class="sxs-lookup"><span data-stu-id="b233a-115">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="b233a-116">En el **Editor**de la colección de elementos, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b233a-116">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="b233a-117">Agregue un <xref:System.Windows.Forms.ToolStripSeparator> y tres <xref:System.Windows.Forms.ToolStripButton> elementos seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haciendo clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="b233a-117">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="b233a-118">Establezca la <xref:System.Windows.Forms.ToolStripItem.Name%2A> propiedad de los botones en **LoadButton**, **SaveButton**y **CancelButton**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b233a-118">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="b233a-119">Establezca la <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad de los botones para **cargar**, **Guardar**y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b233a-119">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="b233a-120">Establezca la <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad de cada uno de los botones en **texto**.</span><span class="sxs-lookup"><span data-stu-id="b233a-120">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="b233a-121">Como alternativa, puede establecer esta propiedad en **Image** o **ImageAndText**y establecer la imagen que se va a mostrar en la <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b233a-121">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="b233a-122">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b233a-122">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="b233a-123">Los botones se agregan a <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="b233a-123">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="b233a-124">Haga clic con el botón secundario en el formulario y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="b233a-124">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="b233a-125">En el editor de código, busque la línea de código que carga los datos en el adaptador de tabla.</span><span class="sxs-lookup"><span data-stu-id="b233a-125">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="b233a-126">Este código se generó al configurar el enlace de datos en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b233a-126">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="b233a-127">El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)` .</span><span class="sxs-lookup"><span data-stu-id="b233a-127">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="b233a-128">Lo más probable es que esté en el evento del formulario <xref:System.Windows.Forms.Form.Load> .</span><span class="sxs-lookup"><span data-stu-id="b233a-128">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="b233a-129">Cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> evento de la **carga** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y mueva el código de carga de datos a él.</span><span class="sxs-lookup"><span data-stu-id="b233a-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="b233a-130">El código debería tener ahora un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b233a-130">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="b233a-131">Cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> evento del **guardado** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para actualizar los datos de la tabla a la que está enlazado el control.</span><span class="sxs-lookup"><span data-stu-id="b233a-131">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="b233a-132">En algunos casos, el <xref:System.Windows.Forms.BindingNavigator> componente ya tiene un botón **Guardar** , pero el diseñador de Windows Forms no ha generado ningún código.</span><span class="sxs-lookup"><span data-stu-id="b233a-132">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="b233a-133">En este caso, puede colocar el código anterior en el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para ese botón, en lugar de crear un botón completamente nuevo en el <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="b233a-133">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b233a-134">Sin embargo, el botón está deshabilitado de forma predeterminada, por lo que debe establecer la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad del botón en `true` para que el botón funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="b233a-134">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="b233a-135">Cree un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> evento de **cancelación** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para cancelar cualquier cambio en el registro de datos que se muestra.</span><span class="sxs-lookup"><span data-stu-id="b233a-135">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="b233a-136">El <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> ámbito del método es la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="b233a-136">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="b233a-137">Guarde los cambios que realice mientras ve ese registro individual antes de ir al siguiente registro.</span><span class="sxs-lookup"><span data-stu-id="b233a-137">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="b233a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b233a-138">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="b233a-139">Control BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="b233a-139">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="b233a-140">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="b233a-140">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)

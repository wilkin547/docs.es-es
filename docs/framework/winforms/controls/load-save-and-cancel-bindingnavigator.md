---
title: 'Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 8f331c67dd22a6a9e2382ecc11d23c67cd2a5cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540496"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="314d6-102">Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="314d6-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="314d6-103">El <xref:System.Windows.Forms.BindingNavigator> control es un propósito especial <xref:System.Windows.Forms.ToolStrip> control que está pensado para navegar y manipular los controles en el formulario que están enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="314d6-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="314d6-104">Porque es un <xref:System.Windows.Forms.ToolStrip> (control), el <xref:System.Windows.Forms.BindingNavigator> componente puede modificarse fácilmente para incluir comandos adicionales o alternativos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="314d6-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="314d6-105">En el siguiente procedimiento, un <xref:System.Windows.Forms.TextBox> control se enlaza a datos y el <xref:System.Windows.Forms.ToolStrip> control que se agrega al formulario se modifica para incluir cargar, guardar y cancelar botones.</span><span class="sxs-lookup"><span data-stu-id="314d6-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="314d6-106">Para agregar una carga, guardar, botones y Cancelar al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="314d6-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="314d6-107">Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.</span><span class="sxs-lookup"><span data-stu-id="314d6-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="314d6-108">Enlazar a un <xref:System.Windows.Forms.BindingSource>, que está enlazado a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="314d6-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="314d6-109">En este ejemplo, el <xref:System.Windows.Forms.BindingSource> está enlazado a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="314d6-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="314d6-110">Después de generar el adaptador de conjunto de datos y tabla, arrastre un <xref:System.Windows.Forms.BindingNavigator> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="314d6-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="314d6-111">Establecer el <xref:System.Windows.Forms.BindingNavigator> del control <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> propiedad a la <xref:System.Windows.Forms.BindingSource> en el formulario que se enlaza a los controles.</span><span class="sxs-lookup"><span data-stu-id="314d6-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="314d6-112">Seleccione el control <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="314d6-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="314d6-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) por lo que la **tareas BindingNavigator** cuadro de diálogo aparece y seleccione **editar elementos**.</span><span class="sxs-lookup"><span data-stu-id="314d6-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="314d6-114">El **Editor de la colección de elementos** aparece.</span><span class="sxs-lookup"><span data-stu-id="314d6-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="314d6-115">En el **Editor de la colección de elementos**, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="314d6-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="314d6-116">Agregar un <xref:System.Windows.Forms.ToolStripSeparator> y tres <xref:System.Windows.Forms.ToolStripButton> elementos seleccionando el tipo adecuado de <xref:System.Windows.Forms.ToolStripItem> y haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="314d6-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="314d6-117">Establecer el <xref:System.Windows.Forms.ToolStripItem.Name%2A> propiedad de los botones para**LoadButton**,**SaveButton**, y**CancelButton**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="314d6-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to**LoadButton**,**SaveButton**, and**CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="314d6-118">Establecer el <xref:System.Windows.Forms.ToolStripItem.Text%2A> propiedad de los botones para**carga** `,` **guardar**, y**cancelar**.</span><span class="sxs-lookup"><span data-stu-id="314d6-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to**Load**`,` **Save**, and**Cancel**.</span></span>  
  
    4.  <span data-ttu-id="314d6-119">Establecer el <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> propiedad para cada uno de los botones para**texto**.</span><span class="sxs-lookup"><span data-stu-id="314d6-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to**Text**.</span></span> <span data-ttu-id="314d6-120">Como alternativa, puede establecer esta propiedad en**imagen**o**ImageAndText**y establecer la imagen que se mostrará en el <xref:System.Windows.Forms.ToolStripItem.Image%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="314d6-120">Alternatively, you can set this property to**Image**or**ImageAndText**and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="314d6-121">Haga clic en **Aceptar** para cerrar el cuadro de diálogo. Los botones se agregan a la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="314d6-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="314d6-122">Haga clic en el formulario y elija **ver código**.</span><span class="sxs-lookup"><span data-stu-id="314d6-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="314d6-123">En el Editor de código, busque la línea de código que carga datos en el adaptador de la tabla.</span><span class="sxs-lookup"><span data-stu-id="314d6-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="314d6-124">Este código se generó cuando se configura el enlace de datos en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="314d6-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="314d6-125">El código debe ser similar al siguiente: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="314d6-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="314d6-126">Hará lo más probable es que tener el formato <xref:System.Windows.Forms.Form.Load> eventos.</span><span class="sxs-lookup"><span data-stu-id="314d6-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="314d6-127">Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la**carga** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y muévalos a este código de carga de datos.</span><span class="sxs-lookup"><span data-stu-id="314d6-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Load**<xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="314d6-128">El código debe ser ahora similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="314d6-128">Your code should now look similar to the following:</span></span>  
  
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
  
11. <span data-ttu-id="314d6-129">Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la **guardar** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escribe código para actualizar los datos dentro de la tabla, el control se enlaza a.</span><span class="sxs-lookup"><span data-stu-id="314d6-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
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
    >  <span data-ttu-id="314d6-130">En algunos casos, el <xref:System.Windows.Forms.BindingNavigator> componente ya tendrá un**guardar** botón, pero ningún código se habrán generado por el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="314d6-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a**Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="314d6-131">En este caso, puede colocar el código anterior en el <xref:System.Windows.Forms.ToolStripItem.Click> controlador de eventos para ese botón, en lugar de crear un botón totalmente nuevo en la <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="314d6-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="314d6-132">Sin embargo, el botón está deshabilitado de forma predeterminada, por lo que debe establecer el <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad del botón en `true` para que el botón funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="314d6-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>  
  
12. <span data-ttu-id="314d6-133">Crear un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos de la**cancelar** <xref:System.Windows.Forms.ToolStripButton> que creó anteriormente y escriba código para cancelar los cambios realizados en el registro de datos que se muestra.</span><span class="sxs-lookup"><span data-stu-id="314d6-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the**Cancel**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
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
    >  <span data-ttu-id="314d6-134">El <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> método tiene un ámbito para la fila de datos.</span><span class="sxs-lookup"><span data-stu-id="314d6-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="314d6-135">Guarde los cambios que realice al ver el registro concreto antes de navegar hasta el siguiente registro.</span><span class="sxs-lookup"><span data-stu-id="314d6-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314d6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="314d6-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="314d6-137">BindingNavigator (control)</span><span class="sxs-lookup"><span data-stu-id="314d6-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="314d6-138">Información general sobre el componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="314d6-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)

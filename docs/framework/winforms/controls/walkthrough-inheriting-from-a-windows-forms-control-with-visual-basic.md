---
title: 'Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0625695933b776b8cdbe5488adc116723b930dd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="b03c0-102">Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b03c0-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="b03c0-103">Con [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], puede crear controles personalizados eficaces mediante *herencia*.</span><span class="sxs-lookup"><span data-stu-id="b03c0-103">With [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="b03c0-104">A través de la herencia puede crear controles que conserven toda la funcionalidad inherente de controles de Windows Forms estándar y además incorporen funcionalidad personalizada.</span><span class="sxs-lookup"><span data-stu-id="b03c0-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="b03c0-105">En este tutorial, creará un control heredado simple denominado `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="b03c0-106">Este botón heredará la funcionalidad de los formularios de Windows estándar <xref:System.Windows.Forms.Button> controlar y expondrá una propiedad personalizada denominada `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b03c0-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="b03c0-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b03c0-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="b03c0-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b03c0-109">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b03c0-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="b03c0-110">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="b03c0-110">Creating the Project</span></span>  
 <span data-ttu-id="b03c0-111">Cuando cree un proyecto, especifique su nombre para establecer el espacio de nombres raíz, el nombre de ensamblado y el nombre del proyecto, y para asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="b03c0-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="b03c0-112">Para crear la biblioteca de controles ValueButtonLib y el control ValueButton</span><span class="sxs-lookup"><span data-stu-id="b03c0-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="b03c0-113">En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="b03c0-114">Seleccione la plantilla de proyecto **Biblioteca de controles de Windows Forms** en la lista de proyectos de [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] y escriba `ValueButtonLib` en el cuadro **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-114">Select the **Windows Forms Control Library** project template from the list of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="b03c0-115">El nombre del proyecto, `ValueButtonLib`, también se asigna de forma predeterminada al espacio de nombres raíz.</span><span class="sxs-lookup"><span data-stu-id="b03c0-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="b03c0-116">El espacio de nombres raíz se utiliza para calificar los nombres de los componentes del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b03c0-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="b03c0-117">Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar su componente `ValueButton` mediante `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="b03c0-118">Para más información, consulte [Espacios de nombres en Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b03c0-118">For more information, see [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
3.  <span data-ttu-id="b03c0-119">En el **Explorador de soluciones**, haga clic con el botón derecho en **UserControl1.vb** y elija **Cambiar nombre** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-119">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="b03c0-120">Cambie el nombre del archivo a `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-120">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="b03c0-121">Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código "UserControl1".</span><span class="sxs-lookup"><span data-stu-id="b03c0-121">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>  
  
4.  <span data-ttu-id="b03c0-122">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-122">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="b03c0-123">Abra el nodo **ValueButton.vb** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-123">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="b03c0-124">Abra este archivo en el **Editor de código**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-124">Open this file in the **Code Editor**.</span></span>  
  
6.  <span data-ttu-id="b03c0-125">Busque la `Class` instrucción, `Partial Public Class ValueButton`y cambie el tipo del que este control hereda de <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="b03c0-125">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="b03c0-126">Esto permite al control heredado heredar toda la funcionalidad de la <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="b03c0-126">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
7.  <span data-ttu-id="b03c0-127">Busque la `InitializeComponent` método y quite la línea que asigna la <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b03c0-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="b03c0-128">Esta propiedad no existe en el <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="b03c0-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="b03c0-129">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b03c0-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
     <span data-ttu-id="b03c0-130">Tenga en cuenta que ya no hay disponible ningún diseñador visual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-130">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="b03c0-131">Dado que el <xref:System.Windows.Forms.Button> control realiza su propia representación, no puede modificar su apariencia en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b03c0-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="b03c0-132">Su representación visual será exactamente igual que la de la clase que hereda (es decir, <xref:System.Windows.Forms.Button>) a menos que modifique en el código.</span><span class="sxs-lookup"><span data-stu-id="b03c0-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b03c0-133">Todavía puede agregar componentes, que no tienen ningún elemento de interfaz de usuario, a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b03c0-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="b03c0-134">Agregar una propiedad al control heredado</span><span class="sxs-lookup"><span data-stu-id="b03c0-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="b03c0-135">Un uso posible de los controles de Windows Forms heredados es la creación de controles que sean idénticos en apariencia y comportamiento a los controles de Windows Forms estándar, pero que expongan propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b03c0-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="b03c0-136">En esta sección, agregará una propiedad denominada `ButtonValue` al control.</span><span class="sxs-lookup"><span data-stu-id="b03c0-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="b03c0-137">Para agregar la propiedad Value</span><span class="sxs-lookup"><span data-stu-id="b03c0-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="b03c0-138">En el **Explorador de soluciones**, haga clic con el botón derecho en **ValueButton.vb** y haga clic en **Ver código** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-138">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b03c0-139">Busque la instrucción `Public Class ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-139">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="b03c0-140">Justo debajo de esta declaración, escriba el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="b03c0-140">Immediately beneath this statement, type the following code:</span></span>  
  
    ```vb  
    ' Creates the private variable that will store the value of your   
    ' property.  
    Private varValue as integer  
    ' Declares the property.  
    Property ButtonValue() as Integer  
    ' Sets the method for retrieving the value of your property.  
       Get  
          Return varValue  
       End Get  
    ' Sets the method for setting the value of your property.  
       Set(ByVal Value as Integer)  
          varValue = Value  
       End Set  
    End Property  
    ```  
  
     <span data-ttu-id="b03c0-141">Este código establece los métodos por los que se almacena y se recupera la propiedad `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="b03c0-142">La instrucción `Get` establece el valor devuelto en el valor que se almacena en la variable privada `varValue`, y la instrucción `Set` establece el valor de la variable privada mediante la palabra clave `Value`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-142">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>  
  
3.  <span data-ttu-id="b03c0-143">En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b03c0-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="b03c0-144">Probar el control</span><span class="sxs-lookup"><span data-stu-id="b03c0-144">Testing Your Control</span></span>  
 <span data-ttu-id="b03c0-145">Los controles no son proyectos independientes; deben hospedarse en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="b03c0-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="b03c0-146">Para probar el control, debe proporcionar un proyecto de prueba donde pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="b03c0-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="b03c0-147">También debe hacer que el control resulte accesible al proyecto de prueba al compilarlo.</span><span class="sxs-lookup"><span data-stu-id="b03c0-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="b03c0-148">En esta sección, compilará el control y lo probará en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b03c0-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="b03c0-149">Para compilar el control</span><span class="sxs-lookup"><span data-stu-id="b03c0-149">To build your control</span></span>  
  
1.  <span data-ttu-id="b03c0-150">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="b03c0-151">La compilación debería completarse correctamente sin advertencias ni errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="b03c0-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="b03c0-152">Para crear un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="b03c0-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="b03c0-153">En el menú **Archivo**, elija **Agregar** y haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="b03c0-154">Seleccione el nodo de proyectos de [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] y haga clic en **Aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-154">Select the [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projects node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="b03c0-155">En el cuadro **Nombre**, escriba `Test`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="b03c0-156">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-156">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="b03c0-157">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Referencias** para su proyecto de prueba y seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-157">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="b03c0-158">Haga clic en la pestaña **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-158">Click the **Projects** tab.</span></span>  
  
7.  <span data-ttu-id="b03c0-159">Haga clic en la pestaña etiquetada como **Proyectos**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-159">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="b03c0-160">El proyecto `ValueButtonLib` aparecerá bajo **Nombre de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-160">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="b03c0-161">Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="b03c0-161">Double-click the project to add the reference to the test project.</span></span>  
  
8.  <span data-ttu-id="b03c0-162">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y seleccione **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-162">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="b03c0-163">Para agregar el control al formulario</span><span class="sxs-lookup"><span data-stu-id="b03c0-163">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="b03c0-164">En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1.vb** y elija **Ver diseñador** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-164">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="b03c0-165">En el **cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-165">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="b03c0-166">Haga doble clic en **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-166">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="b03c0-167">Aparece un componente **ValueButton** en el formulario.</span><span class="sxs-lookup"><span data-stu-id="b03c0-167">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="b03c0-168">Haga clic con el botón derecho en **ValueButton** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-168">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="b03c0-169">En la ventana **Propiedades**, examine las propiedades de este control.</span><span class="sxs-lookup"><span data-stu-id="b03c0-169">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="b03c0-170">Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-170">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="b03c0-171">Establezca la propiedad `ButtonValue` en `5`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-171">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="b03c0-172">En el **todos los formularios Windows Forms** pestaña de la **cuadro de herramientas**, haga doble clic en **etiqueta** para agregar un <xref:System.Windows.Forms.Label> al formulario.</span><span class="sxs-lookup"><span data-stu-id="b03c0-172">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="b03c0-173">Mueva la etiqueta al centro del formulario.</span><span class="sxs-lookup"><span data-stu-id="b03c0-173">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="b03c0-174">Haga doble clic en `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-174">Double-click `ValueButton1`.</span></span>  
  
     <span data-ttu-id="b03c0-175">Se abre el **Editor de código** en el evento `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-175">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="b03c0-176">Escriba la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="b03c0-176">Type the following line of code.</span></span>  
  
    ```vb  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. <span data-ttu-id="b03c0-177">En el **Explorador de soluciones**, haga clic con el botón derecho en **Probar** y elija **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b03c0-177">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="b03c0-178">En el menú **Depurar**, seleccione **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="b03c0-178">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="b03c0-179">Aparece `Form1`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-179">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="b03c0-180">Haga clic en `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-180">Click `Valuebutton1`.</span></span>  
  
     <span data-ttu-id="b03c0-181">Se muestra el número "5" en `Label1`, lo que demuestra que la propiedad `ButtonValue` del control heredado se ha pasado a `Label1` a través del método `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="b03c0-181">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="b03c0-182">Por lo tanto, su control `ValueButton` hereda toda la funcionalidad del botón estándar de Windows Forms, pero expone una propiedad personalizada adicional.</span><span class="sxs-lookup"><span data-stu-id="b03c0-182">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b03c0-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="b03c0-183">See Also</span></span>  
 [<span data-ttu-id="b03c0-184">Tutorial: Crear un control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b03c0-184">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="b03c0-185">Cómo: Mostrar un control en el cuadro de diálogo Seleccionar elementos del cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="b03c0-185">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="b03c0-186">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b03c0-186">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="b03c0-187">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b03c0-187">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="b03c0-188">Tutoriales sobre la creación de componentes</span><span class="sxs-lookup"><span data-stu-id="b03c0-188">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)

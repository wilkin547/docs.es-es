---
title: Hospedar un control compuesto de Windows Forms en WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 16c09b4bb393fa830412385b4b405dd1fae9878b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744997"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="d6211-102">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="d6211-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d6211-103">proporciona un entorno rico para crear aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d6211-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="d6211-104">Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más eficaz reutilizar al menos parte de ese código en su aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirlo desde el principio.</span><span class="sxs-lookup"><span data-stu-id="d6211-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="d6211-105">El escenario más común es cuando tiene controles de Windows Forms existentes.</span><span class="sxs-lookup"><span data-stu-id="d6211-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="d6211-106">En algunos casos, incluso podría no tener acceso al código fuente de estos controles.</span><span class="sxs-lookup"><span data-stu-id="d6211-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="d6211-107">proporciona un procedimiento sencillo para hospedar estos controles en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6211-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d6211-108">Por ejemplo, puede usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la mayor parte de la programación mientras hospeda los controles de <xref:System.Windows.Forms.DataGridView> especializados.</span><span class="sxs-lookup"><span data-stu-id="d6211-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="d6211-109">Este tutorial le guía a través de una aplicación que hospeda un Windows Forms control compuesto para realizar la entrada de datos en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6211-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d6211-110">El control compuesto se empaqueta en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="d6211-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="d6211-111">Este procedimiento general se puede extender a aplicaciones y controles más complejos.</span><span class="sxs-lookup"><span data-stu-id="d6211-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="d6211-112">Este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d6211-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="d6211-113">La principal diferencia es que se invierte el escenario de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="d6211-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="d6211-114">Este tutorial está dividido en dos secciones.</span><span class="sxs-lookup"><span data-stu-id="d6211-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="d6211-115">En la primera sección se describe brevemente la implementación de Windows Forms control compuesto.</span><span class="sxs-lookup"><span data-stu-id="d6211-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="d6211-116">En la segunda sección se explica en detalle cómo hospedar el control compuesto en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], recibir eventos del control y tener acceso a algunas de las propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="d6211-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="d6211-117">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="d6211-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="d6211-118">Implementar el control compuesto de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d6211-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="d6211-119">Implementar la aplicación host de WPF.</span><span class="sxs-lookup"><span data-stu-id="d6211-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="d6211-120">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [hospedar un Windows Forms control compuesto en el ejemplo de WPF](https://go.microsoft.com/fwlink/?LinkID=159999).</span><span class="sxs-lookup"><span data-stu-id="d6211-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6211-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d6211-121">Prerequisites</span></span>  

<span data-ttu-id="d6211-122">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d6211-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="d6211-123">Implementar el control compuesto de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6211-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="d6211-124">El Windows Forms control compuesto utilizado en este ejemplo es un formulario de entrada de datos simple.</span><span class="sxs-lookup"><span data-stu-id="d6211-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="d6211-125">Este formulario toma el nombre y la dirección del usuario y, después, usa un evento personalizado para devolver esa información al host.</span><span class="sxs-lookup"><span data-stu-id="d6211-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="d6211-126">En la ilustración siguiente se muestra la representación del control.</span><span class="sxs-lookup"><span data-stu-id="d6211-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="d6211-127">La siguiente imagen muestra un Windows Forms control compuesto:</span><span class="sxs-lookup"><span data-stu-id="d6211-127">The following image shows a Windows Forms composite control:</span></span>  

 ![Captura de pantalla que muestra un control de Windows Forms simple.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="d6211-129">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d6211-129">Creating the Project</span></span>  
 <span data-ttu-id="d6211-130">Para iniciar el proyecto:</span><span class="sxs-lookup"><span data-stu-id="d6211-130">To start the project:</span></span>  
  
1. <span data-ttu-id="d6211-131">Inicie Visual Studio y abra el cuadro de diálogo **nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="d6211-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="d6211-132">En la categoría de ventana, seleccione la plantilla **biblioteca de controles de Windows Forms** .</span><span class="sxs-lookup"><span data-stu-id="d6211-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="d6211-133">Asigne al nuevo proyecto el nombre de `MyControls`.</span><span class="sxs-lookup"><span data-stu-id="d6211-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="d6211-134">Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, como `WpfHostingWindowsFormsControl`.</span><span class="sxs-lookup"><span data-stu-id="d6211-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="d6211-135">Más tarde, colocará la aplicación host en esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="d6211-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="d6211-136">Haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6211-136">Click **OK** to create the project.</span></span> <span data-ttu-id="d6211-137">El proyecto predeterminado contiene un solo control denominado `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="d6211-138">En Explorador de soluciones, cambie el nombre de `UserControl1` a `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="d6211-139">El proyecto debe tener referencias a los siguientes archivos DLL del sistema.</span><span class="sxs-lookup"><span data-stu-id="d6211-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="d6211-140">Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6211-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="d6211-141">System</span><span class="sxs-lookup"><span data-stu-id="d6211-141">System</span></span>  
  
- <span data-ttu-id="d6211-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="d6211-142">System.Data</span></span>  
  
- <span data-ttu-id="d6211-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="d6211-143">System.Drawing</span></span>  
  
- <span data-ttu-id="d6211-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="d6211-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="d6211-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="d6211-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="d6211-146">Agregar controles al formulario</span><span class="sxs-lookup"><span data-stu-id="d6211-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="d6211-147">Para agregar controles al formulario:</span><span class="sxs-lookup"><span data-stu-id="d6211-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="d6211-148">Abra `MyControl1` en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="d6211-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="d6211-149">En el formulario, agregue cinco controles <xref:System.Windows.Forms.Label> y sus controles de <xref:System.Windows.Forms.TextBox> correspondientes, con el tamaño y el orden en que se encuentran en la ilustración anterior.</span><span class="sxs-lookup"><span data-stu-id="d6211-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="d6211-150">En el ejemplo, los controles de <xref:System.Windows.Forms.TextBox> se denominan:</span><span class="sxs-lookup"><span data-stu-id="d6211-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="d6211-151">Agregue dos <xref:System.Windows.Forms.Button> controles con la etiqueta **Aceptar** y **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="d6211-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="d6211-152">En el ejemplo, los nombres de los botones son `btnOK` y `btnCancel`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d6211-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="d6211-153">Implementar el código auxiliar</span><span class="sxs-lookup"><span data-stu-id="d6211-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="d6211-154">Abra el formulario en la vista Código.</span><span class="sxs-lookup"><span data-stu-id="d6211-154">Open the form in code view.</span></span> <span data-ttu-id="d6211-155">El control devuelve los datos recopilados a su host mediante la generación del evento de `OnButtonClick` personalizado.</span><span class="sxs-lookup"><span data-stu-id="d6211-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="d6211-156">Los datos están contenidos en el objeto de argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="d6211-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="d6211-157">En el código siguiente se muestra la declaración de evento y delegado.</span><span class="sxs-lookup"><span data-stu-id="d6211-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="d6211-158">Agregue el código siguiente a la clase `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="d6211-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="d6211-159">La clase `MyControlEventArgs` contiene la información que se va a devolver al host.</span><span class="sxs-lookup"><span data-stu-id="d6211-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="d6211-160">Agregue la clase siguiente al formulario.</span><span class="sxs-lookup"><span data-stu-id="d6211-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="d6211-161">Cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** , los controladores de eventos <xref:System.Windows.Forms.Control.Click> crean un objeto `MyControlEventArgs` que contiene los datos y genera el evento `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="d6211-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="d6211-162">La única diferencia entre los dos controladores es la propiedad `IsOK` del argumento de evento.</span><span class="sxs-lookup"><span data-stu-id="d6211-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="d6211-163">Esta propiedad permite que el host determine en qué botón se ha hecho clic.</span><span class="sxs-lookup"><span data-stu-id="d6211-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="d6211-164">Se establece en `true` para el botón **Aceptar** y `false` para el botón **Cancelar** .</span><span class="sxs-lookup"><span data-stu-id="d6211-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="d6211-165">En el código siguiente se muestran los dos controladores de botón.</span><span class="sxs-lookup"><span data-stu-id="d6211-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="d6211-166">Agregue el código siguiente a la clase `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="d6211-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="d6211-167">Dar un nombre seguro al ensamblado y compilar el ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6211-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="d6211-168">Para que una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] haga referencia a este ensamblado, debe tener un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d6211-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="d6211-169">Para crear un nombre seguro, cree un archivo de clave con SN. exe y agréguelo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6211-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="d6211-170">Abra un símbolo del sistema de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="d6211-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="d6211-171">Para ello, haga clic en el menú **Inicio** y, a continuación, seleccione **todos los programas/Microsoft Visual Studio 2010/Visual Studio Tools/símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="d6211-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="d6211-172">Esto inicia una ventana de consola con variables de entorno personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d6211-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="d6211-173">En el símbolo del sistema, use el comando `cd` para ir a la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6211-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="d6211-174">Ejecute el comando siguiente para generar un archivo de clave denominado MyControls.snk.</span><span class="sxs-lookup"><span data-stu-id="d6211-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="d6211-175">Para incluir el archivo de clave en el proyecto, haga clic con el botón secundario en el nombre del proyecto en Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d6211-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="d6211-176">En el diseñador de proyectos, haga clic en la pestaña **firma** , active la casilla **firmar el ensamblado** y, a continuación, busque el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="d6211-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="d6211-177">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="d6211-177">Build the solution.</span></span> <span data-ttu-id="d6211-178">La compilación generará un archivo DLL denominado MyControls.dll.</span><span class="sxs-lookup"><span data-stu-id="d6211-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="d6211-179">Implementar la aplicación host de WPF</span><span class="sxs-lookup"><span data-stu-id="d6211-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="d6211-180">La aplicación host de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> para hospedar `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="d6211-181">La aplicación controla el evento `OnButtonClick` para recibir los datos del control.</span><span class="sxs-lookup"><span data-stu-id="d6211-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="d6211-182">También tiene una colección de botones de opción que le permiten cambiar algunas de las propiedades del control de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6211-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d6211-183">En la ilustración siguiente se muestra la aplicación finalizada.</span><span class="sxs-lookup"><span data-stu-id="d6211-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="d6211-184">En la imagen siguiente se muestra la aplicación completa, incluido el control insertado en la aplicación WPF:</span><span class="sxs-lookup"><span data-stu-id="d6211-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![Captura de pantalla que muestra un control incrustado en una página de WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="d6211-186">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="d6211-186">Creating the Project</span></span>
 <span data-ttu-id="d6211-187">Para iniciar el proyecto:</span><span class="sxs-lookup"><span data-stu-id="d6211-187">To start the project:</span></span>

1. <span data-ttu-id="d6211-188">Abra Visual Studio y seleccione **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d6211-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="d6211-189">En la categoría de ventana, seleccione la plantilla **aplicación WPF** .</span><span class="sxs-lookup"><span data-stu-id="d6211-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="d6211-190">Asigne al nuevo proyecto el nombre de `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="d6211-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="d6211-191">Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.</span><span class="sxs-lookup"><span data-stu-id="d6211-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="d6211-192">Haga clic en **Aceptar** para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6211-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="d6211-193">También debe agregar referencias al archivo DLL que contiene `MyControl1` y otros ensamblados.</span><span class="sxs-lookup"><span data-stu-id="d6211-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="d6211-194">Haga clic con el botón derecho en el nombre del proyecto en Explorador de soluciones y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d6211-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="d6211-195">Haga clic en la pestaña **examinar** y busque la carpeta que contiene DataControl. dll.</span><span class="sxs-lookup"><span data-stu-id="d6211-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="d6211-196">En este tutorial, esta carpeta es MyControls\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="d6211-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="d6211-197">Seleccione Datacontrols. dll y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6211-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="d6211-198">Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="d6211-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="d6211-199">Implementar el diseño básico</span><span class="sxs-lookup"><span data-stu-id="d6211-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="d6211-200">La [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación host se implementa en MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="d6211-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="d6211-201">Este archivo contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado que define el diseño y hospeda el control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d6211-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="d6211-202">La aplicación se divide en tres regiones:</span><span class="sxs-lookup"><span data-stu-id="d6211-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="d6211-203">El panel **propiedades del control** , que contiene una colección de botones de opción que puede usar para modificar diversas propiedades del control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="d6211-204">Los **datos del panel de control** , que contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos por el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="d6211-205">El control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-205">The hosted control itself.</span></span>

 <span data-ttu-id="d6211-206">En el siguiente código XAML se muestra el diseño básico.</span><span class="sxs-lookup"><span data-stu-id="d6211-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="d6211-207">El marcado que se necesita para hospedar `MyControl1` se omite en este ejemplo, pero se tratará más adelante.</span><span class="sxs-lookup"><span data-stu-id="d6211-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="d6211-208">Reemplace el código XAML del archivo MainWindow.xaml.vb por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d6211-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="d6211-209">Si está utilizando Visual Basic, cambie la clase a `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="d6211-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="d6211-210">El primer elemento <xref:System.Windows.Controls.StackPanel> contiene varios conjuntos de controles <xref:System.Windows.Controls.RadioButton> que permiten modificar diversas propiedades predeterminadas del control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="d6211-211">Seguido de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, que hospeda `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="d6211-212">El último elemento <xref:System.Windows.Controls.StackPanel> contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos por el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="d6211-213">El orden de los elementos y los valores de los atributos <xref:System.Windows.Controls.DockPanel.Dock%2A> y <xref:System.Windows.FrameworkElement.Height%2A> insertan el control hospedado en la ventana sin espacios ni distorsión.</span><span class="sxs-lookup"><span data-stu-id="d6211-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="d6211-214">Hospedar el control</span><span class="sxs-lookup"><span data-stu-id="d6211-214">Hosting the Control</span></span>
 <span data-ttu-id="d6211-215">La siguiente versión editada del código XAML anterior se centra en los elementos necesarios para hospedar `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="d6211-216">El atributo de asignación de espacio de nombres `xmlns` crea una referencia al espacio de nombres `MyControls` que contiene el control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="d6211-217">Esta asignación permite representar `MyControl1` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como `<mcl:MyControl1>`.</span><span class="sxs-lookup"><span data-stu-id="d6211-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="d6211-218">Dos elementos del código XAML controlan el hospedaje:</span><span class="sxs-lookup"><span data-stu-id="d6211-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="d6211-219">`WindowsFormsHost` representa el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> que permite hospedar un control Windows Forms en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6211-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="d6211-220">`mcl:MyControl1`, que representa `MyControl1`, se agrega a la colección secundaria del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="d6211-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="d6211-221">Como resultado, este control de Windows Forms se representa como parte de la ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y puede comunicarse con el control desde la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6211-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="d6211-222">Implementar el archivo de código subyacente</span><span class="sxs-lookup"><span data-stu-id="d6211-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="d6211-223">El archivo de código subyacente, MainWindow. Xaml. vb o MainWindow.xaml.cs, contiene el código de procedimiento que implementa la funcionalidad de los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="d6211-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="d6211-224">Las tareas principales son:</span><span class="sxs-lookup"><span data-stu-id="d6211-224">The primary tasks are:</span></span>

- <span data-ttu-id="d6211-225">Adjuntar un controlador de eventos al evento `OnButtonClick` de `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="d6211-226">Modificar varias propiedades de `MyControl1`, en función de cómo se establece la colección de botones de opción.</span><span class="sxs-lookup"><span data-stu-id="d6211-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="d6211-227">Mostrar los datos recopilados por el control.</span><span class="sxs-lookup"><span data-stu-id="d6211-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="d6211-228">Inicializar la aplicación</span><span class="sxs-lookup"><span data-stu-id="d6211-228">Initializing the Application</span></span>
 <span data-ttu-id="d6211-229">El código de inicialización está contenido en un controlador de eventos para el evento de <xref:System.Windows.FrameworkElement.Loaded> de la ventana y asocia un controlador de eventos al evento de `OnButtonClick` del control.</span><span class="sxs-lookup"><span data-stu-id="d6211-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="d6211-230">En MainWindow. Xaml. vb o MainWindow.xaml.cs, agregue el código siguiente a la clase `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="d6211-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="d6211-231">Dado que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] explicó anteriormente ha agregado `MyControl1` a la colección de elementos secundarios del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, puede convertir el <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> del elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> para obtener la referencia a `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="d6211-232">Después, puede usar esa referencia para adjuntar un controlador de eventos a `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="d6211-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="d6211-233">Además de proporcionar una referencia al propio control, <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone una serie de las propiedades del control, que se pueden manipular desde la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6211-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="d6211-234">El código de inicialización asigna estos valores a variables globales privadas para su uso posterior en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6211-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="d6211-235">Para que pueda tener acceso fácilmente a los tipos de la DLL `MyControls`, agregue la siguiente `Imports` o `using` instrucción en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="d6211-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="d6211-236">Controlar el evento OnButtonClick</span><span class="sxs-lookup"><span data-stu-id="d6211-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="d6211-237">`MyControl1` provoca el evento `OnButtonClick` cuando el usuario hace clic en cualquiera de los botones del control.</span><span class="sxs-lookup"><span data-stu-id="d6211-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="d6211-238">Agregue el código siguiente a la clase `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="d6211-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="d6211-239">Los datos de los cuadros de texto se empaquetan en el objeto `MyControlEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="d6211-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="d6211-240">Si el usuario hace clic en el botón **Aceptar** , el controlador de eventos extrae los datos y los muestra en el panel siguiente `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="d6211-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="d6211-241">Modificar las propiedades del control</span><span class="sxs-lookup"><span data-stu-id="d6211-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="d6211-242">El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone algunas de las propiedades predeterminadas del control hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6211-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="d6211-243">Como resultado, puede cambiar el aspecto del control para que se adapte mejor al estilo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6211-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="d6211-244">Los conjuntos de botones de opción del panel izquierdo permiten al usuario modificar varias propiedades de color y fuente.</span><span class="sxs-lookup"><span data-stu-id="d6211-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="d6211-245">Cada conjunto de botones tiene un controlador para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, que detecta las selecciones del botón de opción del usuario y cambia la propiedad correspondiente en el control.</span><span class="sxs-lookup"><span data-stu-id="d6211-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="d6211-246">Agregue el código siguiente a la clase `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="d6211-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="d6211-247">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6211-247">Build and run the application.</span></span> <span data-ttu-id="d6211-248">Agregue texto en el Windows Forms control compuesto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6211-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="d6211-249">El texto aparece en las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d6211-249">The text appears in the labels.</span></span> <span data-ttu-id="d6211-250">Haga clic en los diferentes botones de radio para ver el efecto en el control.</span><span class="sxs-lookup"><span data-stu-id="d6211-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6211-251">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6211-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d6211-252">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d6211-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="d6211-253">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="d6211-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="d6211-254">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d6211-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

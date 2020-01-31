---
title: 'Tutorial: Localizar una aplicación híbrida'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: b406d539f2446824027e9462c8ecbe20c18cfb27
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794124"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="23397-102">Tutorial: Localizar una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="23397-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="23397-103">En este tutorial se muestra cómo localizar elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una aplicación híbrida basada en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23397-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="23397-104">Las tareas ilustradas en este tutorial incluyen:</span><span class="sxs-lookup"><span data-stu-id="23397-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="23397-105">Crear el proyecto de host de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23397-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="23397-106">Agregar contenido localizable.</span><span class="sxs-lookup"><span data-stu-id="23397-106">Adding localizable content.</span></span>

- <span data-ttu-id="23397-107">Habilitar la localización.</span><span class="sxs-lookup"><span data-stu-id="23397-107">Enabling localization.</span></span>

- <span data-ttu-id="23397-108">Asignar identificadores de recursos.</span><span class="sxs-lookup"><span data-stu-id="23397-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="23397-109">Usar la herramienta LocBaml para generar un ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="23397-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="23397-110">Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [localizar una aplicación híbrida de ejemplo](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="23397-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="23397-111">Cuando haya terminado, tendrá una aplicación híbrida localizada.</span><span class="sxs-lookup"><span data-stu-id="23397-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="23397-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="23397-112">Prerequisites</span></span>

<span data-ttu-id="23397-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="23397-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="23397-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="23397-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="23397-115">Crear el proyecto del host de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23397-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="23397-116">El primer paso consiste en crear el proyecto de aplicación de Windows Forms y agregar un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con el contenido que se va a localizar.</span><span class="sxs-lookup"><span data-stu-id="23397-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="23397-117">Para crear el proyecto del host</span><span class="sxs-lookup"><span data-stu-id="23397-117">To create the host project</span></span>

1. <span data-ttu-id="23397-118">Cree un proyecto de **aplicación de WPF** denominado `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="23397-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="23397-119">(**Archivo** > **nuevo** **proyecto** de >  \*\* > C# visual\*\* o **Visual Basic** > **aplicación WPF** > de **escritorio clásico** ).</span><span class="sxs-lookup"><span data-stu-id="23397-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="23397-120">Agregue un elemento de <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]denominado `SimpleControl` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="23397-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="23397-121">Utilice el control <xref:System.Windows.Forms.Integration.ElementHost> para colocar un elemento `SimpleControl` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="23397-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="23397-122">Para obtener más información, vea [Tutorial: hospedar un control compuesto de WPF 3D en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="23397-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="23397-123">Agregar contenido localizable</span><span class="sxs-lookup"><span data-stu-id="23397-123">Adding Localizable Content</span></span>

<span data-ttu-id="23397-124">A continuación, agregará un control etiqueta de Windows Forms y establecerá el contenido del elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una cadena localizable.</span><span class="sxs-lookup"><span data-stu-id="23397-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="23397-125">Para agregar contenido localizable</span><span class="sxs-lookup"><span data-stu-id="23397-125">To add localizable content</span></span>

1. <span data-ttu-id="23397-126">En **Explorador de soluciones**, haga doble clic en **SimpleControl. Xaml** para abrirlo en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="23397-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="23397-127">Establezca el contenido del control <xref:System.Windows.Controls.Button> mediante el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="23397-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="23397-128">En **Explorador de soluciones**, haga doble clic en **Form1** para abrirlo en el diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23397-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="23397-129">Abra el **cuadro de herramientas** y haga doble clic en **etiqueta** para agregar un control etiqueta al formulario.</span><span class="sxs-lookup"><span data-stu-id="23397-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="23397-130">Establezca el valor de su propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="23397-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="23397-131">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="23397-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="23397-132">Tanto el elemento `SimpleControl` como el control etiqueta muestran el texto **"Hello"** .</span><span class="sxs-lookup"><span data-stu-id="23397-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="23397-133">Habilitar la localización</span><span class="sxs-lookup"><span data-stu-id="23397-133">Enabling Localization</span></span>

<span data-ttu-id="23397-134">El Diseñador de Windows Forms proporciona opciones para habilitar la localización en un ensamblado satélite.</span><span class="sxs-lookup"><span data-stu-id="23397-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="23397-135">Para habilitar la localización</span><span class="sxs-lookup"><span data-stu-id="23397-135">To enable localization</span></span>

1. <span data-ttu-id="23397-136">En **Explorador de soluciones**, haga doble clic en **Form1.CS** para abrirlo en el diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="23397-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="23397-137">En la ventana **propiedades** , establezca el valor de la propiedad **traducible** del formulario en `true`.</span><span class="sxs-lookup"><span data-stu-id="23397-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="23397-138">En la ventana **propiedades** , establezca el valor de la propiedad **idioma** en **Español (España)** .</span><span class="sxs-lookup"><span data-stu-id="23397-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="23397-139">En el Diseñador de Windows Forms, seleccione el control de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="23397-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="23397-140">En la ventana **propiedades** , establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Text%2A> en `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="23397-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="23397-141">Se ha agregado al proyecto un nuevo archivo de recursos denominado Form1.es-ES.resx.</span><span class="sxs-lookup"><span data-stu-id="23397-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="23397-142">En **Explorador de soluciones**, haga clic con el botón secundario en **Form1.CS** y haga clic en **Ver código** para abrirlo en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="23397-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="23397-143">Copie el código siguiente en el constructor `Form1`, antes de la llamada a `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="23397-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="23397-144">En **Explorador de soluciones**, haga clic con el botón secundario en **LocalizingWpfInWf** y haga clic en **descargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="23397-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="23397-145">El nombre del proyecto tiene la etiqueta **(no disponible)** .</span><span class="sxs-lookup"><span data-stu-id="23397-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="23397-146">Haga clic con el botón secundario en **LocalizingWpfInWf**y haga clic en **Editar LocalizingWpfInWf. csproj**.</span><span class="sxs-lookup"><span data-stu-id="23397-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="23397-147">El archivo del proyecto se abre en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="23397-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="23397-148">Copie la siguiente línea en el primer `PropertyGroup` del archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="23397-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="23397-149">Guarde el archivo del proyecto y ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="23397-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="23397-150">En **Explorador de soluciones**, haga clic con el botón secundario en **LocalizingWpfInWf** y haga clic en **volver a cargar el proyecto**.</span><span class="sxs-lookup"><span data-stu-id="23397-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="23397-151">Asignar identificadores de recursos</span><span class="sxs-lookup"><span data-stu-id="23397-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="23397-152">Puede asignar el contenido localizable a ensamblados de recursos usando identificadores de recursos.</span><span class="sxs-lookup"><span data-stu-id="23397-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="23397-153">La aplicación MsBuild. exe asigna automáticamente los identificadores de recursos cuando se especifica la opción `updateuid`.</span><span class="sxs-lookup"><span data-stu-id="23397-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="23397-154">Para asignar identificadores de recursos</span><span class="sxs-lookup"><span data-stu-id="23397-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="23397-155">En el menú Inicio, abra el Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="23397-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="23397-156">Use el siguiente comando para asignar identificadores de recursos al contenido localizable.</span><span class="sxs-lookup"><span data-stu-id="23397-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="23397-157">En **Explorador de soluciones**, haga doble clic en **SimpleControl. Xaml** para abrirlo en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="23397-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="23397-158">Verá que el comando `msbuild` ha agregado el atributo `Uid` a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="23397-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="23397-159">Esto facilita la localización mediante la asignación de identificadores de recursos.</span><span class="sxs-lookup"><span data-stu-id="23397-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="23397-160">Presione **F6** para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="23397-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="23397-161">Usar LocBaml para generar un ensamblado satélite</span><span class="sxs-lookup"><span data-stu-id="23397-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="23397-162">El contenido localizado se almacena en un *ensamblado satélite*solo de recursos.</span><span class="sxs-lookup"><span data-stu-id="23397-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="23397-163">Use la herramienta de línea de comandos LocBaml. exe para generar un ensamblado localizado para el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23397-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="23397-164">Para generar un ensamblado satélite</span><span class="sxs-lookup"><span data-stu-id="23397-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="23397-165">Copie LocBaml.exe en la carpeta obj\Debug del proyecto.</span><span class="sxs-lookup"><span data-stu-id="23397-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="23397-166">Para obtener más información, consulte [localizar una aplicación](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="23397-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="23397-167">En la ventana del símbolo del sistema, use el siguiente comando para extraer las cadenas de recursos en un archivo temporal.</span><span class="sxs-lookup"><span data-stu-id="23397-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="23397-168">Abra el archivo temp. csv con Visual Studio u otro editor de texto.</span><span class="sxs-lookup"><span data-stu-id="23397-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="23397-169">Reemplace la cadena `"Hello"` por su traducción española `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="23397-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="23397-170">Guarde el archivo temp.csv.</span><span class="sxs-lookup"><span data-stu-id="23397-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="23397-171">Use el siguiente comando para generar el archivo de recursos localizado.</span><span class="sxs-lookup"><span data-stu-id="23397-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="23397-172">El archivo LocalizingWpfInWf.g.es-ES.resources se crea en la carpeta obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="23397-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="23397-173">Use el siguiente comando para compilar el ensamblado satélite localizado.</span><span class="sxs-lookup"><span data-stu-id="23397-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="23397-174">El archivo LocalizingWpfInWf.resources.dll se crea en la carpeta obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="23397-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="23397-175">Copie el archivo LocalizingWpfInWf.resources.dll en la carpeta bin\Debug\es-ES del proyecto.</span><span class="sxs-lookup"><span data-stu-id="23397-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="23397-176">Reemplace el archivo existente.</span><span class="sxs-lookup"><span data-stu-id="23397-176">Replace the existing file.</span></span>

8. <span data-ttu-id="23397-177">Ejecute LocalizingWpfInWf.exe, que se encuentra en la carpeta bin\Debug del proyecto.</span><span class="sxs-lookup"><span data-stu-id="23397-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="23397-178">No vuelva a compilar la aplicación; de lo contrario, el ensamblado satélite se sobrescribirá.</span><span class="sxs-lookup"><span data-stu-id="23397-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="23397-179">La aplicación muestra las cadenas localizadas en lugar de las cadenas en inglés.</span><span class="sxs-lookup"><span data-stu-id="23397-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="23397-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="23397-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="23397-181">Localizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="23397-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="23397-182">[Tutorial: localizar Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="23397-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="23397-183">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="23397-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)

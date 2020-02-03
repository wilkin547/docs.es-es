---
title: Almacenar datos en la aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728058"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="572b3-102">Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="572b3-103">El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido.</span><span class="sxs-lookup"><span data-stu-id="572b3-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="572b3-104">Cuando se vuelve a acceder a los datos, las aplicaciones pueden obtenerlos de la memoria caché en lugar de recuperarlos de la fuente original.</span><span class="sxs-lookup"><span data-stu-id="572b3-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="572b3-105">Esto puede mejorar el rendimiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="572b3-105">This can improve performance and scalability.</span></span> <span data-ttu-id="572b3-106">Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.</span><span class="sxs-lookup"><span data-stu-id="572b3-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="572b3-107">El .NET Framework proporciona clases que permiten usar el almacenamiento en caché en aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="572b3-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="572b3-108">Estas clases se encuentran en el espacio de nombres <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="572b3-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="572b3-109">El espacio de nombres <xref:System.Runtime.Caching> es nuevo en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="572b3-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="572b3-110">Este espacio de nombres hace que el almacenamiento en caché esté disponible para todas .NET Framework aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="572b3-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="572b3-111">En versiones anteriores del .NET Framework, el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, requería una dependencia en las clases ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="572b3-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="572b3-112">En este tutorial se muestra cómo usar la funcionalidad de almacenamiento en caché que está disponible en el .NET Framework como parte de una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="572b3-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="572b3-113">En el tutorial, almacenará en caché el contenido de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="572b3-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="572b3-114">Las tareas que se ilustran en este tutorial son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="572b3-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="572b3-115">Crear un proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="572b3-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="572b3-116">Agregar una referencia al .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="572b3-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="572b3-117">Inicializar una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-117">Initializing a cache.</span></span>

- <span data-ttu-id="572b3-118">Agregar una entrada de caché que incluye el contenido de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="572b3-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="572b3-119">Proporcionar una directiva de expulsión para la entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="572b3-120">Supervisar la ruta de acceso del archivo en caché y notificar a la instancia de caché los cambios en el elemento supervisado.</span><span class="sxs-lookup"><span data-stu-id="572b3-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="572b3-121">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="572b3-121">Prerequisites</span></span>
 <span data-ttu-id="572b3-122">Para completar esta visita guiada, necesitará:</span><span class="sxs-lookup"><span data-stu-id="572b3-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="572b3-123">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="572b3-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="572b3-124">Un archivo de texto que contiene una pequeña cantidad de texto.</span><span class="sxs-lookup"><span data-stu-id="572b3-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="572b3-125">(Se mostrará el contenido del archivo de texto en un cuadro de mensaje). En el código que se muestra en el tutorial se da por supuesto que está trabajando con el siguiente archivo:</span><span class="sxs-lookup"><span data-stu-id="572b3-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="572b3-126">Sin embargo, puede usar cualquier archivo de texto y realizar pequeños cambios en el código de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="572b3-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="572b3-127">Crear un proyecto de aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="572b3-128">Comenzará creando un proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="572b3-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="572b3-129">Para crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-129">To create a WPF application</span></span>

1. <span data-ttu-id="572b3-130">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="572b3-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="572b3-131">En el menú **archivo** , haga clic en **nuevo**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="572b3-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="572b3-132">Se muestra el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="572b3-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="572b3-133">En **plantillas instaladas**, seleccione el lenguaje de programación que desea usar (**Visual Basic** o **Visual C#** ).</span><span class="sxs-lookup"><span data-stu-id="572b3-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="572b3-134">En el cuadro de diálogo **nuevo proyecto** , seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="572b3-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="572b3-135">Si no ve la plantilla de **aplicación de WPF** , asegúrese de que tiene como destino una versión de la .NET Framework que admite WPF.</span><span class="sxs-lookup"><span data-stu-id="572b3-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="572b3-136">En el cuadro de diálogo **nuevo proyecto** , seleccione .NET Framework 4 en la lista.</span><span class="sxs-lookup"><span data-stu-id="572b3-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="572b3-137">En el cuadro de texto **nombre** , escriba un nombre para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="572b3-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="572b3-138">Por ejemplo, puede escribir **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="572b3-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="572b3-139">Active la casilla **Crear directorio para la solución**.</span><span class="sxs-lookup"><span data-stu-id="572b3-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="572b3-140">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="572b3-140">Click **OK**.</span></span>

     <span data-ttu-id="572b3-141">WPF Designer se abre en la vista de **diseño** y muestra el archivo MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="572b3-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="572b3-142">Visual Studio crea la carpeta **mi proyecto** , el archivo Application. XAML y el archivo MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="572b3-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="572b3-143">Establecer como destino el .NET Framework y agregar una referencia a los ensamblados de almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="572b3-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="572b3-144">De forma predeterminada, las aplicaciones de WPF tienen como destino el perfil de cliente de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="572b3-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="572b3-145">Para usar el espacio de nombres <xref:System.Runtime.Caching> en una aplicación de WPF, la aplicación debe tener como destino el .NET Framework 4 (no el perfil de cliente de .NET Framework 4) y debe incluir una referencia al espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="572b3-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="572b3-146">Por lo tanto, el siguiente paso es cambiar el destino de .NET Framework y agregar una referencia al espacio de nombres <xref:System.Runtime.Caching>.</span><span class="sxs-lookup"><span data-stu-id="572b3-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="572b3-147">El procedimiento para cambiar el destino de .NET Framework es diferente en un proyecto de Visual Basic y en C# un proyecto visual.</span><span class="sxs-lookup"><span data-stu-id="572b3-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="572b3-148">Para cambiar la .NET Framework de destino en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="572b3-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="572b3-149">En el **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="572b3-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="572b3-150">Se muestra la ventana Propiedades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="572b3-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="572b3-151">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="572b3-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="572b3-152">En la parte inferior de la ventana, haga clic en **Opciones de compilación avanzadas.** .</span><span class="sxs-lookup"><span data-stu-id="572b3-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="572b3-153">Se muestra el cuadro de diálogo **configuración de compilador avanzada** .</span><span class="sxs-lookup"><span data-stu-id="572b3-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="572b3-154">En la lista versión de **.NET Framework de destino (todas las configuraciones)** , seleccione .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="572b3-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="572b3-155">(No seleccione .NET Framework 4 Client Profile).</span><span class="sxs-lookup"><span data-stu-id="572b3-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="572b3-156">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="572b3-156">Click **OK**.</span></span>

     <span data-ttu-id="572b3-157">Aparecerá el cuadro de diálogo **Cambio de plataforma de destino**.</span><span class="sxs-lookup"><span data-stu-id="572b3-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="572b3-158">En el cuadro de diálogo cambio de versión de **.NET Framework de destino** , haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="572b3-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="572b3-159">El proyecto está cerrado y se vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="572b3-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="572b3-160">Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="572b3-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="572b3-161">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="572b3-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="572b3-162">Seleccione la pestaña **.net** , seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="572b3-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="572b3-163">Para cambiar el .NET Framework de destino en un C# proyecto visual</span><span class="sxs-lookup"><span data-stu-id="572b3-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="572b3-164">En **Explorador de soluciones**, haga clic con el botón secundario en el nombre del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="572b3-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="572b3-165">Se muestra la ventana Propiedades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="572b3-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="572b3-166">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="572b3-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="572b3-167">En la lista **plataforma de destino** , seleccione .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="572b3-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="572b3-168">(No seleccione **.NET Framework 4 Client Profile**).</span><span class="sxs-lookup"><span data-stu-id="572b3-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="572b3-169">Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="572b3-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="572b3-170">Haga clic con el botón secundario en la carpeta **referencias** y después haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="572b3-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="572b3-171">Seleccione la pestaña **.net** , seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="572b3-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="572b3-172">Agregar un botón a la ventana de WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="572b3-173">A continuación, agregará un control de botón y creará un controlador de eventos para el evento de `Click` del botón.</span><span class="sxs-lookup"><span data-stu-id="572b3-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="572b3-174">Más adelante agregará código al hacer clic en el botón, el contenido del archivo de texto se almacenará en la memoria caché y se mostrará.</span><span class="sxs-lookup"><span data-stu-id="572b3-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="572b3-175">Para agregar un control de botón</span><span class="sxs-lookup"><span data-stu-id="572b3-175">To add a button control</span></span>

1. <span data-ttu-id="572b3-176">En **Explorador de soluciones**, haga doble clic en el archivo MainWindow. XAML para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="572b3-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="572b3-177">En el **cuadro de herramientas**, en **controles WPF comunes**, arrastre un control `Button` a la ventana `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="572b3-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="572b3-178">En la ventana **propiedades** , establezca la propiedad `Content` del control `Button` en **obtener caché**.</span><span class="sxs-lookup"><span data-stu-id="572b3-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="572b3-179">Inicialización de la memoria caché y almacenamiento en caché de una entrada</span><span class="sxs-lookup"><span data-stu-id="572b3-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="572b3-180">A continuación, agregará el código para realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="572b3-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="572b3-181">Cree una instancia de la clase cache, es decir, creará una instancia de un nuevo objeto <xref:System.Runtime.Caching.MemoryCache>.</span><span class="sxs-lookup"><span data-stu-id="572b3-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="572b3-182">Especifica que la memoria caché utiliza un objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> para supervisar los cambios en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="572b3-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="572b3-183">Lea el archivo de texto y almacene en caché su contenido como una entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="572b3-184">Mostrar el contenido del archivo de texto almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="572b3-185">Para crear el objeto de caché</span><span class="sxs-lookup"><span data-stu-id="572b3-185">To create the cache object</span></span>

1. <span data-ttu-id="572b3-186">Haga doble clic en el botón que acaba de agregar para crear un controlador de eventos en el archivo MainWindow.xaml.cs o MainWindow. Xaml. VB.</span><span class="sxs-lookup"><span data-stu-id="572b3-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="572b3-187">En la parte superior del archivo (antes de la declaración de clase), agregue las siguientes instrucciones `Imports` (Visual Basic)C#o `using` ():</span><span class="sxs-lookup"><span data-stu-id="572b3-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="572b3-188">En el controlador de eventos, agregue el código siguiente para crear una instancia del objeto de caché:</span><span class="sxs-lookup"><span data-stu-id="572b3-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="572b3-189">La clase <xref:System.Runtime.Caching.ObjectCache> es una clase integrada que proporciona una memoria caché de objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="572b3-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="572b3-190">Agregue el código siguiente para leer el contenido de una entrada de caché denominada `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="572b3-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="572b3-191">Agregue el código siguiente para comprobar si existe la entrada de caché denominada `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="572b3-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="572b3-192">Si la entrada de caché especificada no existe, debe leer el archivo de texto y agregarlo como una entrada de caché a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="572b3-193">En el bloque `if/then`, agregue el código siguiente para crear un nuevo objeto <xref:System.Runtime.Caching.CacheItemPolicy> que especifique que la entrada de caché expira después de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="572b3-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="572b3-194">Si no se proporciona ninguna información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché nunca expiran en función de un tiempo absoluto.</span><span class="sxs-lookup"><span data-stu-id="572b3-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="572b3-195">En su lugar, las entradas de la memoria caché expiran solo cuando hay presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="572b3-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="572b3-196">Como práctica recomendada, siempre debe proporcionar explícitamente una expiración absoluta o variable.</span><span class="sxs-lookup"><span data-stu-id="572b3-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="572b3-197">En el bloque `if/then` y siga el código que agregó en el paso anterior, agregue el código siguiente para crear una colección para las rutas de acceso de archivo que desea supervisar y para agregar la ruta de acceso del archivo de texto a la colección:</span><span class="sxs-lookup"><span data-stu-id="572b3-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="572b3-198">Si el archivo de texto que desea usar no está `c:\cache\cacheText.txt`, especifique la ruta de acceso donde se encuentra el archivo de texto que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="572b3-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="572b3-199">Después del código que agregó en el paso anterior, agregue el código siguiente para agregar un nuevo objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> a la colección de monitores de cambios para la entrada de caché:</span><span class="sxs-lookup"><span data-stu-id="572b3-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="572b3-200">El objeto <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se producen cambios.</span><span class="sxs-lookup"><span data-stu-id="572b3-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="572b3-201">En este ejemplo, la entrada de la caché expirará si cambia el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="572b3-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="572b3-202">Después del código que agregó en el paso anterior, agregue el código siguiente para leer el contenido del archivo de texto:</span><span class="sxs-lookup"><span data-stu-id="572b3-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="572b3-203">La marca de tiempo de fecha y hora se agrega para que pueda ver cuándo expira la entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="572b3-204">Después del código que agregó en el paso anterior, agregue el código siguiente para insertar el contenido del archivo en el objeto de caché como una instancia de <xref:System.Runtime.Caching.CacheItem>:</span><span class="sxs-lookup"><span data-stu-id="572b3-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="572b3-205">Especifique información sobre cómo se debe expulsar la entrada de caché pasando el <xref:System.Runtime.Caching.CacheItemPolicy> objeto que creó anteriormente como parámetro.</span><span class="sxs-lookup"><span data-stu-id="572b3-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="572b3-206">Después del bloque `if/then`, agregue el código siguiente para mostrar el contenido del archivo almacenado en memoria caché en un cuadro de mensaje:</span><span class="sxs-lookup"><span data-stu-id="572b3-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="572b3-207">En el menú **compilar** , haga clic en **compilar WPFCaching** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="572b3-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="572b3-208">Probar el almacenamiento en caché en la aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="572b3-209">Ahora puede probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="572b3-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="572b3-210">Para probar el almacenamiento en caché en la aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="572b3-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="572b3-211">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="572b3-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="572b3-212">Se muestra la ventana `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="572b3-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="572b3-213">Haga clic en **obtener caché**.</span><span class="sxs-lookup"><span data-stu-id="572b3-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="572b3-214">El contenido almacenado en caché del archivo de texto se muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="572b3-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="572b3-215">Observe la marca de tiempo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="572b3-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="572b3-216">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="572b3-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="572b3-217">La marca de tiempo no cambia.</span><span class="sxs-lookup"><span data-stu-id="572b3-217">The timestamp is unchanged.</span></span> <span data-ttu-id="572b3-218">Esto indica que se muestra el contenido almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="572b3-219">Espere 10 segundos o más y, a continuación, haga clic en **obtener caché** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="572b3-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="572b3-220">Esta vez se muestra una nueva marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="572b3-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="572b3-221">Esto indica que la Directiva permite que la entrada de caché expire y que se muestre el nuevo contenido almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="572b3-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="572b3-222">En un editor de texto, abra el archivo de texto que creó.</span><span class="sxs-lookup"><span data-stu-id="572b3-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="572b3-223">No realice ningún cambio todavía.</span><span class="sxs-lookup"><span data-stu-id="572b3-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="572b3-224">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="572b3-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="572b3-225">Observe la marca de tiempo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="572b3-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="572b3-226">Realice un cambio en el archivo de texto y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="572b3-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="572b3-227">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="572b3-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="572b3-228">Este cuadro de mensaje contiene el contenido actualizado del archivo de texto y una nueva marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="572b3-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="572b3-229">Esto indica que el monitor de cambio de archivo de host expulsó la entrada de caché inmediatamente al cambiar el archivo, aunque el período de tiempo de espera absoluto no haya expirado.</span><span class="sxs-lookup"><span data-stu-id="572b3-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="572b3-230">Puede aumentar el tiempo de expulsión hasta 20 segundos o más para dejar más tiempo para que realice un cambio en el archivo.</span><span class="sxs-lookup"><span data-stu-id="572b3-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="572b3-231">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="572b3-231">Code Example</span></span>
 <span data-ttu-id="572b3-232">Una vez que haya completado este tutorial, el código del proyecto que ha creado será similar al del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="572b3-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="572b3-233">Consulte también</span><span class="sxs-lookup"><span data-stu-id="572b3-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="572b3-234">Almacenamiento en caché en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="572b3-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)

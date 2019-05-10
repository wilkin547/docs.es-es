---
title: 'Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 65dfe906276912b5f6dc8d49af6a2662e3a09157
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630784"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="d67b0-102">Tutorial: Almacenar en caché datos de la aplicación en una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="d67b0-103">El almacenamiento en caché permite almacenar datos en memoria para un acceso rápido.</span><span class="sxs-lookup"><span data-stu-id="d67b0-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="d67b0-104">Cuando se vuelve a acceder a los datos, las aplicaciones pueden obtenerlos de la memoria caché en lugar de recuperarlos de la fuente original.</span><span class="sxs-lookup"><span data-stu-id="d67b0-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="d67b0-105">Esto puede mejorar el rendimiento y la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="d67b0-105">This can improve performance and scalability.</span></span> <span data-ttu-id="d67b0-106">Además, el almacenamiento en caché permite que los datos estén disponibles cuando el origen de datos no está disponible temporalmente.</span><span class="sxs-lookup"><span data-stu-id="d67b0-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="d67b0-107">El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona clases que le permiten usar el almacenamiento en caché en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d67b0-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="d67b0-108">Estas clases se encuentran en el <xref:System.Runtime.Caching> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d67b0-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="d67b0-109">El <xref:System.Runtime.Caching> espacio de nombres es nuevo en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d67b0-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d67b0-110">Hace que este espacio de nombres de almacenamiento en caché está disponible para todos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d67b0-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="d67b0-111">En versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], el almacenamiento en caché solo estaba disponible en el espacio de nombres <xref:System.Web> y, por tanto, exigía una dependencia en las clases de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d67b0-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="d67b0-112">En este tutorial se muestra cómo usar la funcionalidad de almacenamiento en caché está disponible en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] como parte de un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="d67b0-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d67b0-113">En el tutorial, almacenar en caché el contenido de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="d67b0-114">Las tareas que se ilustran en este tutorial son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d67b0-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="d67b0-115">Crear un proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="d67b0-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="d67b0-116">Agregar una referencia a la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d67b0-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

- <span data-ttu-id="d67b0-117">Inicializando una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-117">Initializing a cache.</span></span>

- <span data-ttu-id="d67b0-118">Agregar una entrada de caché que contiene el contenido de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="d67b0-119">Proporcionar una directiva de expulsión para la entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="d67b0-120">Supervisión de la ruta de acceso del archivo almacenado en caché y notificar a la instancia de caché acerca de los cambios en los elementos supervisados.</span><span class="sxs-lookup"><span data-stu-id="d67b0-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d67b0-121">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d67b0-121">Prerequisites</span></span>
 <span data-ttu-id="d67b0-122">Para poder completar este tutorial, necesitará:</span><span class="sxs-lookup"><span data-stu-id="d67b0-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="d67b0-123">Microsoft Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="d67b0-123">Microsoft Visual Studio 2010.</span></span>

- <span data-ttu-id="d67b0-124">Un archivo de texto que contiene una pequeña cantidad de texto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="d67b0-125">(Se mostrará el contenido del archivo de texto en un cuadro de mensaje). El código que se muestra en el tutorial se da por supuesto que está trabajando con el siguiente archivo:</span><span class="sxs-lookup"><span data-stu-id="d67b0-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="d67b0-126">Sin embargo, puede usar cualquier archivo de texto y realizar pequeños cambios en el código en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d67b0-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="d67b0-127">Crear un proyecto de aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="d67b0-128">Se iniciará mediante la creación de un proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="d67b0-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="d67b0-129">Para crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-129">To create a WPF application</span></span>

1. <span data-ttu-id="d67b0-130">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d67b0-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="d67b0-131">En el **archivo** menú, haga clic en **New**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="d67b0-132">Aparecerá el cuadro de diálogo **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="d67b0-133">En **plantillas instaladas**, seleccione el lenguaje de programación que desea utilizar (**Visual Basic** o **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="d67b0-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="d67b0-134">En el **nuevo proyecto** cuadro de diálogo, seleccione **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d67b0-135">Si no ve el **aplicación WPF** plantilla, asegúrese de que se usa como destino una versión de la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que es compatible con WPF.</span><span class="sxs-lookup"><span data-stu-id="d67b0-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="d67b0-136">En el **nuevo proyecto** cuadro de diálogo, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] en la lista.</span><span class="sxs-lookup"><span data-stu-id="d67b0-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5. <span data-ttu-id="d67b0-137">En el **nombre** texto, escriba un nombre para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="d67b0-138">Por ejemplo, puede escribir **WPFCaching**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="d67b0-139">Active la casilla **Crear directorio para la solución**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="d67b0-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-140">Click **OK**.</span></span>

     <span data-ttu-id="d67b0-141">Se abre el Diseñador de WPF en **diseño** ver y muestra el archivo MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d67b0-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="d67b0-142">Visual Studio crea el **mi proyecto** carpeta, el archivo Application.xaml y el archivo MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="d67b0-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="d67b0-143">Destinadas a .NET Framework y agregar una referencia a los ensamblados de almacenamiento en caché</span><span class="sxs-lookup"><span data-stu-id="d67b0-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="d67b0-144">De forma predeterminada, el destino de las aplicaciones de WPF la [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d67b0-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="d67b0-145">Para usar el <xref:System.Runtime.Caching> espacio de nombres en una aplicación WPF, la aplicación debe tener como destino el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (no el [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) y debe incluir una referencia al espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d67b0-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="d67b0-146">Por lo tanto, el siguiente paso es cambiar el destino de .NET Framework y agregar una referencia a la <xref:System.Runtime.Caching> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d67b0-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="d67b0-147">El procedimiento para cambiar el destino de .NET Framework es diferente en un proyecto de Visual Basic y en un proyecto de Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d67b0-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="d67b0-148">Para cambiar el destino de .NET Framework en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d67b0-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="d67b0-149">En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="d67b0-150">Se muestra la ventana Propiedades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d67b0-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="d67b0-151">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="d67b0-152">En la parte inferior de la ventana, haga clic en **opciones de compilación avanzadas...** .</span><span class="sxs-lookup"><span data-stu-id="d67b0-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="d67b0-153">El **configuración de compilador avanzada** se muestra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="d67b0-154">En el **.NET framework de destino (todas las configuraciones)** lista, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d67b0-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d67b0-155">(No seleccione [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="d67b0-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5. <span data-ttu-id="d67b0-156">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-156">Click **OK**.</span></span>

     <span data-ttu-id="d67b0-157">Aparecerá el cuadro de diálogo **Cambio de plataforma de destino**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="d67b0-158">En el **cambio de plataforma de destino** cuadro de diálogo, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="d67b0-159">El proyecto se cierra y, a continuación, se vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="d67b0-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="d67b0-160">Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d67b0-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="d67b0-161">En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="d67b0-162">Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="d67b0-163">Para cambiar el destino de .NET Framework en un proyecto de Visual C#</span><span class="sxs-lookup"><span data-stu-id="d67b0-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="d67b0-164">En **el Explorador de soluciones**, haga clic en el nombre del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="d67b0-165">Se muestra la ventana Propiedades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d67b0-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="d67b0-166">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="d67b0-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="d67b0-167">En el **.NET framework de destino** lista, seleccione [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d67b0-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d67b0-168">(No seleccione **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="d67b0-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="d67b0-169">Agregue una referencia al ensamblado de almacenamiento en caché siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d67b0-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="d67b0-170">Haga clic en el **referencias** carpeta y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="d67b0-171">Seleccione el **.NET** ficha, seleccione `System.Runtime.Caching`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="d67b0-172">Agregar un botón a la ventana de WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="d67b0-173">A continuación, agregará un control de botón y crear un controlador de eventos del botón `Click` eventos.</span><span class="sxs-lookup"><span data-stu-id="d67b0-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="d67b0-174">Más adelante agregará código para por lo que al hacer clic en el botón, el contenido del archivo de texto se almacena en caché y se muestran.</span><span class="sxs-lookup"><span data-stu-id="d67b0-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="d67b0-175">Para agregar un control de botón</span><span class="sxs-lookup"><span data-stu-id="d67b0-175">To add a button control</span></span>

1. <span data-ttu-id="d67b0-176">En **el Explorador de soluciones**, haga doble clic en el archivo MainWindow.xaml para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="d67b0-177">Desde el **cuadro de herramientas**, en **controles WPF comunes**, arrastre un `Button` el control a la `MainWindow` ventana.</span><span class="sxs-lookup"><span data-stu-id="d67b0-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="d67b0-178">En el **propiedades** ventana, establezca el `Content` propiedad de la `Button` el control a **obtener caché**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="d67b0-179">Inicializar la memoria caché y almacenamiento en caché una entrada</span><span class="sxs-lookup"><span data-stu-id="d67b0-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="d67b0-180">A continuación, agregará el código para llevar a cabo las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d67b0-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="d67b0-181">Cree una instancia de la clase de caché, es decir, se creará una instancia de un nuevo <xref:System.Runtime.Caching.MemoryCache> objeto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="d67b0-182">Especificar que la memoria caché usa un <xref:System.Runtime.Caching.HostFileChangeMonitor> objetos para supervisar los cambios en el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="d67b0-183">Leer el archivo de texto y su contenido en caché como una entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="d67b0-184">Mostrar el contenido del archivo de texto almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="d67b0-185">Para crear el objeto de caché</span><span class="sxs-lookup"><span data-stu-id="d67b0-185">To create the cache object</span></span>

1. <span data-ttu-id="d67b0-186">Haga doble clic en el botón que acaba de agregar para crear un controlador de eventos en el archivo MainWindow.xaml.cs o MainWindow.Xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="d67b0-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="d67b0-187">En la parte superior del archivo (antes de la declaración de clase), agregue el siguiente `Imports` (Visual Basic) o `using` instrucciones (C#):</span><span class="sxs-lookup"><span data-stu-id="d67b0-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="d67b0-188">En el controlador de eventos, agregue el código siguiente para crear una instancia del objeto de caché:</span><span class="sxs-lookup"><span data-stu-id="d67b0-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="d67b0-189">El <xref:System.Runtime.Caching.ObjectCache> es una clase integrada que proporciona una caché de objetos en memoria.</span><span class="sxs-lookup"><span data-stu-id="d67b0-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="d67b0-190">Agregue el código siguiente para leer el contenido de una entrada de caché denominada `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="d67b0-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="d67b0-191">Agregue el código siguiente para comprobar si la entrada de caché denominada `filecontents` existe:</span><span class="sxs-lookup"><span data-stu-id="d67b0-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="d67b0-192">Si la entrada de caché especificado no existe, debe leer el archivo de texto y agregarlo como una entrada de caché a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="d67b0-193">En el `if/then` en bloques, agregue el código siguiente para crear un nuevo <xref:System.Runtime.Caching.CacheItemPolicy> objeto que especifica que la entrada de caché expira transcurridos 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="d67b0-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="d67b0-194">Si se proporciona ninguna información de expulsión o expiración, el valor predeterminado es <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, lo que significa que las entradas de caché no expiren nunca basándose solo en un tiempo absoluto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="d67b0-195">En su lugar, las entradas de caché expiran solo cuando hay presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="d67b0-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="d67b0-196">Como práctica recomendada, debe proporcionar siempre explícitamente absoluta o una expiración variable.</span><span class="sxs-lookup"><span data-stu-id="d67b0-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="d67b0-197">Dentro de la `if/then` bloquear y después del código que agregó en el paso anterior, agregue el código siguiente para crear una colección para las rutas de acceso de archivo que desea supervisar y para agregar la ruta de acceso del archivo de texto a la colección:</span><span class="sxs-lookup"><span data-stu-id="d67b0-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="d67b0-198">Si el archivo de texto que desea usar no es `c:\cache\cacheText.txt`, especifique la ruta de acceso donde está el archivo de texto que desea usar.</span><span class="sxs-lookup"><span data-stu-id="d67b0-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="d67b0-199">Siguiendo el código que agregó en el paso anterior, agregue el código siguiente para agregar un nuevo <xref:System.Runtime.Caching.HostFileChangeMonitor> supervisa el objeto a la colección de cambios para la entrada de caché:</span><span class="sxs-lookup"><span data-stu-id="d67b0-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="d67b0-200">La <xref:System.Runtime.Caching.HostFileChangeMonitor> objeto supervisa la ruta de acceso del archivo de texto y notifica a la memoria caché si se producen cambios.</span><span class="sxs-lookup"><span data-stu-id="d67b0-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="d67b0-201">En este ejemplo, la entrada de caché expirará si cambia el contenido del archivo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="d67b0-202">Después del código que agregó en el paso anterior, agregue el código siguiente para leer el contenido del archivo de texto:</span><span class="sxs-lookup"><span data-stu-id="d67b0-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="d67b0-203">Se agrega la marca de tiempo de fecha y hora para que puedan ver cuando expira la entrada de caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="d67b0-204">Siguiendo el código que agregó en el paso anterior, agregue el siguiente código para insertar el contenido del archivo en el objeto de caché como un <xref:System.Runtime.Caching.CacheItem> instancia:</span><span class="sxs-lookup"><span data-stu-id="d67b0-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="d67b0-205">Especifique información acerca de cómo debe expulsarse la entrada de caché pasando el <xref:System.Runtime.Caching.CacheItemPolicy> objeto que creó anteriormente como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="d67b0-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="d67b0-206">Después de la `if/then` en bloques, agregue el código siguiente para mostrar el contenido del archivo almacenado en caché en un cuadro de mensaje:</span><span class="sxs-lookup"><span data-stu-id="d67b0-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="d67b0-207">En el **compilar** menú, haga clic en **WPFCaching compilación** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d67b0-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="d67b0-208">Pruebas de almacenamiento en caché en la aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="d67b0-209">Ahora puede probar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d67b0-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="d67b0-210">Para probar el almacenamiento en caché en la aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="d67b0-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="d67b0-211">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d67b0-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="d67b0-212">El `MainWindow` se muestra la ventana.</span><span class="sxs-lookup"><span data-stu-id="d67b0-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="d67b0-213">Haga clic en **obtener memoria caché**.</span><span class="sxs-lookup"><span data-stu-id="d67b0-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="d67b0-214">Se muestra el contenido almacenado en caché del archivo de texto en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d67b0-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="d67b0-215">Tenga en cuenta la marca de tiempo en el archivo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="d67b0-216">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d67b0-217">Se ha modificado la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-217">The timestamp is unchanged.</span></span> <span data-ttu-id="d67b0-218">Esto indica que se muestra el contenido almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="d67b0-219">Espere 10 segundos o más y, a continuación, haga clic en **obtener caché** nuevo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d67b0-220">Este tiempo se muestra una marca de tiempo nueva.</span><span class="sxs-lookup"><span data-stu-id="d67b0-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="d67b0-221">Esto indica que la directiva que permite la entrada de caché expiran y que se muestra el nuevo contenido en caché.</span><span class="sxs-lookup"><span data-stu-id="d67b0-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="d67b0-222">En un editor de texto, abra el archivo de texto que ha creado.</span><span class="sxs-lookup"><span data-stu-id="d67b0-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="d67b0-223">No realice los cambios todavía.</span><span class="sxs-lookup"><span data-stu-id="d67b0-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="d67b0-224">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d67b0-225">Observe nuevamente la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="d67b0-226">Realice un cambio en el archivo de texto y, a continuación, guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="d67b0-227">Cierre el cuadro de mensaje y, a continuación, haga clic en **obtener caché** nuevo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d67b0-228">Este cuadro de mensaje contiene el contenido actualizado desde el archivo de texto y una marca de tiempo nueva.</span><span class="sxs-lookup"><span data-stu-id="d67b0-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="d67b0-229">Esto indica que la supervisión de cambios de archivos host expulsa la entrada de caché inmediatamente cuando cambia el archivo, incluso si no ha expirado el período de tiempo de espera absoluta.</span><span class="sxs-lookup"><span data-stu-id="d67b0-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d67b0-230">Puede aumentar el tiempo de expulsión en 20 segundos o más para dar más tiempo para que pueda realizar un cambio en el archivo.</span><span class="sxs-lookup"><span data-stu-id="d67b0-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="d67b0-231">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="d67b0-231">Code Example</span></span>
 <span data-ttu-id="d67b0-232">Después de completar este tutorial, el código para el proyecto creó tendrá un aspecto similar en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d67b0-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d67b0-233">Vea también</span><span class="sxs-lookup"><span data-stu-id="d67b0-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="d67b0-234">Almacenamiento en caché en aplicaciones .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d67b0-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)

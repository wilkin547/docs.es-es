---
title: Símbolo del sistema para desarrolladores de Visual Studio
ms.date: 08/14/2018
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc88106a54a00b4b12e5043da7961791a98102c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344369"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="c9046-102">Símbolo del sistema para desarrolladores de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9046-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="c9046-103">El Símbolo del sistema para desarrolladores de Visual Studio permite usar herramientas de .NET Framework más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="c9046-103">The Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="c9046-104">Es un símbolo del sistema que establece automáticamente variables de entorno específicas.</span><span class="sxs-lookup"><span data-stu-id="c9046-104">It is a command prompt that automatically sets specific environment variables.</span></span>

> [!div class="button"]
> [<span data-ttu-id="c9046-105">Descarga de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9046-105">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="c9046-106">Búsqueda del símbolo del sistema en el equipo</span><span class="sxs-lookup"><span data-stu-id="c9046-106">Search for the command prompt on your machine</span></span>

<span data-ttu-id="c9046-107">Es posible que tenga varios símbolos del sistema, en función de la versión de Visual Studio y de los SDK adicionales que haya instalado.</span><span class="sxs-lookup"><span data-stu-id="c9046-107">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="c9046-108">Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c9046-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="c9046-109">(Las versiones de 32 y 64 bits de la mayoría de las herramientas son iguales; pero algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits). Si los pasos siguientes no funcionan, puede probar los que se describen en [Buscar manualmente los archivos en el equipo](#manually-locate-the-files-on-your-machine) o [Ejecutar el símbolo del sistema desde Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c9046-109">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [Run the command prompt from inside Visual Studio](#run-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="c9046-110">En Windows 10</span><span class="sxs-lookup"><span data-stu-id="c9046-110">In Windows 10</span></span>

1. <span data-ttu-id="c9046-111">En el cuadro de búsqueda de la barra de tareas, comience a escribir el nombre de la herramienta, como `dev` o `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="c9046-111">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="c9046-112">Esto muestra una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c9046-112">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="c9046-113">Si busca un símbolo del sistema diferente, pruebe a escribir otro término de búsqueda, como `prompt`.</span><span class="sxs-lookup"><span data-stu-id="c9046-113">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="c9046-114">Elija **Símbolo del sistema para desarrolladores de Visual Studio** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="c9046-114">Choose the **Developer Command Prompt for Visual Studio** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="c9046-115">En Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c9046-115">In Windows 8.1</span></span>

1. <span data-ttu-id="c9046-116">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="c9046-116">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="c9046-117">En la pantalla **Inicio**, presione **Ctrl**+**Tabulador** para abrir la lista **Aplicaciones** y escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="c9046-117">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then enter `V`.</span></span> <span data-ttu-id="c9046-118">Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="c9046-118">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="c9046-119">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="c9046-119">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="c9046-120">En Windows 8</span><span class="sxs-lookup"><span data-stu-id="c9046-120">In Windows 8</span></span>

1. <span data-ttu-id="c9046-121">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="c9046-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="c9046-122">En la pantalla **Inicio**, presione la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="c9046-122">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="c9046-123">Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="c9046-123">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="c9046-124">Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="c9046-124">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="c9046-125">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="c9046-125">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="c9046-126">En Windows 7</span><span class="sxs-lookup"><span data-stu-id="c9046-126">In Windows 7</span></span>

1. <span data-ttu-id="c9046-127">Elija **Inicio**, expanda **Todos los programas** y luego, **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="c9046-127">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="c9046-128">Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="c9046-128">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="c9046-129">Si tiene instalados otros SDK, como el [SDK de Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versiones anteriores](https://developer.microsoft.com/windows/downloads/sdk-archive), es posible que vea símbolos del sistema adicionales para las arquitecturas ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="c9046-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="c9046-130">Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="c9046-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="c9046-131">Buscar manualmente los archivos en el equipo</span><span class="sxs-lookup"><span data-stu-id="c9046-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="c9046-132">Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\ProgramData\Microsoft\Windows\Menú Inicio\Programas\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="c9046-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="c9046-133">Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c9046-133">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="c9046-134">Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, *VsDevCmd.bat* o vaya a la carpeta de herramientas; por ejemplo, C:\Archivos de programa (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (la ruta de acceso cambia según la versión de Visual Studio, la edición y la ubicación de instalación).</span><span class="sxs-lookup"><span data-stu-id="c9046-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="c9046-135">Ejecutar el símbolo del sistema desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c9046-135">Run the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="c9046-136">Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú **Herramientas** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9046-136">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="c9046-137">Para que la herramienta esté disponible, agréguela a la lista de herramientas externas.</span><span class="sxs-lookup"><span data-stu-id="c9046-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="c9046-138">Estos son los pasos:</span><span class="sxs-lookup"><span data-stu-id="c9046-138">Here are the steps:</span></span>

1. <span data-ttu-id="c9046-139">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9046-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="c9046-140">Seleccione el menú **Herramientas** y, después, elija **Herramientas externas**.</span><span class="sxs-lookup"><span data-stu-id="c9046-140">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="c9046-141">En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c9046-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="c9046-142">Aparecerá una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="c9046-142">A new entry appears.</span></span>

4. <span data-ttu-id="c9046-143">Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).</span><span class="sxs-lookup"><span data-stu-id="c9046-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="c9046-144">En el campo **Comando**, especifique el archivo que quiere iniciar, como `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="c9046-144">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="c9046-145">En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (este comando inicia el símbolo del sistema para desarrolladores que se instala con Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="c9046-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="c9046-146">Cambie este valor según la ubicación de instalación, la edición y la versión de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9046-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="c9046-147">Elija un valor para el campo **Directorio inicial**, como **Directorio del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c9046-147">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="c9046-148">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="c9046-148">Choose the **OK** button.</span></span>

   <span data-ttu-id="c9046-149">Se agregará el nuevo elemento de menú y podrá acceder al símbolo del sistema desde el menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="c9046-149">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

   ![Elemento de menú del símbolo del sistema en Visual Studio](media/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="c9046-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9046-151">See also</span></span>

- [<span data-ttu-id="c9046-152">Herramientas</span><span class="sxs-lookup"><span data-stu-id="c9046-152">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="c9046-153">Administrar herramientas externas</span><span class="sxs-lookup"><span data-stu-id="c9046-153">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)

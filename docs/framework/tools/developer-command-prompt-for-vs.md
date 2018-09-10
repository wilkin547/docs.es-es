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
ms.openlocfilehash: 4c95074190419dd3e984c7659ede917b83b97f08
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524721"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="52f8f-102">Símbolo del sistema para desarrolladores de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52f8f-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="52f8f-103">El símbolo del sistema para desarrolladores de Visual Studio establece automáticamente las variables de entorno que permiten usar fácilmente las herramientas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="52f8f-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span>

> [!div class="button"]
[<span data-ttu-id="52f8f-104">Descarga de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52f8f-104">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="52f8f-105">Búsqueda del símbolo del sistema en el equipo</span><span class="sxs-lookup"><span data-stu-id="52f8f-105">Searching for the command prompt on your machine</span></span>

<span data-ttu-id="52f8f-106">Es posible que tenga varios símbolos del sistema, en función de la versión de Visual Studio y de los SDK adicionales que haya instalado.</span><span class="sxs-lookup"><span data-stu-id="52f8f-106">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="52f8f-107">Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="52f8f-107">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="52f8f-108">(Las versiones de 32 y 64 bits de la mayoría de las herramientas son iguales; pero algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits). Si los pasos siguientes no funcionan, puede probar los que se describen en [Buscar manualmente los archivos en el equipo](#manually-locating-the-files-on-your-machine) o [Ejecutar el símbolo del sistema desde Visual Studio](#running-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="52f8f-108">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running the command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="52f8f-109">En Windows 10</span><span class="sxs-lookup"><span data-stu-id="52f8f-109">In Windows 10</span></span>

1. <span data-ttu-id="52f8f-110">En el cuadro de búsqueda de la barra de tareas, comience a escribir el nombre de la herramienta, como `dev` o `developer command prompt`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-110">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="52f8f-111">Esto muestra una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="52f8f-111">This brings up a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="52f8f-112">Si busca un símbolo del sistema diferente, pruebe a escribir otro término de búsqueda, como `prompt`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-112">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="52f8f-113">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="52f8f-113">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="52f8f-114">En Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="52f8f-114">In Windows 8.1</span></span>

1. <span data-ttu-id="52f8f-115">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="52f8f-115">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="52f8f-116">En la pantalla **Inicio**, presione `CTRL + TAB` para abrir la lista **Aplicaciones** y escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-116">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="52f8f-117">Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="52f8f-117">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="52f8f-118">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="52f8f-118">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="52f8f-119">En Windows 8</span><span class="sxs-lookup"><span data-stu-id="52f8f-119">In Windows 8</span></span>

1. <span data-ttu-id="52f8f-120">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="52f8f-120">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="52f8f-121">En la pantalla **Inicio**, presione la tecla del logotipo de Windows ![logotipo de Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-121">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="52f8f-122">Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-122">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="52f8f-123">Esto muestra una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="52f8f-123">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="52f8f-124">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="52f8f-124">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="52f8f-125">En Windows 7</span><span class="sxs-lookup"><span data-stu-id="52f8f-125">In Windows 7</span></span>

1. <span data-ttu-id="52f8f-126">Elija **Inicio**, expanda **Todos los programas** y luego, **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="52f8f-126">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="52f8f-127">Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="52f8f-127">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="52f8f-128">Si tiene instalados otros SDK, como el [SDK de Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versiones anteriores](https://developer.microsoft.com/windows/downloads/sdk-archive), es posible que vea símbolos del sistema adicionales para las arquitecturas ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="52f8f-128">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="52f8f-129">Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="52f8f-129">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="52f8f-130">Buscar manualmente los archivos en el equipo</span><span class="sxs-lookup"><span data-stu-id="52f8f-130">Manually locate the files on your machine</span></span>

<span data-ttu-id="52f8f-131">Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\ProgramData\Microsoft\Windows\Menú Inicio\Programas\Visual Studio 2017\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="52f8f-131">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="52f8f-132">Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="52f8f-132">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="52f8f-133">Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, *VsDevCmd.bat* o vaya a la carpeta de herramientas; por ejemplo, C:\Archivos de programa (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (la ruta de acceso cambia según la versión de Visual Studio, la edición y la ubicación de instalación).</span><span class="sxs-lookup"><span data-stu-id="52f8f-133">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="run-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="52f8f-134">Ejecutar el símbolo del sistema desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52f8f-134">Run command prompt from inside Visual Studio</span></span>

<span data-ttu-id="52f8f-135">Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú **Herramientas** de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52f8f-135">For easier access, you can add the Visual Studio Developer Command Prompt, or any other command prompt, to the **Tools** menu in Visual Studio.</span></span> <span data-ttu-id="52f8f-136">Para que la herramienta esté disponible, agréguela a la lista de herramientas externas.</span><span class="sxs-lookup"><span data-stu-id="52f8f-136">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="52f8f-137">Estos son los pasos:</span><span class="sxs-lookup"><span data-stu-id="52f8f-137">Here are the steps:</span></span>

1. <span data-ttu-id="52f8f-138">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52f8f-138">Open Visual Studio.</span></span>

2. <span data-ttu-id="52f8f-139">Seleccione el menú **Herramientas** y, después, elija **Herramientas externas**.</span><span class="sxs-lookup"><span data-stu-id="52f8f-139">Select the **Tools** menu, and then choose **External Tools**.</span></span>

3. <span data-ttu-id="52f8f-140">En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="52f8f-140">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="52f8f-141">Aparecerá una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="52f8f-141">A new entry appears.</span></span>

4. <span data-ttu-id="52f8f-142">Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).</span><span class="sxs-lookup"><span data-stu-id="52f8f-142">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="52f8f-143">En el campo **Comando**, especifique el archivo que quiere iniciar, como `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="52f8f-143">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="52f8f-144">En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (este comando inicia el símbolo del sistema para desarrolladores que se instala con Visual Studio 2017 Enterprise).</span><span class="sxs-lookup"><span data-stu-id="52f8f-144">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="52f8f-145">Cambie este valor según la ubicación de instalación, la edición y la versión de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52f8f-145">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="52f8f-146">Elija un valor para el campo **Directorio inicial**, como **Directorio del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="52f8f-146">Choose a value for the **Initial directory** field, such as **Project Directory**.</span></span>

8. <span data-ttu-id="52f8f-147">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="52f8f-147">Choose the **OK** button.</span></span>

   <span data-ttu-id="52f8f-148">Se agregará el nuevo elemento de menú y podrá acceder al símbolo del sistema desde el menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="52f8f-148">The new menu item is added, and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="52f8f-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="52f8f-149">See also</span></span>

- [<span data-ttu-id="52f8f-150">Herramientas</span><span class="sxs-lookup"><span data-stu-id="52f8f-150">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="52f8f-151">Administrar herramientas externas</span><span class="sxs-lookup"><span data-stu-id="52f8f-151">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)

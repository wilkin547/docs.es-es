---
title: Símbolo del sistema para desarrolladores de Visual Studio
description: Aprenda a usar el Símbolo del sistema para desarrolladores de Visual Studio, que permite usar herramientas de .NET más fácilmente. Establece automáticamente variables de entorno específicas.
ms.date: 01/05/2020
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
ms.openlocfilehash: 92416820f47cb778dfcc916b8626df4aa328814c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167179"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="06c3d-104">Símbolo del sistema para desarrolladores de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06c3d-104">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="06c3d-105">El Símbolo del sistema para desarrolladores de Visual Studio permite usar herramientas de .NET Framework más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="06c3d-105">Developer Command Prompt for Visual Studio enables you to use .NET Framework tools more easily.</span></span> <span data-ttu-id="06c3d-106">Es un símbolo del sistema que establece automáticamente variables de entorno específicas.</span><span class="sxs-lookup"><span data-stu-id="06c3d-106">It's a command prompt that automatically sets specific environment variables.</span></span> <span data-ttu-id="06c3d-107">Una vez abierto el Símbolo del sistema para desarrolladores, puede escribir los comandos para [herramientas de .NET Framework](index.md) como `ildasm` o `clrver`.</span><span class="sxs-lookup"><span data-stu-id="06c3d-107">After opening Developer Command Prompt, you can enter the commands for [.NET Framework tools](index.md) such as `ildasm` or `clrver`.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="06c3d-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="06c3d-108">Prerequisites</span></span>

- [<span data-ttu-id="06c3d-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="06c3d-109">Visual Studio 2019</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

## <a name="search-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="06c3d-110">Búsqueda del símbolo del sistema en el equipo</span><span class="sxs-lookup"><span data-stu-id="06c3d-110">Search for the command prompt on your machine</span></span>

<span data-ttu-id="06c3d-111">Es posible que tenga varios símbolos del sistema, en función de la versión de Visual Studio y de los SDK y las cargas de trabajo adicionales que haya instalado.</span><span class="sxs-lookup"><span data-stu-id="06c3d-111">You may have multiple command prompts, depending on the version of Visual Studio and any additional SDKs and workloads you've installed.</span></span> <span data-ttu-id="06c3d-112">Si los pasos siguientes no funcionan, puede intentar [buscar manualmente los archivos en el equipo](#manually-locate-the-files-on-your-machine) o [ejecutar el símbolo del sistema desde Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="06c3d-112">If the following steps don't work, you can try to [manually locate the files on your machine](#manually-locate-the-files-on-your-machine) or [start the command prompt from inside Visual Studio](#start-the-command-prompt-from-inside-visual-studio).</span></span>

### <a name="windows-10"></a><span data-ttu-id="06c3d-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="06c3d-113">Windows 10</span></span>

1. <span data-ttu-id="06c3d-114">Seleccione **Inicio** ![Tecla del logotipo de Windows del teclado.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="06c3d-114">Select **Start** ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="06c3d-115">y desplácese hasta la letra **V**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-115">and scroll to the letter **V**.</span></span>

1. <span data-ttu-id="06c3d-116">Expanda la carpeta **Visual Studio 2019**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-116">Expand the **Visual Studio 2019** folder.</span></span>

1. <span data-ttu-id="06c3d-117">Elija el **Símbolo del sistema para desarrolladores de VS 2019** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="06c3d-117">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

   <span data-ttu-id="06c3d-118">Como alternativa, puede empezar a escribir el nombre del símbolo del sistema en el cuadro de búsqueda de la barra de tareas y elegir el resultado que desee a medida que la lista de resultados empiece a mostrar las coincidencias de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="06c3d-118">Alternatively, you can start typing the name of the command prompt in the search box on the taskbar, and choose the result you want as the result list starts to display the search matches.</span></span>

   ![GIF animado que muestra el comportamiento de búsqueda en Windows 10](./media/developer-command-prompt-for-vs/windows10-search.gif)

### <a name="windows-81"></a><span data-ttu-id="06c3d-120">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="06c3d-120">Windows 8.1</span></span>

1. <span data-ttu-id="06c3d-121">Vaya a la pantalla **Inicio** al presionar la tecla de logotipo de Windows ![Tecla de logotipo de Windows en el teclado.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span><span class="sxs-lookup"><span data-stu-id="06c3d-121">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo key on the keyboard.](./media/developer-command-prompt-for-vs/windows-logo-key-graphic.png)</span></span> <span data-ttu-id="06c3d-122">en el teclado, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="06c3d-122">on your keyboard for example.</span></span>

1. <span data-ttu-id="06c3d-123">En la pantalla **Inicio**, presione **Ctrl**+**Tabulador** para abrir la lista **Aplicaciones** y presione **V**. Esto muestra una lista que incluye todos los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="06c3d-123">On the **Start** screen, press **Ctrl**+**Tab** to open the **Apps** list, and then press **V**. This brings up a list that includes all installed Visual Studio command prompts.</span></span>

1. <span data-ttu-id="06c3d-124">Elija el **Símbolo del sistema para desarrolladores de VS 2019** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="06c3d-124">Choose **Developer Command Prompt for VS 2019** (or the command prompt you want to use).</span></span>

### <a name="windows-7"></a><span data-ttu-id="06c3d-125">Windows 7</span><span class="sxs-lookup"><span data-stu-id="06c3d-125">Windows 7</span></span>

1. <span data-ttu-id="06c3d-126">Elija **Inicio** y, a continuación, expanda **Todos los programas**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-126">Choose **Start** and then expand **All Programs**.</span></span>

1. <span data-ttu-id="06c3d-127">Elija **Visual Studio 2019** > **Herramientas de Visual Studio** > **Símbolo del sistema para desarrolladores de VS 2019**, o bien el símbolo del sistema que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="06c3d-127">Choose **Visual Studio 2019** > **Visual Studio Tools** > **Developer Command Prompt for VS 2019**, or the command prompt you want to use.</span></span>

   ![Menú Inicio de Windows 7 con el símbolo del sistema resaltado](./media/developer-command-prompt-for-vs/windows7-menu.png)

<span data-ttu-id="06c3d-129">Si tiene instalados otros SDK, como el [SDK de Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk) o [versiones anteriores](https://developer.microsoft.com/windows/downloads/sdk-archive), es posible que vea símbolos del sistema adicionales.</span><span class="sxs-lookup"><span data-stu-id="06c3d-129">If you have other SDKs installed, such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive), you may see additional command prompts.</span></span> <span data-ttu-id="06c3d-130">Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="06c3d-130">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locate-the-files-on-your-machine"></a><span data-ttu-id="06c3d-131">Buscar manualmente los archivos en el equipo</span><span class="sxs-lookup"><span data-stu-id="06c3d-131">Manually locate the files on your machine</span></span>

<span data-ttu-id="06c3d-132">Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span><span class="sxs-lookup"><span data-stu-id="06c3d-132">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in *%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2019\Visual Studio Tools*.</span></span> <span data-ttu-id="06c3d-133">Pero si por alguna razón, la búsqueda del símbolo del sistema no produce los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo.</span><span class="sxs-lookup"><span data-stu-id="06c3d-133">But if, for some reason, searching for the command prompt doesn't produce the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="06c3d-134">Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, *VsDevCmd.bat* o vaya a la carpeta de herramientas; por ejemplo, *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (la ruta de acceso cambia según la versión de Visual Studio, la edición y la ubicación de instalación).</span><span class="sxs-lookup"><span data-stu-id="06c3d-134">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder, such as *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Community\Common7\Tools* (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="start-the-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="06c3d-135">Iniciar el símbolo del sistema desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06c3d-135">Start the command prompt from inside Visual Studio</span></span>

<span data-ttu-id="06c3d-136">Para un acceso más sencillo, puede agregar el Símbolo del sistema para desarrolladores o cualquier otro símbolo del sistema al menú Herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06c3d-136">For easier access, you can add Developer Command Prompt, or any other command prompt, to the Tools menu in Visual Studio.</span></span> <span data-ttu-id="06c3d-137">Para que la herramienta esté disponible, agréguela a la lista de herramientas externas.</span><span class="sxs-lookup"><span data-stu-id="06c3d-137">To make the tool available, add it to the external tools list.</span></span> <span data-ttu-id="06c3d-138">Estos son los pasos:</span><span class="sxs-lookup"><span data-stu-id="06c3d-138">Here are the steps:</span></span>

1. <span data-ttu-id="06c3d-139">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06c3d-139">Open Visual Studio.</span></span>

1. <span data-ttu-id="06c3d-140">En la ventana de inicio, elija **Continuar sin código**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-140">On the start window, choose **Continue without code**.</span></span>

1. <span data-ttu-id="06c3d-141">En la barra de menús, elija **Herramientas** > **Herramientas externas**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-141">On the menu bar, choose **Tools** > **External Tools**.</span></span>

1. <span data-ttu-id="06c3d-142">En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="06c3d-142">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="06c3d-143">Aparecerá una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="06c3d-143">A new entry appears.</span></span>

1. <span data-ttu-id="06c3d-144">Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).</span><span class="sxs-lookup"><span data-stu-id="06c3d-144">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

1. <span data-ttu-id="06c3d-145">En el campo **Comando**, especifique el archivo que quiere iniciar, como `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="06c3d-145">In the **Command** field, specify the file you want to launch, such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

1. <span data-ttu-id="06c3d-146">En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span><span class="sxs-lookup"><span data-stu-id="06c3d-146">In the **Arguments** field, specify where to find the specific command prompt you want to use, such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat"`.</span></span> <span data-ttu-id="06c3d-147">Este comando inicia el Símbolo del sistema para desarrolladores instalado con Visual Studio 2019 Community.</span><span class="sxs-lookup"><span data-stu-id="06c3d-147">This command launches the Developer Command Prompt that's installed with Visual Studio 2019 Community.</span></span> <span data-ttu-id="06c3d-148">Cambie este valor según la ubicación de instalación, la edición y la versión de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="06c3d-148">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

1. <span data-ttu-id="06c3d-149">En el campo **Directorio inicial**, especifique el directorio en el que se iniciará el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="06c3d-149">In the **Initial directory** field, specify the directory in which the command prompt will start.</span></span> <span data-ttu-id="06c3d-150">Elija un valor como **Directorio del proyecto** seleccionando la flecha situada junto al campo.</span><span class="sxs-lookup"><span data-stu-id="06c3d-150">Choose a value such as **Project Directory** by selecting the arrow next to the field.</span></span>

1. <span data-ttu-id="06c3d-151">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="06c3d-151">Choose the **OK** button.</span></span>

   ![Cuadro de diálogo Herramientas externas con los valores de campo rellenados.](./media/developer-command-prompt-for-vs/add-external-tool.png)

   <span data-ttu-id="06c3d-153">Se agregará el nuevo elemento de menú y podrá acceder al símbolo del sistema desde el menú Herramientas.</span><span class="sxs-lookup"><span data-stu-id="06c3d-153">The new menu item is added, and you can access the command prompt from the Tools menu.</span></span>

   ![Elemento de menú del símbolo del sistema en Visual Studio](./media/developer-command-prompt-for-vs/command-prompt-vs-menu.png)

## <a name="see-also"></a><span data-ttu-id="06c3d-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06c3d-155">See also</span></span>

- [<span data-ttu-id="06c3d-156">Herramientas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="06c3d-156">.NET Framework Tools</span></span>](index.md)
- [<span data-ttu-id="06c3d-157">Administrar herramientas externas</span><span class="sxs-lookup"><span data-stu-id="06c3d-157">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
- [<span data-ttu-id="06c3d-158">Uso del conjunto de herramientas de Microsoft C++ desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="06c3d-158">Use the Microsoft C++ toolset from the command line</span></span>](/cpp/build/building-on-the-command-line)

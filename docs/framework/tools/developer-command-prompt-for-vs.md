---
title: "Símbolo del sistema para desarrolladores de Visual Studio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8bd7baec77e6e776f93a2a13156d66c1199f918
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="b7c94-102">Símbolo del sistema para desarrolladores de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b7c94-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="b7c94-103">El símbolo del sistema para desarrolladores de Visual Studio establece automáticamente las variables de entorno que permiten usar fácilmente las herramientas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7c94-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="b7c94-104">El símbolo del sistema para desarrolladores se instala con la edición completa o la edición Community de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7c94-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="b7c94-105">No se instala con las versiones Express de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7c94-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="b7c94-106">Buscar el símbolo del sistema en el equipo</span><span class="sxs-lookup"><span data-stu-id="b7c94-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="b7c94-107">Quizás vea varios símbolos del sistema, dependiendo de la versión de Visual Studio y de los SDK adicionales que haya instalado.</span><span class="sxs-lookup"><span data-stu-id="b7c94-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="b7c94-108">Por ejemplo, las versiones de 64 bits de Visual Studio proporcionan los símbolos del sistema de 32 y de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b7c94-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="b7c94-109">(Las versiones de 32 y 64 bits de la mayoría de las herramientas son idénticas; sin embargo, algunas herramientas realizan cambios específicos para los entornos de 32 o 64 bits). Si los pasos siguientes no funcionan, puede probar los indicados en [Buscar manualmente los archivos en la máquina](#alternative) o [Ejecutar el símbolo del sistema desde Visual Studio](#visualstudio).</span><span class="sxs-lookup"><span data-stu-id="b7c94-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="b7c94-110">**En Windows 10**</span><span class="sxs-lookup"><span data-stu-id="b7c94-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="b7c94-111">Abra el menú **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="b7c94-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="b7c94-112">En el menú **Inicio**, escriba `dev`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="b7c94-113">Esto mostrará una lista de las aplicaciones instaladas que coinciden con el patrón de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b7c94-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="b7c94-114">Si busca un símbolo del sistema diferente, pruebe a escribir otro término de búsqueda, como `prompt`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="b7c94-115">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="b7c94-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="b7c94-116">**En Windows 8.1**</span><span class="sxs-lookup"><span data-stu-id="b7c94-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="b7c94-117">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="b7c94-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="b7c94-118">En la pantalla **Inicio**, presione `CTRL + TAB` para abrir la lista **Aplicaciones** y escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="b7c94-119">Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="b7c94-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="b7c94-120">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="b7c94-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="b7c94-121">**En Windows 8**</span><span class="sxs-lookup"><span data-stu-id="b7c94-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="b7c94-122">Vaya a la pantalla **Inicio** presionando, por ejemplo, la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") del teclado.</span><span class="sxs-lookup"><span data-stu-id="b7c94-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="b7c94-123">En la pantalla **Inicio**, presione la tecla del logotipo de Windows ![logotipo de Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="b7c94-124">Elija el icono **Vista Aplicaciones** en la parte inferior de la pantalla y después escriba `V`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="b7c94-125">Esto mostrará una lista que incluye los símbolos del sistema de Visual Studio instalados.</span><span class="sxs-lookup"><span data-stu-id="b7c94-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="b7c94-126">Elija el **Símbolo del sistema para desarrolladores** (o el símbolo del sistema que quiera usar).</span><span class="sxs-lookup"><span data-stu-id="b7c94-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="b7c94-127">**En Windows 7**</span><span class="sxs-lookup"><span data-stu-id="b7c94-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="b7c94-128">Elija **Inicio**, expanda **Todos los programas** y luego, **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b7c94-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="b7c94-129">Según la versión de Visual Studio que tenga instalada, elija **Visual Studio Tools**, **Visual Studio Command Prompt** o el símbolo del sistema que quiera usar.</span><span class="sxs-lookup"><span data-stu-id="b7c94-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="b7c94-130">Si tiene [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) o [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) instalado, puede ver otros símbolos del sistema para las arquitecturas ARM, x86 o x64.</span><span class="sxs-lookup"><span data-stu-id="b7c94-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="b7c94-131">Consulte la documentación de cada herramienta para conocer la versión del símbolo del sistema que debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="b7c94-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="b7c94-132">Buscar manualmente los archivos en el equipo</span><span class="sxs-lookup"><span data-stu-id="b7c94-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="b7c94-133">Normalmente, los accesos directos de los símbolos del sistema que haya instalado se colocan en la carpeta **Menú Inicio** para Visual Studio; por ejemplo, en C:\ProgramData\Microsoft\Windows\Menú Inicio\Programas\Visual Studio 2015\Visual Studio Tools.</span><span class="sxs-lookup"><span data-stu-id="b7c94-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="b7c94-134">Pero si por alguna razón, la búsqueda del símbolo del sistema no muestra los resultados esperados, puede intentar buscar manualmente el acceso directo en el equipo para poder usarlo.</span><span class="sxs-lookup"><span data-stu-id="b7c94-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="b7c94-135">Pruebe a buscar el nombre del archivo de símbolo del sistema; por ejemplo, VsDevCmd.bat o vaya a la carpeta de herramientas; por ejemplo, C:\Program Files (x 86) \Microsoft Visual Studio 14.0\Common7\Tools (la ruta de acceso cambia según la versión de Visual Studio y la ubicación de instalación).</span><span class="sxs-lookup"><span data-stu-id="b7c94-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="b7c94-136">Ejecutar el símbolo del sistema desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b7c94-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="b7c94-137">Para un acceso más sencillo, puede agregar el símbolo del sistema para desarrolladores de Visual Studio o cualquier otro símbolo del sistema al menú Herramientas de Visual Studio con tan solo agregarlo a la lista de herramientas externas.</span><span class="sxs-lookup"><span data-stu-id="b7c94-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="b7c94-138">Haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7c94-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="b7c94-139">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7c94-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b7c94-140">Seleccione el menú **Herramientas** y elija **Herramientas externas...**.</span><span class="sxs-lookup"><span data-stu-id="b7c94-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="b7c94-141">En el cuadro de diálogo **Herramientas externas**, elija el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7c94-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="b7c94-142">Aparecerá una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="b7c94-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="b7c94-143">Escriba el **Título** correspondiente al nuevo elemento de menú (por ejemplo, `Command Prompt`).</span><span class="sxs-lookup"><span data-stu-id="b7c94-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="b7c94-144">Indique en el campo **Comando** el archivo que quiere iniciar como, por ejemplo, `%comspec%` o `C:\Windows\System32\cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="b7c94-145">En el campo **Argumentos** indique dónde se encuentra el símbolo del sistema específico que quiere usar como, por ejemplo, `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (esto iniciará el símbolo del sistema para desarrolladores instalado con [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b7c94-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="b7c94-146">Es necesario cambiar este valor según la ubicación de instalación y la versión de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7c94-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="b7c94-147">Elija un valor para el campo **Directorio inicial** (por ejemplo, **Directorio del proyecto**).</span><span class="sxs-lookup"><span data-stu-id="b7c94-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="b7c94-148">Elija el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="b7c94-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="b7c94-149">De este modo, se agregará el nuevo elemento de menú y ya podrá acceder al símbolo del sistema desde el menú **Herramientas**.</span><span class="sxs-lookup"><span data-stu-id="b7c94-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c94-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7c94-150">See Also</span></span>  
 [<span data-ttu-id="b7c94-151">Herramientas</span><span class="sxs-lookup"><span data-stu-id="b7c94-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="b7c94-152">Administrar herramientas externas</span><span class="sxs-lookup"><span data-stu-id="b7c94-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)

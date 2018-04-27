---
title: 'Cómo: Invocar al compilador de la línea de comandos (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f1ccf08ba58fa6af60bd8ffd7cba79b205dc0f3d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="52ad8-102">Cómo: Invocar al compilador de la línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52ad8-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="52ad8-103">Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo de MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="52ad8-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="52ad8-104">Si compila desde la línea de comandos de Windows de manera predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="52ad8-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="52ad8-105">Para invalidar este comportamiento predeterminado, puede utilizar el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] símbolo o modificar la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="52ad8-105">To override this default behavior, you can either use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt, or modify the PATH environment variable.</span></span> <span data-ttu-id="52ad8-106">Ambos permiten compilar desde cualquier directorio escribiendo simplemente el nombre del compilador.</span><span class="sxs-lookup"><span data-stu-id="52ad8-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a><span data-ttu-id="52ad8-107">Para invocar al compilador mediante el símbolo del sistema de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52ad8-107">To invoke the compiler using the Visual Studio Command Prompt</span></span>  
  
1.  <span data-ttu-id="52ad8-108">Abra la carpeta de programas de Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52ad8-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="52ad8-109">Puede usar el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] línea de comandos para tener acceso al compilador desde cualquier directorio en su equipo, si está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52ad8-109">You can use the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="52ad8-110">Invocar el [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="52ad8-110">Invoke the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Command Prompt.</span></span>  
  
4.  <span data-ttu-id="52ad8-111">En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="52ad8-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="52ad8-112">Por ejemplo, si almacena el código fuente en un directorio denominado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="52ad8-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="52ad8-113">Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="52ad8-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="52ad8-114">Para establecer la variable de entorno PATH en el compilador de la línea de comandos de Windows</span><span class="sxs-lookup"><span data-stu-id="52ad8-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="52ad8-115">Usar la característica de búsqueda de Windows para buscar Vbc.exe en el disco local.</span><span class="sxs-lookup"><span data-stu-id="52ad8-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="52ad8-116">El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y la versión de "Instalado .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="52ad8-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="52ad8-117">Si tiene más de una versión de ".NET Framework" instalado, debe determinar qué versión debe utilizar (normalmente, la versión más reciente).</span><span class="sxs-lookup"><span data-stu-id="52ad8-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="52ad8-118">Desde el **iniciar** menú, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="52ad8-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="52ad8-119">Haga clic en el **avanzadas** ficha y, a continuación, haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="52ad8-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="52ad8-120">En el **System** panel variables, seleccione **ruta de acceso** en la lista y haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="52ad8-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="52ad8-121">En el **sistema editar** cuadro de diálogo Variable, mover el punto de inserción al final de la cadena en el **valor de la Variable** campo y escriba un punto y coma (;) seguido por el nombre de directorio completo se encuentra en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="52ad8-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="52ad8-122">Haga clic en **Aceptar** para confirmar los cambios y cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="52ad8-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="52ad8-123">Después de cambiar la variable de entorno PATH, podrá ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.</span><span class="sxs-lookup"><span data-stu-id="52ad8-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="52ad8-124">Para invocar al compilador mediante el símbolo del sistema de Windows</span><span class="sxs-lookup"><span data-stu-id="52ad8-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="52ad8-125">Desde el **iniciar** menú, haga clic en el **Accesorios** carpeta y, a continuación, abra el **símbolo del sistema de Windows**.</span><span class="sxs-lookup"><span data-stu-id="52ad8-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="52ad8-126">En la línea de comandos, escriba `vbc.exe` *nombreArchivoOrigen* y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="52ad8-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="52ad8-127">Por ejemplo, si almacena el código fuente en un directorio denominado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="52ad8-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="52ad8-128">Si el directorio contiene un archivo de origen denominado `Source.vb`, puede compilarlo escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="52ad8-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ad8-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ad8-129">See Also</span></span>  
 [<span data-ttu-id="52ad8-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="52ad8-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="52ad8-131">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="52ad8-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

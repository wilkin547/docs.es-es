---
title: Filtrar Invocar el compilador de línea de comandos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 78bf5b1f19db3a4f39e263cfd71283f0f7718631
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817193"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="123e9-102">Filtrar Invocar el compilador de línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="123e9-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>
<span data-ttu-id="123e9-103">Puede invocar el compilador de línea de comandos escribiendo el nombre de su archivo ejecutable en la línea de comandos, también conocido como el símbolo de MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="123e9-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="123e9-104">Si compila desde la línea de comandos de Windows de forma predeterminada, debe escribir la ruta de acceso completa al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="123e9-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="123e9-105">Para invalidar este comportamiento predeterminado, puede utilizar el símbolo del sistema para desarrolladores de Visual Studio o modifique la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="123e9-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="123e9-106">Ambos permiten compilar desde cualquier directorio escribiendo simplemente el nombre del compilador.</span><span class="sxs-lookup"><span data-stu-id="123e9-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="123e9-107">Para invocar al compilador con el símbolo del sistema para desarrolladores para Visual Studio</span><span class="sxs-lookup"><span data-stu-id="123e9-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>  
  
1.  <span data-ttu-id="123e9-108">Abra la carpeta del programa de Visual Studio Tools en el grupo de programas de Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="123e9-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>  
  
2.  <span data-ttu-id="123e9-109">Puede utilizar el símbolo del sistema para desarrolladores para Visual Studio para tener acceso al compilador desde cualquier directorio del equipo, si está instalado Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="123e9-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>  
  
3.  <span data-ttu-id="123e9-110">Invocar el símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="123e9-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>  
  
4.  <span data-ttu-id="123e9-111">En la línea de comandos, escriba `vbc.exe` *sourceFileName* y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="123e9-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="123e9-112">Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="123e9-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="123e9-113">Si el directorio contiene un archivo de origen denominado `Source.vb`, compilarlo escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="123e9-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="123e9-114">Para establecer la variable de entorno PATH en el compilador para el símbolo del sistema de Windows</span><span class="sxs-lookup"><span data-stu-id="123e9-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="123e9-115">Usar la característica de Windows Search para buscar Vbc.exe en el disco local.</span><span class="sxs-lookup"><span data-stu-id="123e9-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>  
  
     <span data-ttu-id="123e9-116">El nombre exacto del directorio donde se encuentra el compilador depende de la ubicación del directorio de Windows y la versión de "Instalado .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="123e9-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="123e9-117">Si tiene más de una versión de ".NET Framework" instalada, debe determinar qué versión debe utilizar (normalmente, la versión más reciente).</span><span class="sxs-lookup"><span data-stu-id="123e9-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>  
  
2.  <span data-ttu-id="123e9-118">Desde su **iniciar** menú, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="123e9-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="123e9-119">Haga clic en el **avanzadas** pestaña y, a continuación, haga clic en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="123e9-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>  
  
4.  <span data-ttu-id="123e9-120">En el **sistema** panel variables, seleccione **ruta** en la lista y haga clic en **editar**.</span><span class="sxs-lookup"><span data-stu-id="123e9-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>  
  
5.  <span data-ttu-id="123e9-121">En el **sistema editar** cuadro de diálogo Variable, mover el punto de inserción al final de la cadena en el **valor de la Variable** campo y escriba un punto y coma (;) seguido del nombre de directorio completa se encuentra en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="123e9-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>  
  
6.  <span data-ttu-id="123e9-122">Haga clic en **Aceptar** para confirmar los cambios y cerrar los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="123e9-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>  
  
     <span data-ttu-id="123e9-123">Después de cambiar la variable de entorno PATH, puede ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.</span><span class="sxs-lookup"><span data-stu-id="123e9-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="123e9-124">Para invocar al compilador mediante el símbolo del sistema de Windows</span><span class="sxs-lookup"><span data-stu-id="123e9-124">To invoke the compiler using the Windows Command Prompt</span></span>  
  
1.  <span data-ttu-id="123e9-125">Desde el **iniciar** menú, haga clic en el **Accesorios** carpeta y, a continuación, abra el **símbolo del sistema Windows**.</span><span class="sxs-lookup"><span data-stu-id="123e9-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="123e9-126">En la línea de comandos, escriba `vbc.exe` *sourceFileName* y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="123e9-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>  
  
     <span data-ttu-id="123e9-127">Por ejemplo, si almacena el código fuente en un directorio llamado `SourceFiles`, abriría el símbolo del sistema y el tipo `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="123e9-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="123e9-128">Si el directorio contiene un archivo de origen denominado `Source.vb`, compilarlo escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="123e9-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123e9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="123e9-129">See also</span></span>

- [<span data-ttu-id="123e9-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="123e9-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="123e9-131">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="123e9-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

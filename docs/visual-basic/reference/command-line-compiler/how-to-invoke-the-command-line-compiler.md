---
title: Procedimiento Invocación del compilador de la línea de comandos
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344256"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a><span data-ttu-id="6f742-102">Procedimiento Invocación del compilador de la línea de comandos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f742-102">How to: Invoke the Command-Line Compiler (Visual Basic)</span></span>

<span data-ttu-id="6f742-103">Para invocar el compilador de la línea de comandos, puede escribir el nombre del archivo ejecutable correspondiente en la línea de comandos, también conocida como símbolo del sistema de MS-DOS.</span><span class="sxs-lookup"><span data-stu-id="6f742-103">You can invoke the command-line compiler by typing the name of its executable file into the command line, also known as the MS-DOS prompt.</span></span> <span data-ttu-id="6f742-104">Si se compila desde el símbolo del sistema de Windows predeterminado, es necesario escribir la ruta de acceso completa al archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="6f742-104">If you compile from the default Windows Command Prompt, you must type the fully qualified path to the executable file.</span></span> <span data-ttu-id="6f742-105">Para invalidar este comportamiento predeterminado, se puede usar el Símbolo del sistema para desarrolladores de Visual Studio, o bien modificar la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="6f742-105">To override this default behavior, you can either use the Developer Command Prompt for Visual Studio, or modify the PATH environment variable.</span></span> <span data-ttu-id="6f742-106">Ambos métodos permiten compilar desde cualquier directorio, simplemente escribiendo el nombre del compilador.</span><span class="sxs-lookup"><span data-stu-id="6f742-106">Both allow you to compile from any directory by simply typing the compiler name.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a><span data-ttu-id="6f742-107">Para invocar el compilador usando el Símbolo del sistema para desarrolladores de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f742-107">To invoke the compiler using the Developer Command Prompt for Visual Studio</span></span>

1. <span data-ttu-id="6f742-108">Abra la carpeta del programa Visual Studio Tools dentro del grupo de programas de Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f742-108">Open the Visual Studio Tools program folder within the Microsoft Visual Studio program group.</span></span>

2. <span data-ttu-id="6f742-109">Si Visual Studio está instalado, se puede usar el Símbolo del sistema para desarrolladores de Visual Studio para acceder al compilador desde cualquier directorio del equipo.</span><span class="sxs-lookup"><span data-stu-id="6f742-109">You can use the Developer Command Prompt for Visual Studio to access the compiler from any directory on your machine, if Visual Studio is installed.</span></span>

3. <span data-ttu-id="6f742-110">Invoque el Símbolo del sistema para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6f742-110">Invoke the Developer Command Prompt for Visual Studio.</span></span>

4. <span data-ttu-id="6f742-111">En la línea de comandos, escriba `vbc.exe` *sourceFileName* y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="6f742-111">At the command line, type `vbc.exe` *sourceFileName* and then press ENTER.</span></span>

    <span data-ttu-id="6f742-112">Por ejemplo, si tiene almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="6f742-112">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="6f742-113">Si el directorio contuviera un archivo de código fuente denominado `Source.vb`, se podría compilar escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="6f742-113">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a><span data-ttu-id="6f742-114">Para establecer la variable de entorno PATH en el compilador del símbolo del sistema de Windows</span><span class="sxs-lookup"><span data-stu-id="6f742-114">To set the PATH environment variable to the compiler for the Windows Command Prompt</span></span>

1. <span data-ttu-id="6f742-115">Use la característica Windows Search para encontrar Vbc.exe en el disco local.</span><span class="sxs-lookup"><span data-stu-id="6f742-115">Use the Windows Search feature to find Vbc.exe on your local disk.</span></span>

    <span data-ttu-id="6f742-116">El nombre exacto del directorio donde está el compilador depende de la ubicación del directorio de Windows y de la versión de .NET Framework que haya instalada.</span><span class="sxs-lookup"><span data-stu-id="6f742-116">The exact name of the directory where the compiler is located depends on the location of the Windows directory and the version of the ".NET Framework" installed.</span></span> <span data-ttu-id="6f742-117">Si hay más de una versión de .NET Framework instalada, hay que determinar cuál usar (normalmente, la última).</span><span class="sxs-lookup"><span data-stu-id="6f742-117">If you have more than one version of the ".NET Framework" installed, you must determine which version to use (typically the latest version).</span></span>

2. <span data-ttu-id="6f742-118">En el menú **Inicio**, haga clic con el botón derecho en **Mi PC** y, después, haga clic en **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6f742-118">From your **Start** Menu, right-click **My Computer**, and then click **Properties** from the shortcut menu.</span></span>

3. <span data-ttu-id="6f742-119">Haga clic en la pestaña **Avanzadas** y, después, en **Variables de entorno**.</span><span class="sxs-lookup"><span data-stu-id="6f742-119">Click the **Advanced** tab, and then click **Environment Variables**.</span></span>

4. <span data-ttu-id="6f742-120">En el panel **Variables del sistema**, seleccione **Path** de la lista y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6f742-120">In the **System** variables pane, select **Path** from the list and click **Edit**.</span></span>

5. <span data-ttu-id="6f742-121">En el cuadro de diálogo **Editar la variable del sistema**, mueva el punto de inserción al final de la cadena en el campo **Valor de la variable** y escriba un punto y coma (;) seguido del nombre de directorio completo del paso 1.</span><span class="sxs-lookup"><span data-stu-id="6f742-121">In the **Edit System** Variable dialog box, move the insertion point to the end of the string in the **Variable Value** field and type a semicolon (;) followed by the full directory name found in Step 1.</span></span>

6. <span data-ttu-id="6f742-122">Haga clic en **Aceptar** para confirmar las modificaciones y cierre los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6f742-122">Click **OK** to confirm your edits and close the dialog boxes.</span></span>

     <span data-ttu-id="6f742-123">Después de cambiar la variable de entorno PATH, puede ejecutar el compilador de Visual Basic en el símbolo del sistema de Windows desde cualquier directorio del equipo.</span><span class="sxs-lookup"><span data-stu-id="6f742-123">After you change the PATH environment variable, you can run the Visual Basic compiler at the Windows Command Prompt from any directory on the computer.</span></span>

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a><span data-ttu-id="6f742-124">Para invocar el compilador con el símbolo del sistema de Windows</span><span class="sxs-lookup"><span data-stu-id="6f742-124">To invoke the compiler using the Windows Command Prompt</span></span>

1. <span data-ttu-id="6f742-125">En el menú **Inicio**, haga clic en la carpeta **Accesorios** y, después, abra **Símbolo del sistema de Windows**.</span><span class="sxs-lookup"><span data-stu-id="6f742-125">From the **Start** menu, click on the **Accessories** folder, and then open the **Windows Command Prompt**.</span></span>

2. <span data-ttu-id="6f742-126">En la línea de comandos, escriba `vbc.exe`*sourceFileName* y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="6f742-126">At the command line, type `vbc.exe`*sourceFileName* and then press ENTER.</span></span>

     <span data-ttu-id="6f742-127">Por ejemplo, si tiene almacenado el código fuente en un directorio llamado `SourceFiles`, abra el símbolo del sistema y escriba `cd SourceFiles` para cambiar a ese directorio.</span><span class="sxs-lookup"><span data-stu-id="6f742-127">For example, if you stored your source code in a directory called `SourceFiles`, you would open the Command Prompt and type `cd SourceFiles` to change to that directory.</span></span> <span data-ttu-id="6f742-128">Si el directorio contuviera un archivo de código fuente denominado `Source.vb`, se podría compilar escribiendo `vbc.exe Source.vb`.</span><span class="sxs-lookup"><span data-stu-id="6f742-128">If the directory contained a source file named `Source.vb`, you could compile it by typing `vbc.exe Source.vb`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f742-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f742-129">See also</span></span>

- [<span data-ttu-id="6f742-130">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6f742-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6f742-131">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="6f742-131">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)

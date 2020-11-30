---
description: Compilar la línea de comandos con csc.exe
title: Compilar la línea de comandos con csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: 9ffd164602862fce7f5e4f0982d3eda7cb403e60
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125935"
---
# <a name="command-line-build-with-cscexe"></a><span data-ttu-id="c5416-103">Compilar la línea de comandos con csc.exe</span><span class="sxs-lookup"><span data-stu-id="c5416-103">Command-line build with csc.exe</span></span>

<span data-ttu-id="c5416-104">Puede invocar el compilador de C# escribiendo el nombre de su archivo ejecutable (*csc.exe*) en un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5416-104">You can invoke the C# compiler by typing the name of its executable file (*csc.exe*) at a command prompt.</span></span>

<span data-ttu-id="c5416-105">Si usa la ventana **Símbolo del sistema para desarrolladores de Visual Studio**, todas las variables de entorno necesarias se establecen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c5416-105">If you use the **Developer Command Prompt for Visual Studio** window, all the necessary environment variables are set for you.</span></span> <span data-ttu-id="c5416-106">Para obtener información sobre cómo acceder a esta herramienta, vea el tema [Símbolo del sistema para desarrolladores de Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="c5416-106">For information on how to access this tool, see the [Developer Command Prompt for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) topic.</span></span>

<span data-ttu-id="c5416-107">Si usa una ventana de símbolo del sistema estándar, debe ajustar la ruta de acceso antes de poder invocar *csc.exe* desde cualquier subdirectorio del equipo.</span><span class="sxs-lookup"><span data-stu-id="c5416-107">If you use a standard Command Prompt window, you must adjust your path before you can invoke *csc.exe* from any subdirectory on your computer.</span></span> <span data-ttu-id="c5416-108">También debe ejecutar *VsDevCmd.bat* para establecer las variables de entorno adecuadas para admitir las compilaciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c5416-108">You also must run *VsDevCmd.bat* to set the appropriate environment variables to support command-line builds.</span></span> <span data-ttu-id="c5416-109">Para obtener más información sobre *VsDevCmd.bat*, incluidas las instrucciones sobre cómo buscarlo y ejecutarlo, vea [Establecimiento de variables de entorno para la línea de comandos de Visual Studio](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="c5416-109">For more information about *VsDevCmd.bat*, including instructions for how to find and run it, see [How to set environment variables for the Visual Studio Command Line](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

<span data-ttu-id="c5416-110">Si trabaja en un equipo que solo tiene el kit de desarrollo de software (SDK) de Windows, puede usar el compilador de C# en el **símbolo del sistema de SDK**, que puede abrir desde la opción de menú **Microsoft .NET Framework SDK**.</span><span class="sxs-lookup"><span data-stu-id="c5416-110">If you're working on a computer that has only the Windows Software Development Kit (SDK), you can use the C# compiler at the **SDK Command Prompt**, which you open from the **Microsoft .NET Framework SDK** menu option.</span></span>

<span data-ttu-id="c5416-111">También puede usar MSBuild para compilar programas de C# mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c5416-111">You can also use MSBuild to build C# programs programmatically.</span></span> <span data-ttu-id="c5416-112">Para obtener más información, vea [MSBuild](/visualstudio/msbuild/msbuild).</span><span class="sxs-lookup"><span data-stu-id="c5416-112">For more information, see [MSBuild](/visualstudio/msbuild/msbuild).</span></span>

<span data-ttu-id="c5416-113">El archivo ejecutable *csc.exe* suele encontrarse en la carpeta Microsoft.NET\Framework\\ *\<Version>* en el directorio *Windows*.</span><span class="sxs-lookup"><span data-stu-id="c5416-113">The *csc.exe* executable file usually is located in the Microsoft.NET\Framework\\*\<Version>* folder under the *Windows* directory.</span></span> <span data-ttu-id="c5416-114">Su ubicación puede variar, según la configuración exacta de un equipo concreto.</span><span class="sxs-lookup"><span data-stu-id="c5416-114">Its location might vary depending on the exact configuration of a particular computer.</span></span> <span data-ttu-id="c5416-115">Si se instala más de una versión de .NET Framework en el equipo, encontrará varias versiones de este archivo.</span><span class="sxs-lookup"><span data-stu-id="c5416-115">If more than one version of the .NET Framework is installed on your computer, you'll find multiple versions of this file.</span></span> <span data-ttu-id="c5416-116">Para obtener más información sobre estas instalaciones, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="c5416-116">For more information about such installations, see [How to: determine which versions of the .NET Framework are installed](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

> [!TIP]
> <span data-ttu-id="c5416-117">Al compilar un proyecto mediante el IDE de Visual Studio, puede mostrar el comando **csc** y las opciones del compilador asociadas en la ventana **Salida**.</span><span class="sxs-lookup"><span data-stu-id="c5416-117">When you build a project by using the Visual Studio IDE, you can display the **csc** command and its associated compiler options in the **Output** window.</span></span> <span data-ttu-id="c5416-118">Para mostrar esta información, siga las instrucciones de [Cómo: Ver, guardar y configurar archivos de registro de compilación](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) para cambiar el nivel de detalle de los datos del registro a **Normal** o **Detallado**.</span><span class="sxs-lookup"><span data-stu-id="c5416-118">To display this information, follow the instructions in [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) to change the verbosity level of the log data to **Normal** or **Detailed**.</span></span> <span data-ttu-id="c5416-119">Una vez recompilado el proyecto, busque **csc** en la ventana **Salida** para localizar la invocación del compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="c5416-119">After you rebuild your project, search the **Output** window for **csc** to find the invocation of the C# compiler.</span></span>

 <span data-ttu-id="c5416-120">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c5416-120">**In this topic**</span></span>

- [<span data-ttu-id="c5416-121">Reglas para la sintaxis de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5416-121">Rules for command-line syntax</span></span>](#rules-for-command-line-syntax-for-the-c-compiler)

- [<span data-ttu-id="c5416-122">Líneas de comandos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5416-122">Sample command lines</span></span>](#sample-command-lines-for-the-c-compiler)

- [<span data-ttu-id="c5416-123">Diferencias entre el resultado del compilador de C++ y el compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c5416-123">Differences between C# compiler and C++ compiler output</span></span>](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a><span data-ttu-id="c5416-124">Reglas para la sintaxis de la línea de comandos para el compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c5416-124">Rules for command-line syntax for the C# compiler</span></span>

<span data-ttu-id="c5416-125">El compilador de C# utiliza las siguientes reglas para interpretar los argumentos empleados en la línea de comandos del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="c5416-125">The C# compiler uses the following rules when it interprets arguments given on the operating system command line:</span></span>

- <span data-ttu-id="c5416-126">Los argumentos van delimitados por espacio en blanco, que puede ser un carácter de espacio o una tabulación.</span><span class="sxs-lookup"><span data-stu-id="c5416-126">Arguments are delimited by white space, which is either a space or a tab.</span></span>

- <span data-ttu-id="c5416-127">El carácter de intercalación (^) no se reconoce como carácter de escape ni como delimitador.</span><span class="sxs-lookup"><span data-stu-id="c5416-127">The caret character (^) is not recognized as an escape character or delimiter.</span></span> <span data-ttu-id="c5416-128">El analizador de la línea de comandos del sistema operativo procesa este carácter antes de pasarlo a la matriz `argv` del programa.</span><span class="sxs-lookup"><span data-stu-id="c5416-128">The character is handled by the command-line parser in the operating system before it's passed to the `argv` array in the program.</span></span>

- <span data-ttu-id="c5416-129">Una cadena entre comillas ("cadena") se interpreta como un solo argumento, sin importar el espacio en blanco que contenga.</span><span class="sxs-lookup"><span data-stu-id="c5416-129">A string enclosed in double quotation marks ("string") is interpreted as a single argument, regardless of white space that is contained within.</span></span> <span data-ttu-id="c5416-130">Se puede incrustar una cadena entre comillas dentro de un argumento.</span><span class="sxs-lookup"><span data-stu-id="c5416-130">A quoted string can be embedded in an argument.</span></span>

- <span data-ttu-id="c5416-131">Unas comillas precedidas por una barra diagonal inversa (\\") se interpretan como un literal de cadena de comillas (").</span><span class="sxs-lookup"><span data-stu-id="c5416-131">A double quotation mark preceded by a backslash (\\") is interpreted as a literal double quotation mark character (").</span></span>

- <span data-ttu-id="c5416-132">Las barras diagonales inversas se interpretan literalmente, a menos que precedan inmediatamente a unas comillas.</span><span class="sxs-lookup"><span data-stu-id="c5416-132">Backslashes are interpreted literally, unless they immediately precede a double quotation mark.</span></span>

- <span data-ttu-id="c5416-133">Si a un número par de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz `argv` por cada par de barras diagonales y se interpretan las comillas como delimitador de cadenas.</span><span class="sxs-lookup"><span data-stu-id="c5416-133">If an even number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is interpreted as a string delimiter.</span></span>

- <span data-ttu-id="c5416-134">Si a un número impar de barras diagonales inversas le siguen unas comillas, se coloca una barra diagonal inversa en la matriz `argv` por cada par de barras diagonales y se interpretan las comillas como un carácter de "escape" gracias a la barra diagonal restante.</span><span class="sxs-lookup"><span data-stu-id="c5416-134">If an odd number of backslashes is followed by a double quotation mark, one backslash is put in the `argv` array for every pair of backslashes, and the double quotation mark is "escaped" by the remaining backslash.</span></span> <span data-ttu-id="c5416-135">Esto hace que se agregue un literal de comillas dobles (") a `argv`.</span><span class="sxs-lookup"><span data-stu-id="c5416-135">This causes a literal double quotation mark (") to be added in `argv`.</span></span>

## <a name="sample-command-lines-for-the-c-compiler"></a><span data-ttu-id="c5416-136">Líneas de comandos de ejemplo para el compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c5416-136">Sample command lines for the C# compiler</span></span>

- <span data-ttu-id="c5416-137">Compila *File.cs* y genera *File.exe*:</span><span class="sxs-lookup"><span data-stu-id="c5416-137">Compiles *File.cs* producing *File.exe*:</span></span>

  ```console
  csc File.cs
  ```

- <span data-ttu-id="c5416-138">Compila *File.cs* y genera *File.dll*:</span><span class="sxs-lookup"><span data-stu-id="c5416-138">Compiles *File.cs* producing *File.dll*:</span></span>

  ```console
  csc -target:library File.cs
  ```

- <span data-ttu-id="c5416-139">Compila *File.cs* y crea *My.exe*:</span><span class="sxs-lookup"><span data-stu-id="c5416-139">Compiles *File.cs* and creates *My.exe*:</span></span>

  ```console
  csc -out:My.exe File.cs
  ```

- <span data-ttu-id="c5416-140">Compila todos los archivos de C# del directorio actual, con optimizaciones habilitadas y define el símbolo DEBUG.</span><span class="sxs-lookup"><span data-stu-id="c5416-140">Compiles all the C# files in the current directory with optimizations enabled and defines the DEBUG symbol.</span></span> <span data-ttu-id="c5416-141">El resultado es *File2.exe*:</span><span class="sxs-lookup"><span data-stu-id="c5416-141">The output is *File2.exe*:</span></span>

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- <span data-ttu-id="c5416-142">Compila todos los archivos de C# del directorio actual, generando una versión de depuración de *File2.dll*.</span><span class="sxs-lookup"><span data-stu-id="c5416-142">Compiles all the C# files in the current directory producing a debug version of *File2.dll*.</span></span> <span data-ttu-id="c5416-143">No se muestra logotipo ni ningún tipo de advertencias:</span><span class="sxs-lookup"><span data-stu-id="c5416-143">No logo and no warnings are displayed:</span></span>

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- <span data-ttu-id="c5416-144">Compila todos los archivos de C# del directorio actual en *Something.xyz* (un DLL):</span><span class="sxs-lookup"><span data-stu-id="c5416-144">Compiles all the C# files in the current directory to *Something.xyz* (a DLL):</span></span>

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a><span data-ttu-id="c5416-145">Diferencias entre el resultado del compilador de C++ y el compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c5416-145">Differences between C# compiler and C++ compiler output</span></span>

<span data-ttu-id="c5416-146">No se crean archivos objeto ( *.obj*) como resultado de invocar el compilador de C#; se crean directamente archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="c5416-146">There are no object (*.obj*) files created as a result of invoking the C# compiler; output files are created directly.</span></span> <span data-ttu-id="c5416-147">Como consecuencia de ello, el compilador de C# no requiere un vinculador.</span><span class="sxs-lookup"><span data-stu-id="c5416-147">As a result of this, the C# compiler does not need a linker.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5416-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5416-148">See also</span></span>

- [<span data-ttu-id="c5416-149">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c5416-149">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c5416-150">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="c5416-150">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
- [<span data-ttu-id="c5416-151">Opciones del compilador de C#, por categoría</span><span class="sxs-lookup"><span data-stu-id="c5416-151">C# Compiler Options Listed by Category</span></span>](./listed-by-category.md)
- [<span data-ttu-id="c5416-152">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5416-152">Main() and Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="c5416-153">Argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5416-153">Command-Line Arguments</span></span>](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [<span data-ttu-id="c5416-154">Procedimiento para mostrar argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c5416-154">How to display command-line arguments</span></span>](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [<span data-ttu-id="c5416-155">Valores devueltos de Main()</span><span class="sxs-lookup"><span data-stu-id="c5416-155">Main() Return Values</span></span>](../../programming-guide/main-and-command-args/main-return-values.md)

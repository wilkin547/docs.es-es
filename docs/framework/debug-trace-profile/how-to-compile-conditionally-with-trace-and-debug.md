---
title: 'Cómo: Realizar compilación condicional con Trace y Debug'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trace compiler options
- trace statements
- compiling source code, trace statements
- tracing [.NET Framework], enabling or disabling
- tracing [.NET Framework], compiling conditionally
- TRACE directive
- conditional compilation, tracing code
ms.assetid: 56d051c3-012c-42c1-9a58-7270edc624aa
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5e590888a56ed4c325e89eb828349f4f289815cd
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-compile-conditionally-with-trace-and-debug"></a><span data-ttu-id="31731-102">Cómo: Realizar compilación condicional con Trace y Debug</span><span class="sxs-lookup"><span data-stu-id="31731-102">How to: Compile Conditionally with Trace and Debug</span></span>
<span data-ttu-id="31731-103">Al depurar una aplicación durante el desarrollo, el seguimiento y la salida de depuración aparecen en la ventana Salida de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="31731-103">While you are debugging an application during development, both your tracing and debugging output go to the Output window in Visual Studio.</span></span> <span data-ttu-id="31731-104">Pero para incluir características de seguimiento en una aplicación implementada, tendrá que compilar las aplicaciones instrumentadas con la directiva de compilador **TRACE** habilitada.</span><span class="sxs-lookup"><span data-stu-id="31731-104">However, to include tracing features in a deployed application, you must compile your instrumented applications with the **TRACE** compiler directive enabled.</span></span> <span data-ttu-id="31731-105">Esto permite que el código de seguimiento se compile en la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31731-105">This allows tracing code to be compiled into the release version of your application.</span></span> <span data-ttu-id="31731-106">Si no habilita la directiva **TRACE**, se ignorará todo el código de seguimiento durante la compilación y no se incluirá en el código ejecutable que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="31731-106">If you do not enable the **TRACE** directive, all tracing code is ignored during compilation and is not included in the executable code that you will deploy.</span></span>  
  
 <span data-ttu-id="31731-107">Los métodos de depuración y seguimiento tienen atributos condicionales asociados.</span><span class="sxs-lookup"><span data-stu-id="31731-107">Both the tracing and debugging methods have associated conditional attributes.</span></span> <span data-ttu-id="31731-108">Por ejemplo, si el atributo condicional para el seguimiento es **true**, todas las instrucciones de seguimiento se incluyen dentro de un ensamblado (un archivo .exe o .dll compilado); si el atributo condicional de **Trace** es **false**, no se incluyen las instrucciones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31731-108">For example, if the conditional attribute for tracing is **true**, all trace statements are included within an assembly (a compiled .exe file or .dll); if the **Trace** conditional attribute is **false**, the trace statements are not included.</span></span>  
  
 <span data-ttu-id="31731-109">Para una compilación puede tener activados ambos, uno o ninguno de los atributos condicionales **Trace** o **Debug**.</span><span class="sxs-lookup"><span data-stu-id="31731-109">You can have either the **Trace** or **Debug** conditional attribute turned on for a build, or both, or neither.</span></span> <span data-ttu-id="31731-110">Por tanto, hay cuatro tipos de compilación: **Debug**, **Trace**, ambos o ninguno.</span><span class="sxs-lookup"><span data-stu-id="31731-110">Thus, there are four types of build: **Debug**, **Trace**, both, or neither.</span></span> <span data-ttu-id="31731-111">Algunas compilaciones de versión para la implementación de producción pueden no contener ninguno; la mayoría de las compilaciones de depuración contienen ambos.</span><span class="sxs-lookup"><span data-stu-id="31731-111">Some release builds for production deployment might contain neither; most debugging builds contain both.</span></span>  
  
 <span data-ttu-id="31731-112">La configuración del compilador para la aplicación se puede configurar de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="31731-112">You can specify the compiler settings for your application in several ways:</span></span>  
  
-   <span data-ttu-id="31731-113">Las páginas de propiedades</span><span class="sxs-lookup"><span data-stu-id="31731-113">The property pages</span></span>  
  
-   <span data-ttu-id="31731-114">La línea de comandos</span><span class="sxs-lookup"><span data-stu-id="31731-114">The command line</span></span>  
  
-   <span data-ttu-id="31731-115">**#CONST** (para Visual Basic) y **#define** (para C#)</span><span class="sxs-lookup"><span data-stu-id="31731-115">**#CONST** (for Visual Basic) and **#define** (for C#)</span></span>  
  
### <a name="to-change-compile-settings-from-the-property-pages-dialog-box"></a><span data-ttu-id="31731-116">Para cambiar la configuración de compilación desde el cuadro de diálogo de páginas de propiedades</span><span class="sxs-lookup"><span data-stu-id="31731-116">To change compile settings from the property pages dialog box</span></span>  
  
1.  <span data-ttu-id="31731-117">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="31731-117">Right-click the project node in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="31731-118">Seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="31731-118">Choose **Properties** from the shortcut menu.</span></span>  
  
    -   <span data-ttu-id="31731-119">En Visual Basic, haga clic en la pestaña **Compilar** en el panel izquierdo de la página de propiedades. Después, haga clic en el botón **Opciones de compilación avanzadas** para mostrar el cuadro de diálogo **Configuración de compilador avanzada**.</span><span class="sxs-lookup"><span data-stu-id="31731-119">In Visual Basic, click the **Compile** tab in the left pane of the property page, then click the **Advanced Compile Options** button to display the **Advanced Compiler Settings** dialog box.</span></span> <span data-ttu-id="31731-120">Seleccione las casillas correspondientes a los valores de configuración del compilador que desee habilitar.</span><span class="sxs-lookup"><span data-stu-id="31731-120">Select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="31731-121">Desactive las casillas de los valores de configuración que desee deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="31731-121">Clear the check boxes for settings you want to disable.</span></span>  
  
    -   <span data-ttu-id="31731-122">En C#, haga clic en la pestaña **Compilar** en el panel izquierdo de la página de propiedades y, después, active las casillas correspondientes a los valores de configuración del compilador que quiere habilitar.</span><span class="sxs-lookup"><span data-stu-id="31731-122">In C#, click the **Build** tab in the left pane of the property page, then select the check boxes for the compiler settings you want to enable.</span></span> <span data-ttu-id="31731-123">Desactive las casillas de los valores de configuración que desee deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="31731-123">Clear the check boxes for settings you want to disable.</span></span>  
  
### <a name="to-compile-instrumented-code-using-the-command-line"></a><span data-ttu-id="31731-124">Para compilar código instrumentado desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="31731-124">To compile instrumented code using the command line</span></span>  
  
1.  <span data-ttu-id="31731-125">Establezca un modificador de compilación condicional en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="31731-125">Set a conditional compiler switch on the command line.</span></span> <span data-ttu-id="31731-126">El compilador incluirá código de seguimiento o depuración en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="31731-126">The compiler will include trace or debug code in the executable.</span></span>  
  
     <span data-ttu-id="31731-127">Por ejemplo, la siguiente instrucción del compilador especificada en la línea de comandos incluiría el código de seguimiento en un ejecutable compilado:</span><span class="sxs-lookup"><span data-stu-id="31731-127">For example, the following compiler instruction entered on the command line would include your tracing code in a compiled executable:</span></span>  
  
     <span data-ttu-id="31731-128">En Visual Basic: **vbc-r:System.dll -d: TRACE = TRUE -d: DEBUG = FALSE MiAplicación.vb**</span><span class="sxs-lookup"><span data-stu-id="31731-128">For Visual Basic: **vbc -r:System.dll -d:TRACE=TRUE -d:DEBUG=FALSE MyApplication.vb**</span></span>  
  
     <span data-ttu-id="31731-129">Para C#: **csc-r:System.dll -d: TRACE -d: DEBUG = FALSE MiAplicación.cs**</span><span class="sxs-lookup"><span data-stu-id="31731-129">For C#: **csc -r:System.dll -d:TRACE -d:DEBUG=FALSE MyApplication.cs**</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="31731-130">Para compilar varios archivos de aplicación, deje un espacio en blanco entre los nombres de archivo, por ejemplo, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** o **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span><span class="sxs-lookup"><span data-stu-id="31731-130">To compile more than one application file, leave a blank space between the file names, for example, **MyApplication1.vb MyApplication2.vb MyApplication3.vb** or **MyApplication1.cs MyApplication2.cs MyApplication3.cs**.</span></span>  
  
     <span data-ttu-id="31731-131">El significado de las directivas de compilación condicional usadas en los ejemplos anteriores es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="31731-131">The meaning of the conditional-compilation directives used in the above examples is as follows:</span></span>  
  
    |<span data-ttu-id="31731-132">Directiva</span><span class="sxs-lookup"><span data-stu-id="31731-132">Directive</span></span>|<span data-ttu-id="31731-133">Significado</span><span class="sxs-lookup"><span data-stu-id="31731-133">Meaning</span></span>|  
    |---------------|-------------|  
    |`vbc`|<span data-ttu-id="31731-134">compilador de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31731-134">Visual Basic compiler</span></span>|  
    |`csc`|<span data-ttu-id="31731-135">Compilador de C#</span><span class="sxs-lookup"><span data-stu-id="31731-135">C# compiler</span></span>|  
    |`-r:`|<span data-ttu-id="31731-136">Hace referencia a un ensamblado externo (EXE o DLL)</span><span class="sxs-lookup"><span data-stu-id="31731-136">References an external assembly (EXE or DLL)</span></span>|  
    |`-d:`|<span data-ttu-id="31731-137">Define un símbolo de compilación condicional</span><span class="sxs-lookup"><span data-stu-id="31731-137">Defines a conditional compilation symbol</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="31731-138">TRACE o DEBUG deben escribirse en letras mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="31731-138">You must spell TRACE or DEBUG with uppercase letters.</span></span> <span data-ttu-id="31731-139">Para obtener más información sobre los comandos de compilación condicional, escriba `vbc /?` (para Visual Basic) o `csc /?` (para C#) en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="31731-139">For more information about the conditional compilation commands, enter `vbc /?` (for Visual Basic) or `csc /?` (for C#) at the command prompt.</span></span> <span data-ttu-id="31731-140">Para más información, vea [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (Compilar desde la línea de comandos) (C#) o [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Invocar el compilador de línea de comandos) (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="31731-140">For more information, see [Building from the Command Line](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md) (C#) or [Invoking the Command-Line Compiler](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) (Visual Basic).</span></span>  
  
### <a name="to-perform-conditional-compilation-using-const-or-define"></a><span data-ttu-id="31731-141">Para realizar compilación condicional mediante #CONST o #define</span><span class="sxs-lookup"><span data-stu-id="31731-141">To perform conditional compilation using #CONST or #define</span></span>  
  
1.  <span data-ttu-id="31731-142">Escriba la instrucción apropiada para su lenguaje de programación en la parte superior del archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="31731-142">Type the appropriate statement for your programming language at the top of the source code file.</span></span>  
  
    |<span data-ttu-id="31731-143">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="31731-143">Language</span></span>|<span data-ttu-id="31731-144">Instrucción</span><span class="sxs-lookup"><span data-stu-id="31731-144">Statement</span></span>|<span data-ttu-id="31731-145">Resultado</span><span class="sxs-lookup"><span data-stu-id="31731-145">Result</span></span>|  
    |--------------|---------------|------------|  
    |<span data-ttu-id="31731-146">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="31731-146">**Visual Basic**</span></span>|<span data-ttu-id="31731-147">**#CONST TRACE = true**</span><span class="sxs-lookup"><span data-stu-id="31731-147">**#CONST TRACE = true**</span></span>|<span data-ttu-id="31731-148">Habilita el seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-148">Enables tracing</span></span>|  
    ||<span data-ttu-id="31731-149">**#CONST TRACE = false**</span><span class="sxs-lookup"><span data-stu-id="31731-149">**#CONST TRACE = false**</span></span>|<span data-ttu-id="31731-150">Deshabilita el seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-150">Disables tracing</span></span>|  
    ||<span data-ttu-id="31731-151">**#CONST DEBUG = true**</span><span class="sxs-lookup"><span data-stu-id="31731-151">**#CONST DEBUG = true**</span></span>|<span data-ttu-id="31731-152">Habilita la depuración</span><span class="sxs-lookup"><span data-stu-id="31731-152">Enables debugging</span></span>|  
    ||<span data-ttu-id="31731-153">**#CONST DEBUG = false**</span><span class="sxs-lookup"><span data-stu-id="31731-153">**#CONST DEBUG = false**</span></span>|<span data-ttu-id="31731-154">Deshabilita la depuración</span><span class="sxs-lookup"><span data-stu-id="31731-154">Disables debugging</span></span>|  
    |<span data-ttu-id="31731-155">**C#**</span><span class="sxs-lookup"><span data-stu-id="31731-155">**C#**</span></span>|<span data-ttu-id="31731-156">**#define TRACE**</span><span class="sxs-lookup"><span data-stu-id="31731-156">**#define TRACE**</span></span>|<span data-ttu-id="31731-157">Habilita el seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-157">Enables tracing</span></span>|  
    ||<span data-ttu-id="31731-158">**#undef TRACE**</span><span class="sxs-lookup"><span data-stu-id="31731-158">**#undef TRACE**</span></span>|<span data-ttu-id="31731-159">Deshabilita el seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-159">Disables tracing</span></span>|  
    ||<span data-ttu-id="31731-160">**#define DEBUG**</span><span class="sxs-lookup"><span data-stu-id="31731-160">**#define DEBUG**</span></span>|<span data-ttu-id="31731-161">Habilita la depuración</span><span class="sxs-lookup"><span data-stu-id="31731-161">Enables debugging</span></span>|  
    ||<span data-ttu-id="31731-162">**#undef DEBUG**</span><span class="sxs-lookup"><span data-stu-id="31731-162">**#undef DEBUG**</span></span>|<span data-ttu-id="31731-163">Deshabilita la depuración</span><span class="sxs-lookup"><span data-stu-id="31731-163">Disables debugging</span></span>|  
  
### <a name="to-disable-tracing-or-debugging"></a><span data-ttu-id="31731-164">Para deshabilitar el seguimiento o la depuración</span><span class="sxs-lookup"><span data-stu-id="31731-164">To disable tracing or debugging</span></span>  
  
<span data-ttu-id="31731-165">Elimine la directiva de compilador del código fuente.</span><span class="sxs-lookup"><span data-stu-id="31731-165">Delete the compiler directive from your source code.</span></span>  
  
<span data-ttu-id="31731-166">\- o -</span><span class="sxs-lookup"><span data-stu-id="31731-166">\- or -</span></span>  
  
<span data-ttu-id="31731-167">Convierta en comentario la directiva de compilador.</span><span class="sxs-lookup"><span data-stu-id="31731-167">Comment out the compiler directive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31731-168">Cuando esté preparado para compilar, puede elegir **Compilar** en el menú **Compilar**, o bien usar el método de línea de comandos, pero sin escribir **d:** para definir símbolos de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="31731-168">When you are ready to compile, you can either choose **Build** from the **Build** menu, or use the command line method but without typing the **d:** to define conditional compilation symbols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31731-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="31731-169">See Also</span></span>  
 [<span data-ttu-id="31731-170">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="31731-170">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [<span data-ttu-id="31731-171">Creación, inicialización y configuración de modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-171">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)  
 [<span data-ttu-id="31731-172">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-172">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="31731-173">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="31731-173">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="31731-174">Adición de instrucciones de seguimiento al código de la aplicación</span><span class="sxs-lookup"><span data-stu-id="31731-174">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="31731-175">Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31731-175">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](~/docs/csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 [<span data-ttu-id="31731-176">Invocar al compilador de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="31731-176">How to: Invoke the Command-Line Compiler</span></span>](~/docs/visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)

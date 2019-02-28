---
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 2a359f4bf44887e7c7bc5422d485988b24f45600
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976478"
---
# <a name="-netcf"></a><span data-ttu-id="f5d4d-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="f5d4d-102">-netcf</span></span>
<span data-ttu-id="f5d4d-103">Establece el compilador con destino en [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5d4d-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5d4d-104">Syntax</span></span>  
  
```  
-netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="f5d4d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5d4d-105">Remarks</span></span>  
 <span data-ttu-id="f5d4d-106">El `-netcf` opción hace que el compilador de Visual Basic al destino la [!INCLUDE[Compact](~/includes/compact-md.md)] en lugar de completo [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5d4d-106">The `-netcf` option causes the Visual Basic compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f5d4d-107">Funcionalidad del lenguaje que solo está presente en el completo [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="f5d4d-108">El `-netcf` opción está diseñada para usarse con [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="f5d4d-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="f5d4d-109">Las características del lenguaje deshabilitadas de forma `-netcf` son las mismas características de lenguaje no está presentes en los archivos de destino con `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5d4d-110">El `-netcf` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="f5d4d-111">El `-netcf` opción se establece cuando se carga un proyecto de dispositivo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="f5d4d-112">El `-netcf` opción cambia las características de lenguaje siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5d4d-112">The `-netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="f5d4d-113">El [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) palabra clave, que finaliza la ejecución de un programa, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="f5d4d-114">El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]  
  
-   <span data-ttu-id="f5d4d-115">Enlace en tiempo de ejecución, en todos los formularios, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="f5d4d-116">Se generan errores en tiempo de compilación cuando se producen los escenarios de enlace reconocidos.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="f5d4d-117">El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]  
  
-   <span data-ttu-id="f5d4d-118">El [automática](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificadores están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="f5d4d-119">La sintaxis de la [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica la instrucción en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="f5d4d-120">El código siguiente muestra el efecto de `-netcf` en una compilación.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-120">The following code shows the effect of `-netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="f5d4d-121">Con las palabras clave de Visual Basic 6.0 que se quitaron de Visual Basic genera un error diferente cuando `-netcf` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="f5d4d-122">Esto afecta a los mensajes de error para las siguientes palabras clave:</span><span class="sxs-lookup"><span data-stu-id="f5d4d-122">This affects the error messages for the following keywords:</span></span>  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## <a name="example"></a><span data-ttu-id="f5d4d-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5d4d-123">Example</span></span>  
 <span data-ttu-id="f5d4d-124">El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utilizando las versiones de mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminada de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="f5d4d-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="f5d4d-125">Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5d4d-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console  
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5d4d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5d4d-126">See also</span></span>
- [<span data-ttu-id="f5d4d-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5d4d-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f5d4d-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5d4d-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="f5d4d-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="f5d4d-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

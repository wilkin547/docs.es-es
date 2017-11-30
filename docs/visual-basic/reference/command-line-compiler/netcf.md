---
title: /netcf
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /netcf
- netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a75573b0881af71e907a488c2b3c15db3816fc0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="netcf"></a><span data-ttu-id="e39a4-102">/netcf</span><span class="sxs-lookup"><span data-stu-id="e39a4-102">/netcf</span></span>
<span data-ttu-id="e39a4-103">Establece el compilador con destino en [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39a4-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e39a4-104">Syntax</span></span>  
  
```  
/netcf  
```  
  
## <a name="remarks"></a><span data-ttu-id="e39a4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e39a4-105">Remarks</span></span>  
 <span data-ttu-id="e39a4-106">El `/netcf` opción causas el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador con destino el [!INCLUDE[Compact](~/includes/compact-md.md)] en lugar de toda la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39a4-106">The `/netcf` option causes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e39a4-107">Funcionalidad del lenguaje que está presente sólo en toda la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="e39a4-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>  
  
 <span data-ttu-id="e39a4-108">El `/netcf` opción está diseñada para usarse con [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="e39a4-108">The `/netcf` option is designed to be used with [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="e39a4-109">Las características de lenguaje deshabilitadas por `/netcf` son las mismas características de lenguaje que no están presentes en los archivos de destino con `/sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="e39a4-109">The language features disabled by `/netcf` are the same language features not present in the files targeted with `/sdkpath`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e39a4-110">El `/netcf` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e39a4-110">The `/netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="e39a4-111">El `/netcf` opción se establece cuando un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] se carga el proyecto de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e39a4-111">The `/netcf` option is set when a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="e39a4-112">El `/netcf` opción cambia las características de lenguaje siguientes:</span><span class="sxs-lookup"><span data-stu-id="e39a4-112">The `/netcf` option changes the following language features:</span></span>  
  
-   <span data-ttu-id="e39a4-113">El [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) palabra clave, que finaliza la ejecución de un programa, está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e39a4-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="e39a4-114">El programa siguiente compila y se ejecuta sin `/netcf` , pero se produce un error en tiempo de compilación con `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="e39a4-114">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   <span data-ttu-id="e39a4-115">Enlace de tiempo de ejecución, en todos los formularios, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="e39a4-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="e39a4-116">Se generan errores en tiempo de compilación cuando se encuentran escenarios de enlace tardío reconocidos.</span><span class="sxs-lookup"><span data-stu-id="e39a4-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="e39a4-117">El programa siguiente compila y se ejecuta sin `/netcf` , pero se produce un error en tiempo de compilación con `/netcf`.</span><span class="sxs-lookup"><span data-stu-id="e39a4-117">The following program compiles and runs without `/netcf` but fails at compile time with `/netcf`.</span></span>  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   <span data-ttu-id="e39a4-118">El [automática](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificadores están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="e39a4-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="e39a4-119">La sintaxis de la [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica la instrucción en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="e39a4-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="e39a4-120">El código siguiente muestra el efecto de `/netcf` en una compilación.</span><span class="sxs-lookup"><span data-stu-id="e39a4-120">The following code shows the effect of `/netcf` on a compilation.</span></span>  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   <span data-ttu-id="e39a4-121">Usar palabras clave de Visual Basic 6.0 que se quitaron de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] genera un error diferente cuando `/netcf` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e39a4-121">Using Visual Basic 6.0 keywords that were removed from [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] generates a different error when `/netcf` is used.</span></span> <span data-ttu-id="e39a4-122">Esto afecta a los mensajes de error para las palabras clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="e39a4-122">This affects the error messages for the following keywords:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="e39a4-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e39a4-123">Example</span></span>  
 <span data-ttu-id="e39a4-124">El siguiente código compila `Myfile.vb` con el [!INCLUDE[Compact](~/includes/compact-md.md)], utiliza las versiones de mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminado de la [!INCLUDE[Compact](~/includes/compact-md.md)] en la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="e39a4-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="e39a4-125">Normalmente, se usa la versión más reciente de la [!INCLUDE[Compact](~/includes/compact-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39a4-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e39a4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e39a4-126">See Also</span></span>  
 [<span data-ttu-id="e39a4-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e39a4-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e39a4-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e39a4-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="e39a4-129">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="e39a4-129">/sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

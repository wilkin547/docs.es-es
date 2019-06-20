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
ms.openlocfilehash: 028fa148d0e5622648a5fdfff1789c3d0bfde057
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268284"
---
# <a name="-netcf"></a><span data-ttu-id="ba9a9-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="ba9a9-102">-netcf</span></span>

<span data-ttu-id="ba9a9-103">Establece el compilador para .NET Compact Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba9a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba9a9-104">Syntax</span></span>

```
-netcf
```

## <a name="remarks"></a><span data-ttu-id="ba9a9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba9a9-105">Remarks</span></span>

<span data-ttu-id="ba9a9-106">El `-netcf` opción hace que el compilador de Visual Basic para .NET Compact Framework en lugar de la versión completa de .NET Framework de destino.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="ba9a9-107">Funcionalidad del lenguaje que solo está presente en la versión completa de .NET Framework está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="ba9a9-108">El `-netcf` opción está diseñada para usarse con [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="ba9a9-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="ba9a9-109">Las características del lenguaje deshabilitadas de forma `-netcf` son las mismas características de lenguaje no está presentes en los archivos de destino con `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="ba9a9-110">El `-netcf` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="ba9a9-111">El `-netcf` opción se establece cuando se carga un proyecto de dispositivo de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="ba9a9-112">El `-netcf` opción cambia las características de lenguaje siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba9a9-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="ba9a9-113">El [final \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) palabra clave, que finaliza la ejecución de un programa, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="ba9a9-114">El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="ba9a9-115">Enlace en tiempo de ejecución, en todos los formularios, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="ba9a9-116">Se generan errores en tiempo de compilación cuando se producen los escenarios de enlace reconocidos.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="ba9a9-117">El programa siguiente compila y se ejecuta sin `-netcf` pero se produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="ba9a9-118">El [automática](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modificadores están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="ba9a9-119">La sintaxis de la [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica la instrucción en `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="ba9a9-120">El código siguiente muestra el efecto de `-netcf` en una compilación.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="ba9a9-121">Con las palabras clave de Visual Basic 6.0 que se quitaron de Visual Basic genera un error diferente cuando `-netcf` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="ba9a9-122">Esto afecta a los mensajes de error para las siguientes palabras clave:</span><span class="sxs-lookup"><span data-stu-id="ba9a9-122">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="ba9a9-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a9-123">Example</span></span>

<span data-ttu-id="ba9a9-124">El siguiente código compila `Myfile.vb` con .NET Compact Framework, utilizando las versiones de mscorlib.dll y Microsoft.VisualBasic.dll se encuentra en el directorio de instalación predeterminado de .NET Compact Framework en la unidad C:.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="ba9a9-125">Normalmente, se usa la versión más reciente de .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="ba9a9-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="ba9a9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba9a9-126">See also</span></span>

- [<span data-ttu-id="ba9a9-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba9a9-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ba9a9-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba9a9-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="ba9a9-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="ba9a9-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

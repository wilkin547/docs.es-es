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
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716716"
---
# <a name="-netcf"></a><span data-ttu-id="78e9a-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="78e9a-102">-netcf</span></span>

<span data-ttu-id="78e9a-103">Establece el compilador para que tenga como destino el .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="78e9a-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="78e9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78e9a-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="78e9a-105">Notas</span><span class="sxs-lookup"><span data-stu-id="78e9a-105">Remarks</span></span>

<span data-ttu-id="78e9a-106">La opción `-netcf` hace que el compilador de Visual Basic tenga como destino la .NET Compact Framework en lugar de la .NET Framework completa.</span><span class="sxs-lookup"><span data-stu-id="78e9a-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="78e9a-107">La funcionalidad del lenguaje que solo está presente en el .NET Framework completo está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="78e9a-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="78e9a-108">La opción `-netcf` está diseñada para usarse con [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span><span class="sxs-lookup"><span data-stu-id="78e9a-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="78e9a-109">Las características de lenguaje deshabilitadas por `-netcf` son las mismas características de lenguaje que no están presentes en los archivos de destino de `-sdkpath`.</span><span class="sxs-lookup"><span data-stu-id="78e9a-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="78e9a-110">La opción `-netcf` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="78e9a-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="78e9a-111">La opción `-netcf` se establece cuando se carga un proyecto de dispositivo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="78e9a-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="78e9a-112">La opción `-netcf` cambia las siguientes características del lenguaje:</span><span class="sxs-lookup"><span data-stu-id="78e9a-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="78e9a-113">La palabra clave [End \<palabra clave > instrucción](../../../visual-basic/language-reference/statements/end-keyword-statement.md) , que finaliza la ejecución de un programa, está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="78e9a-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="78e9a-114">El siguiente programa se compila y se ejecuta sin `-netcf` pero produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="78e9a-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="78e9a-115">El enlace en tiempo de ejecución, en todos los formularios, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="78e9a-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="78e9a-116">Se generan errores en tiempo de compilación cuando se encuentran escenarios de enlace en tiempo de ejecución reconocidos.</span><span class="sxs-lookup"><span data-stu-id="78e9a-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="78e9a-117">El siguiente programa se compila y se ejecuta sin `-netcf` pero produce un error en tiempo de compilación con `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="78e9a-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="78e9a-118">Los modificadores [automático](../../../visual-basic/language-reference/modifiers/auto.md), [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md)y [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="78e9a-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="78e9a-119">La sintaxis de la [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) también se modifica para `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span><span class="sxs-lookup"><span data-stu-id="78e9a-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="78e9a-120">En el código siguiente se muestra el efecto de `-netcf` en una compilación.</span><span class="sxs-lookup"><span data-stu-id="78e9a-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="78e9a-121">El uso de Visual Basic palabras clave 6,0 que se quitaron de Visual Basic genera un error diferente cuando se usa `-netcf`.</span><span class="sxs-lookup"><span data-stu-id="78e9a-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="78e9a-122">Esto afecta a los mensajes de error de las palabras clave siguientes:</span><span class="sxs-lookup"><span data-stu-id="78e9a-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="78e9a-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78e9a-123">Example</span></span>

<span data-ttu-id="78e9a-124">El código siguiente compila `Myfile.vb` con el .NET Compact Framework, con las versiones de mscorlib. dll y Microsoft. VisualBasic. dll que se encuentran en el directorio de instalación predeterminado de la .NET Compact Framework en la unidad C.</span><span class="sxs-lookup"><span data-stu-id="78e9a-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="78e9a-125">Normalmente, se usaría la versión más reciente de la .NET Compact Framework.</span><span class="sxs-lookup"><span data-stu-id="78e9a-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="78e9a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="78e9a-126">See also</span></span>

- [<span data-ttu-id="78e9a-127">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78e9a-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="78e9a-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="78e9a-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="78e9a-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="78e9a-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)

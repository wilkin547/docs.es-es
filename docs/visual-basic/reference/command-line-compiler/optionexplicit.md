---
title: -optionexplicit
ms.date: 07/20/2015
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
ms.openlocfilehash: 1de1b3a816739fc5f8ba1d1251b673c0b708d106
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969497"
---
# <a name="-optionexplicit"></a><span data-ttu-id="74e1d-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="74e1d-102">-optionexplicit</span></span>
<span data-ttu-id="74e1d-103">Hace que el compilador notifique errores si no se declaran las variables antes de utilizarlas.</span><span class="sxs-lookup"><span data-stu-id="74e1d-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74e1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74e1d-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="74e1d-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="74e1d-105">Arguments</span></span>  
 <span data-ttu-id="74e1d-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="74e1d-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="74e1d-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="74e1d-107">Optional.</span></span> <span data-ttu-id="74e1d-108">Especificar `-optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="74e1d-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="74e1d-109">El `-optionexplicit+` opción es el valor predeterminado y es el mismo que `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="74e1d-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="74e1d-110">El `-optionexplicit-` opción permite la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="74e1d-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74e1d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74e1d-111">Remarks</span></span>  
 <span data-ttu-id="74e1d-112">Si el archivo de código fuente contiene un [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción invalida el `-optionexplicit` configuración del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="74e1d-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="74e1d-113">Establecer - optionexplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="74e1d-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="74e1d-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="74e1d-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="74e1d-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="74e1d-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="74e1d-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="74e1d-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="74e1d-117">Modifique el valor en el **Option Explicit** cuadro.</span><span class="sxs-lookup"><span data-stu-id="74e1d-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74e1d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74e1d-118">Example</span></span>  
 <span data-ttu-id="74e1d-119">El siguiente código compila cuando `-optionexplicit-` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="74e1d-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionExplicitOff.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="74e1d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="74e1d-120">See also</span></span>
- [<span data-ttu-id="74e1d-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74e1d-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="74e1d-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="74e1d-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="74e1d-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="74e1d-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="74e1d-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="74e1d-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="74e1d-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="74e1d-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="74e1d-126">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="74e1d-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="74e1d-127">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="74e1d-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

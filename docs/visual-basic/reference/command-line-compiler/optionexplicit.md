---
title: -optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
- -optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39ad78c82303d3655d5dda9e2286df0a55b8bf3e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-optionexplicit"></a><span data-ttu-id="aff36-102">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="aff36-102">-optionexplicit</span></span>
<span data-ttu-id="aff36-103">Hace que el compilador para informar de errores si no se declaran variables antes de utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="aff36-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aff36-104">Syntax</span></span>  
  
```  
-optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="aff36-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="aff36-105">Arguments</span></span>  
 <span data-ttu-id="aff36-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="aff36-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="aff36-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="aff36-107">Optional.</span></span> <span data-ttu-id="aff36-108">Especificar `-optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="aff36-108">Specify `-optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="aff36-109">El `-optionexplicit+` opción es el valor predeterminado y es el mismo que `-optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="aff36-109">The `-optionexplicit+` option is the default and is the same as `-optionexplicit`.</span></span> <span data-ttu-id="aff36-110">El `-optionexplicit-` opción habilita la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="aff36-110">The `-optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aff36-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aff36-111">Remarks</span></span>  
 <span data-ttu-id="aff36-112">Si el archivo de código fuente contiene un [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción anula la `-optionexplicit` configuración del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aff36-112">If the source code file contains an [Option Explicit statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `-optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set--optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="aff36-113">Para establecer - optionexplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="aff36-113">To set -optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="aff36-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="aff36-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="aff36-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aff36-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="aff36-116">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="aff36-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="aff36-117">Modifique el valor en el **Option Explicit** cuadro.</span><span class="sxs-lookup"><span data-stu-id="aff36-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff36-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aff36-118">Example</span></span>  
 <span data-ttu-id="aff36-119">El siguiente código compila cuando `-optionexplicit-` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="aff36-119">The following code compiles when `-optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="aff36-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="aff36-120">See Also</span></span>  
 [<span data-ttu-id="aff36-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aff36-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="aff36-122">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="aff36-122">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="aff36-123">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="aff36-123">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="aff36-124">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="aff36-124">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="aff36-125">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aff36-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="aff36-126">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="aff36-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="aff36-127">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="aff36-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

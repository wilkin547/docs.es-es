---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1cfdb94ebafa7d6a14253aeb59ab98b3a953fe4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optionexplicit"></a><span data-ttu-id="35154-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="35154-102">/optionexplicit</span></span>
<span data-ttu-id="35154-103">Hace que el compilador para informar de errores si no se declaran variables antes de utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="35154-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35154-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35154-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="35154-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="35154-105">Arguments</span></span>  
 <span data-ttu-id="35154-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="35154-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="35154-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="35154-107">Optional.</span></span> <span data-ttu-id="35154-108">Especificar `/optionexplicit+` para requerir la declaración explícita de variables.</span><span class="sxs-lookup"><span data-stu-id="35154-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="35154-109">El `/optionexplicit+` opción es el valor predeterminado y es el mismo que `/optionexplicit`.</span><span class="sxs-lookup"><span data-stu-id="35154-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="35154-110">El `/optionexplicit-` opción habilita la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="35154-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35154-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35154-111">Remarks</span></span>  
 <span data-ttu-id="35154-112">Si el archivo de código fuente contiene un [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md), la instrucción anula la `/optionexplicit` configuración del compilador de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="35154-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="35154-113">Para establecer /optionexplicit en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35154-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="35154-114">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="35154-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="35154-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="35154-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="35154-116">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="35154-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="35154-117">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="35154-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="35154-118">Modifique el valor en el **Option Explicit** cuadro.</span><span class="sxs-lookup"><span data-stu-id="35154-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35154-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35154-119">Example</span></span>  
 <span data-ttu-id="35154-120">El siguiente código compila cuando `/optionexplicit-` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="35154-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="35154-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="35154-121">See Also</span></span>  
 [<span data-ttu-id="35154-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35154-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="35154-123">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="35154-123">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="35154-124">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="35154-124">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="35154-125">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="35154-125">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="35154-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="35154-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="35154-127">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="35154-127">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="35154-128">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="35154-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

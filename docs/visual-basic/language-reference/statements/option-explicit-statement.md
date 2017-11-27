---
title: "Option Explicit (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d39b3d7cf5096e3b263938d32e017eae5708e042
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="5af21-102">Option Explicit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5af21-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="5af21-103">Fuerza la declaración explícita de todas las variables en un archivo o permite que las declaraciones implícitas de variables.</span><span class="sxs-lookup"><span data-stu-id="5af21-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5af21-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="5af21-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5af21-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="5af21-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5af21-106">Optional.</span></span> <span data-ttu-id="5af21-107">Permite `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="5af21-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="5af21-108">Si `On` o `Off` no se especifica, el valor predeterminado es `On`.</span><span class="sxs-lookup"><span data-stu-id="5af21-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="5af21-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5af21-109">Optional.</span></span> <span data-ttu-id="5af21-110">Deshabilita `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="5af21-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5af21-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5af21-111">Remarks</span></span>  
 <span data-ttu-id="5af21-112">Cuando `Option Explicit On` o `Option Explicit` aparece en el archivo, debe declarar explícitamente todas las variables utilizando la `Dim` o `ReDim` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5af21-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="5af21-113">Si intenta usar un nombre de variable no declarada, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5af21-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="5af21-114">El `Option Explicit Off` instrucción permite la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="5af21-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="5af21-115">Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5af21-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5af21-116">Establecer `Option Explicit` a `Off` no suele ser una buena práctica.</span><span class="sxs-lookup"><span data-stu-id="5af21-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="5af21-117">Si se equivoca y escribe un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="5af21-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="5af21-118">Cuando una instrucción Option Explicit no está presente</span><span class="sxs-lookup"><span data-stu-id="5af21-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="5af21-119">Si el código fuente no contiene un `Option Explicit` (instrucción), el **Option Explicit** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5af21-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="5af21-120">Si se usa el compilador de línea de comandos, el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) se utiliza la opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="5af21-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="5af21-121">Para establecer Option Explicit en el IDE</span><span class="sxs-lookup"><span data-stu-id="5af21-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="5af21-122">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="5af21-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="5af21-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5af21-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="5af21-124">Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="5af21-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="5af21-125">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="5af21-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="5af21-126">Establezca el valor el **Option Explicit** cuadro.</span><span class="sxs-lookup"><span data-stu-id="5af21-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="5af21-127">Cuando se crea un nuevo proyecto, el **Option Explicit** en el **compilar** ficha está establecida en el **Option Explicit** en el **valorespredeterminadosdeVB**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5af21-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="5af21-128">Para tener acceso a la **valores predeterminados de VB** cuadro de diálogo, en la **herramientas** menú, haga clic en **opciones**.</span><span class="sxs-lookup"><span data-stu-id="5af21-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="5af21-129">En el **opciones** cuadro de diálogo, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="5af21-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="5af21-130">El valor predeterminado inicial de **valores predeterminados de VB** es `On`.</span><span class="sxs-lookup"><span data-stu-id="5af21-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="5af21-131">Para establecer Option Explicit en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="5af21-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="5af21-132">Incluir el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opción del compilador en el **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="5af21-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5af21-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5af21-133">Example</span></span>  
 <span data-ttu-id="5af21-134">En el ejemplo siguiente se usa el `Option Explicit` instrucción para forzar la declaración explícita de todas las variables.</span><span class="sxs-lookup"><span data-stu-id="5af21-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="5af21-135">Cualquier intento de usar una variable no declarada, producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5af21-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5af21-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5af21-136">See Also</span></span>  
 [<span data-ttu-id="5af21-137">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5af21-137">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="5af21-138">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5af21-138">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="5af21-139">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5af21-139">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="5af21-140">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5af21-140">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="5af21-141">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="5af21-141">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="5af21-142">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="5af21-142">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="5af21-143">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="5af21-143">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="5af21-144">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="5af21-144">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

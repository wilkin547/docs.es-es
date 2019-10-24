---
title: Option Explicit (Instrucción, Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 0405814efecbdff5769af36b27dce1cd3305aab5
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775495"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="db2cd-102">Option Explicit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db2cd-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="db2cd-103">Fuerza la declaración explícita de todas las variables de un archivo o permite declaraciones implícitas de variables.</span><span class="sxs-lookup"><span data-stu-id="db2cd-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db2cd-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="db2cd-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="db2cd-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="db2cd-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db2cd-106">Optional.</span></span> <span data-ttu-id="db2cd-107">Habilita la comprobación de `Option Explicit`.</span><span class="sxs-lookup"><span data-stu-id="db2cd-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="db2cd-108">Si no se especifica `On` o `Off`, el valor predeterminado es `On`.</span><span class="sxs-lookup"><span data-stu-id="db2cd-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="db2cd-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db2cd-109">Optional.</span></span> <span data-ttu-id="db2cd-110">Deshabilita la comprobación de `Option Explicit`.</span><span class="sxs-lookup"><span data-stu-id="db2cd-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db2cd-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db2cd-111">Remarks</span></span>  
 <span data-ttu-id="db2cd-112">Cuando `Option Explicit On` o `Option Explicit` aparezca en un archivo, debe declarar explícitamente todas las variables mediante el uso de las instrucciones `Dim` o `ReDim`.</span><span class="sxs-lookup"><span data-stu-id="db2cd-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="db2cd-113">Si intenta usar un nombre de variable no declarado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="db2cd-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="db2cd-114">La instrucción `Option Explicit Off` permite la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="db2cd-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="db2cd-115">Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.</span><span class="sxs-lookup"><span data-stu-id="db2cd-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db2cd-116">La configuración de `Option Explicit` en `Off` no suele ser una buena práctica.</span><span class="sxs-lookup"><span data-stu-id="db2cd-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="db2cd-117">Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="db2cd-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="db2cd-118">Cuando una instrucción Option Explicit no está presente</span><span class="sxs-lookup"><span data-stu-id="db2cd-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="db2cd-119">Si el código fuente no contiene una instrucción `Option Explicit`, se usa el valor **Option Explicit** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="db2cd-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="db2cd-120">Si se usa el compilador de línea de comandos, se usa la opción del compilador [-OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="db2cd-120">If the command-line compiler is used, the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="db2cd-121">Para establecer Option Explicit en el IDE</span><span class="sxs-lookup"><span data-stu-id="db2cd-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="db2cd-122">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="db2cd-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="db2cd-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="db2cd-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="db2cd-124">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="db2cd-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="db2cd-125">Establezca el valor en el cuadro **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="db2cd-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="db2cd-126">Al crear un nuevo proyecto, el valor **Option Explicit** en la pestaña **compilar** se establece en el valor **Option Explicit** en el cuadro de diálogo **valores predeterminados de VB** .</span><span class="sxs-lookup"><span data-stu-id="db2cd-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="db2cd-127">Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="db2cd-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="db2cd-128">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="db2cd-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="db2cd-129">La configuración predeterminada inicial en los **valores predeterminados de VB** es `On`.</span><span class="sxs-lookup"><span data-stu-id="db2cd-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="db2cd-130">Para establecer Option Explicit en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="db2cd-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="db2cd-131">Incluya la opción del compilador [-OptionExplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) en el comando **VBC** .</span><span class="sxs-lookup"><span data-stu-id="db2cd-131">Include the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db2cd-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db2cd-132">Example</span></span>  
 <span data-ttu-id="db2cd-133">En el ejemplo siguiente se usa la instrucción `Option Explicit` para forzar la declaración explícita de todas las variables.</span><span class="sxs-lookup"><span data-stu-id="db2cd-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="db2cd-134">Al intentar usar una variable no declarada, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="db2cd-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="db2cd-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="db2cd-135">See also</span></span>

- [<span data-ttu-id="db2cd-136">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db2cd-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="db2cd-137">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db2cd-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="db2cd-138">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db2cd-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="db2cd-139">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db2cd-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="db2cd-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="db2cd-140">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="db2cd-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="db2cd-141">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="db2cd-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="db2cd-142">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="db2cd-143">Valores predeterminados de Visual Basic, Proyectos, Cuadro de diálogo Opciones</span><span class="sxs-lookup"><span data-stu-id="db2cd-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

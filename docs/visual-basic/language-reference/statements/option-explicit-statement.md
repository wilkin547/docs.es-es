---
title: Instrucción Option Explicit
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
ms.openlocfilehash: a352df0323cfeca1ea0e206ae45c3f85a2cd7da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404374"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="4075e-102">Option Explicit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4075e-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="4075e-103">Fuerza la declaración explícita de todas las variables de un archivo o permite declaraciones implícitas de variables.</span><span class="sxs-lookup"><span data-stu-id="4075e-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4075e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4075e-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="4075e-105">Partes</span><span class="sxs-lookup"><span data-stu-id="4075e-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="4075e-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4075e-106">Optional.</span></span> <span data-ttu-id="4075e-107">Habilita la `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="4075e-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="4075e-108">Si `On` `Off` no se especifica o, el valor predeterminado es `On` .</span><span class="sxs-lookup"><span data-stu-id="4075e-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="4075e-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4075e-109">Optional.</span></span> <span data-ttu-id="4075e-110">Deshabilita la `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="4075e-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4075e-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4075e-111">Remarks</span></span>  
 <span data-ttu-id="4075e-112">Cuando `Option Explicit On` o `Option Explicit` aparece en un archivo, debe declarar explícitamente todas las variables mediante las `Dim` `ReDim` instrucciones o.</span><span class="sxs-lookup"><span data-stu-id="4075e-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="4075e-113">Si intenta usar un nombre de variable no declarado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4075e-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="4075e-114">La `Option Explicit Off` instrucción permite la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="4075e-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="4075e-115">Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.</span><span class="sxs-lookup"><span data-stu-id="4075e-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4075e-116">`Option Explicit`La configuración de en `Off` no suele ser una buena práctica.</span><span class="sxs-lookup"><span data-stu-id="4075e-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="4075e-117">Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="4075e-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="4075e-118">Cuando una instrucción Option Explicit no está presente</span><span class="sxs-lookup"><span data-stu-id="4075e-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="4075e-119">Si el código fuente no contiene una `Option Explicit` instrucción, se utiliza el valor **Option Explicit** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="4075e-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="4075e-120">Si se usa el compilador de línea de comandos, se usa la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="4075e-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="4075e-121">Para establecer Option Explicit en el IDE</span><span class="sxs-lookup"><span data-stu-id="4075e-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="4075e-122">En **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4075e-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="4075e-123">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4075e-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="4075e-124">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="4075e-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="4075e-125">Establezca el valor en el cuadro **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="4075e-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="4075e-126">Al crear un nuevo proyecto, el valor **Option Explicit** en la pestaña **compilar** se establece en el valor **Option Explicit** en el cuadro de diálogo **valores predeterminados de VB** .</span><span class="sxs-lookup"><span data-stu-id="4075e-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="4075e-127">Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="4075e-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="4075e-128">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="4075e-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="4075e-129">La configuración predeterminada inicial en los **valores predeterminados de VB** es `On` .</span><span class="sxs-lookup"><span data-stu-id="4075e-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="4075e-130">Para establecer Option Explicit en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="4075e-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="4075e-131">Incluya la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) en el comando **VBC** .</span><span class="sxs-lookup"><span data-stu-id="4075e-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4075e-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4075e-132">Example</span></span>  
 <span data-ttu-id="4075e-133">En el ejemplo siguiente se usa la `Option Explicit` instrucción para forzar la declaración explícita de todas las variables.</span><span class="sxs-lookup"><span data-stu-id="4075e-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="4075e-134">Al intentar usar una variable no declarada, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4075e-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="4075e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4075e-135">See also</span></span>

- [<span data-ttu-id="4075e-136">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="4075e-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="4075e-137">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="4075e-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="4075e-138">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4075e-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="4075e-139">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4075e-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="4075e-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="4075e-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="4075e-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="4075e-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="4075e-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="4075e-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="4075e-143">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="4075e-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

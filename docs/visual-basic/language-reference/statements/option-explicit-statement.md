---
description: 'Más información acerca de: Option Explicit (instrucción) (Visual Basic)'
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
ms.openlocfilehash: 11f59508125167fde98b4fc359dde7fd7c539b75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741619"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="41e1c-103">Option Explicit (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41e1c-103">Option Explicit Statement (Visual Basic)</span></span>

<span data-ttu-id="41e1c-104">Fuerza la declaración explícita de todas las variables de un archivo o permite declaraciones implícitas de variables.</span><span class="sxs-lookup"><span data-stu-id="41e1c-104">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41e1c-105">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="41e1c-106">Partes</span><span class="sxs-lookup"><span data-stu-id="41e1c-106">Parts</span></span>  

 `On`  
 <span data-ttu-id="41e1c-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="41e1c-107">Optional.</span></span> <span data-ttu-id="41e1c-108">Habilita la `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="41e1c-108">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="41e1c-109">Si `On` `Off` no se especifica o, el valor predeterminado es `On` .</span><span class="sxs-lookup"><span data-stu-id="41e1c-109">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="41e1c-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="41e1c-110">Optional.</span></span> <span data-ttu-id="41e1c-111">Deshabilita la `Option Explicit` comprobación.</span><span class="sxs-lookup"><span data-stu-id="41e1c-111">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41e1c-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="41e1c-112">Remarks</span></span>  

 <span data-ttu-id="41e1c-113">Cuando `Option Explicit On` o `Option Explicit` aparece en un archivo, debe declarar explícitamente todas las variables mediante las `Dim` `ReDim` instrucciones o.</span><span class="sxs-lookup"><span data-stu-id="41e1c-113">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="41e1c-114">Si intenta usar un nombre de variable no declarado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="41e1c-114">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="41e1c-115">La `Option Explicit Off` instrucción permite la declaración implícita de variables.</span><span class="sxs-lookup"><span data-stu-id="41e1c-115">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="41e1c-116">Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.</span><span class="sxs-lookup"><span data-stu-id="41e1c-116">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="41e1c-117">`Option Explicit`La configuración de en `Off` no suele ser una buena práctica.</span><span class="sxs-lookup"><span data-stu-id="41e1c-117">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="41e1c-118">Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="41e1c-118">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="41e1c-119">Cuando una instrucción Option Explicit no está presente</span><span class="sxs-lookup"><span data-stu-id="41e1c-119">When an Option Explicit Statement Is Not Present</span></span>  

 <span data-ttu-id="41e1c-120">Si el código fuente no contiene una `Option Explicit` instrucción, se utiliza el valor **Option Explicit** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="41e1c-120">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="41e1c-121">Si se usa el compilador de línea de comandos, se usa la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) .</span><span class="sxs-lookup"><span data-stu-id="41e1c-121">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="41e1c-122">Para establecer Option Explicit en el IDE</span><span class="sxs-lookup"><span data-stu-id="41e1c-122">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="41e1c-123">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="41e1c-123">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="41e1c-124">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="41e1c-124">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="41e1c-125">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="41e1c-125">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="41e1c-126">Establezca el valor en el cuadro **Option Explicit** .</span><span class="sxs-lookup"><span data-stu-id="41e1c-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="41e1c-127">Al crear un nuevo proyecto, el valor **Option Explicit** en la pestaña **compilar** se establece en el valor **Option Explicit** en el cuadro de diálogo **valores predeterminados de VB** .</span><span class="sxs-lookup"><span data-stu-id="41e1c-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="41e1c-128">Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="41e1c-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="41e1c-129">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="41e1c-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="41e1c-130">La configuración predeterminada inicial en los **valores predeterminados de VB** es `On` .</span><span class="sxs-lookup"><span data-stu-id="41e1c-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="41e1c-131">Para establecer Option Explicit en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="41e1c-131">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="41e1c-132">Incluya la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) en el comando **VBC** .</span><span class="sxs-lookup"><span data-stu-id="41e1c-132">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e1c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41e1c-133">Example</span></span>  

 <span data-ttu-id="41e1c-134">En el ejemplo siguiente se usa la `Option Explicit` instrucción para forzar la declaración explícita de todas las variables.</span><span class="sxs-lookup"><span data-stu-id="41e1c-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="41e1c-135">Al intentar usar una variable no declarada, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="41e1c-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="41e1c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="41e1c-136">See also</span></span>

- [<span data-ttu-id="41e1c-137">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="41e1c-137">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="41e1c-138">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="41e1c-138">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="41e1c-139">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="41e1c-139">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="41e1c-140">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="41e1c-140">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="41e1c-141">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="41e1c-141">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="41e1c-142">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="41e1c-142">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="41e1c-143">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="41e1c-143">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="41e1c-144">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="41e1c-144">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

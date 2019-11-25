---
title: Option Explicit (Instrucción)
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
ms.openlocfilehash: 3c70d958fdcbb1782af22c3a4715676abbeeac0c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353784"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit (Instrucción, Visual Basic)
Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Elementos  
 `On`  
 Opcional. Enables `Option Explicit` checking. If `On` or `Off` is not specified, the default is `On`.  
  
 `Off`  
 Opcional. Disables `Option Explicit` checking.  
  
## <a name="remarks"></a>Comentarios  
 When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements. If you try to use an undeclared variable name, an error occurs at compile time. The `Option Explicit Off` statement allows implicit declaration of variables.  
  
 Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
> [!NOTE]
> Setting `Option Explicit` to `Off` is generally not a good practice. Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>When an Option Explicit Statement Is Not Present  
 If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used. If the command-line compiler is used, the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>To set Option Explicit in the IDE  
  
1. En el **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Set the value in the **Option Explicit** box.  
  
 When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box. To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**. En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**. The initial default setting in **VB Defaults** is `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>To set Option Explicit on the command line  
  
- Include the [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.  
  
## <a name="example"></a>Ejemplo  
 The following example uses the `Option Explicit` statement to force explicit declaration of all variables. Attempting to use an undeclared variable causes an error at compile time.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>Vea también

- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Valores predeterminados de Visual Basic, Proyectos, Cuadro de diálogo Opciones](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

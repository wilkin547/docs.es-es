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
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604606"
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit (Instrucción, Visual Basic)
Fuerza la declaración explícita de todas las variables en un archivo o permite que las declaraciones implícitas de variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Elementos  
 `On`  
 Opcional. Permite `Option Explicit` comprobación. Si `On` o `Off` no se especifica, el valor predeterminado es `On`.  
  
 `Off`  
 Opcional. Deshabilita `Option Explicit` comprobación.  
  
## <a name="remarks"></a>Comentarios  
 Cuando `Option Explicit On` o `Option Explicit` aparece en el archivo, debe declarar explícitamente todas las variables utilizando la `Dim` o `ReDim` las instrucciones. Si intenta usar un nombre de variable no declarada, se produce un error en tiempo de compilación. El `Option Explicit Off` instrucción permite la declaración implícita de variables.  
  
 Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
> [!NOTE]
>  Establecer `Option Explicit` a `Off` no suele ser una buena práctica. Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Cuando una instrucción Option Explicit no está presente  
 Si el código fuente no contiene un `Option Explicit` (instrucción), el **Option Explicit** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. Si se usa el compilador de línea de comandos, el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) se utiliza la opción del compilador.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Para establecer Option Explicit en el IDE  
  
1.  En el **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2.  Haga clic en la pestaña **Compilar**.  
  
3.  Establezca el valor el **Option Explicit** cuadro.  
  
 Cuando se crea un nuevo proyecto, el **Option Explicit** en el **compilar** ficha está establecida en el **Option Explicit** en el **valorespredeterminadosdeVB**cuadro de diálogo. Para tener acceso a la **valores predeterminados de VB** cuadro de diálogo, en la **herramientas** menú, haga clic en **opciones**. En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Para establecer Option Explicit en la línea de comandos  
  
-   Incluir el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Option Explicit` instrucción para forzar la declaración explícita de todas las variables. Cualquier intento de usar una variable no declarada, producirá un error en tiempo de compilación.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

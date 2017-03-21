---
title: "Option Explicit (instrucción) (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 020f12f1fbb9a06647215f1fac6324e3b74e8a77
ms.lasthandoff: 03/13/2017

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
 Cuando `Option Explicit On` o `Option Explicit` aparece en un archivo, debe declarar explícitamente todas las variables utilizando la `Dim` o `ReDim` las instrucciones. Si intenta utilizar un nombre de variable no declarada, se produce un error en tiempo de compilación. El `Option Explicit Off` instrucción permite la declaración implícita de variables.  
  
 Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
> [!NOTE]
>  Configuración de `Option Explicit` a `Off` no suele ser una buena práctica. Se se equivoca y escribe un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Cuando una instrucción Option Explicit no está presente  
 Si el código fuente no contiene una `Option Explicit` instrucción, el **Option Explicit** en el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza. Si se usa el compilador de línea de comandos, el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) se utiliza la opción del compilador.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Para establecer Option Explicit en el IDE  
  
1.  En **el Explorador de soluciones**, seleccione un proyecto. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en el **compilar** ficha.  
  
3.  Establezca el valor de la **Option Explicit** cuadro.  
  
 Cuando se crea un nuevo proyecto, el **Option Explicit** en el **compilar** ficha se establece en el **Option Explicit** en el **valores predeterminados de VB** cuadro de diálogo. Para tener acceso a la **valores predeterminados de VB** cuadro de diálogo el **herramientas** menú, haga clic en **opciones**. En el **opciones** diálogo cuadro, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**. El valor predeterminado inicial de **valores predeterminados de VB** es `On`.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Para establecer Option Explicit en la línea de comandos  
  
-   Incluir el [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) opción del compilador en el **vbc** comando.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Option Explicit` instrucción para exigir la declaración explícita de todas las variables. Al intentar utilizar una variable no declarada, produce un error en tiempo de compilación.  
  
 [!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements Nº&48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim (instrucción)](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

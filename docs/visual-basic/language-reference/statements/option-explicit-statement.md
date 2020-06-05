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
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit (Instrucción, Visual Basic)
Fuerza la declaración explícita de todas las variables de un archivo o permite declaraciones implícitas de variables.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>Partes  
 `On`  
 Opcional. Habilita la `Option Explicit` comprobación. Si `On` `Off` no se especifica o, el valor predeterminado es `On` .  
  
 `Off`  
 Opcional. Deshabilita la `Option Explicit` comprobación.  
  
## <a name="remarks"></a>Observaciones  
 Cuando `Option Explicit On` o `Option Explicit` aparece en un archivo, debe declarar explícitamente todas las variables mediante las `Dim` `ReDim` instrucciones o. Si intenta usar un nombre de variable no declarado, se produce un error en tiempo de compilación. La `Option Explicit Off` instrucción permite la declaración implícita de variables.  
  
 Si se utiliza la instrucción `Option Explicit`, debe aparecer en un archivo antes que cualquier otra instrucción de código fuente.  
  
> [!NOTE]
> `Option Explicit`La configuración de en `Off` no suele ser una buena práctica. Podría escribir mal un nombre de variable en una o varias ubicaciones, lo que provocaría resultados inesperados cuando se ejecuta el programa.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Cuando una instrucción Option Explicit no está presente  
 Si el código fuente no contiene una `Option Explicit` instrucción, se utiliza el valor **Option Explicit** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) . Si se usa el compilador de línea de comandos, se usa la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) .  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>Para establecer Option Explicit en el IDE  
  
1. En **Explorador de soluciones**, seleccione un proyecto. En el menú **Proyecto**, haga clic en **Propiedades**.  
  
2. Haga clic en la pestaña **Compilar**.  
  
3. Establezca el valor en el cuadro **Option Explicit** .  
  
 Al crear un nuevo proyecto, el valor **Option Explicit** en la pestaña **compilar** se establece en el valor **Option Explicit** en el cuadro de diálogo **valores predeterminados de VB** . Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**. En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**. La configuración predeterminada inicial en los **valores predeterminados de VB** es `On` .  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>Para establecer Option Explicit en la línea de comandos  
  
- Incluya la opción del compilador [-OptionExplicit](../../reference/command-line-compiler/optionexplicit.md) en el comando **VBC** .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa la `Option Explicit` instrucción para forzar la declaración explícita de todas las variables. Al intentar usar una variable no declarada, se produce un error en tiempo de compilación.  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Dim](dim-statement.md)
- [Instrucción ReDim](redim-statement.md)
- [Option Compare (instrucción)](option-compare-statement.md)
- [Option Strict (instrucción)](option-strict-statement.md)
- [-optioncompare](../../reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../reference/command-line-compiler/optionstrict.md)
- [Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

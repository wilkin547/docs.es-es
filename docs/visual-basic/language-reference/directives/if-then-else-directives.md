---
title: '#If... Then... #Else directivas (Visual Basic)'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: aaf5e7dd82cebf734da59e9feb89174705468a4b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580088"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else (Directivas)

Compila condicionalmente bloques seleccionados de código Visual Basic.

## <a name="syntax"></a>Sintaxis

```vb
#If expression Then
   statements
[ #ElseIf expression Then
   [ statements ]
...
#ElseIf expression Then
   [ statements ] ]
[ #Else
   [ statements ] ]
#End If
```

## <a name="parts"></a>Elementos

`expression`  
Se requiere para las instrucciones `#If` y `#ElseIf`, opcional en otro lugar. Cualquier expresión, que consta exclusivamente de una o varias constantes, literales y operadores del compilador condicionales, que se evalúa como `True` o `False`.

`statements`  
Obligatorio para `#If` bloque de instrucciones, opcional en otro lugar. Visual Basic líneas de programa o directivas de compilador que se compilan si la expresión asociada se evalúa como `True`.

`#End If`  
Finaliza el `#If` bloque de instrucciones.

## <a name="remarks"></a>Comentarios

En la superficie, el comportamiento de las directivas de `#If...Then...#Else` aparece igual que el de las instrucciones `If...Then...Else`. Sin embargo, las directivas de `#If...Then...#Else` evalúan lo que compila el compilador, mientras que las instrucciones `If...Then...Else` evalúan las condiciones en tiempo de ejecución.

La compilación condicional se usa normalmente para compilar el mismo programa para distintas plataformas. También se usa para evitar que el código de depuración aparezca en un archivo ejecutable. El código excluido durante la compilación condicional se omite completamente del archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o el rendimiento.

Independientemente del resultado de cualquier evaluación, todas las expresiones se evalúan mediante `Option Compare Binary`. La instrucción `Option Compare` no afecta a las expresiones de las instrucciones `#If` y `#ElseIf`.

> [!NOTE]
> No existe ninguna forma de una sola línea de las directivas `#If`, `#Else`, `#ElseIf` y `#End If`. No puede aparecer ningún otro código en la misma línea que ninguna de las directivas.

Las instrucciones de un bloque de compilación condicional deben ser instrucciones lógicas completas. Por ejemplo, no puede compilar condicionalmente solo los atributos de una función, pero puede declarar condicionalmente la función junto con sus atributos:

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a>Ejemplo

En este ejemplo se usa la construcción `#If...Then...#Else` para determinar si se deben compilar ciertas instrucciones.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>Vea también

- [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>

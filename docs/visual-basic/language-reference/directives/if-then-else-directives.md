---
description: 'Más información acerca de: #If... Then... #Else directivas'
title: '#Directivas If...Then...#Else'
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
ms.openlocfilehash: fd95d259315e0bd6fd6ab2a3f222288bb4726ce6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797255"
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

## <a name="parts"></a>Partes

`expression`  
Necesario para `#If` las `#ElseIf` instrucciones y, opcional en cualquier otro lugar. Cualquier expresión, que consta exclusivamente de una o varias constantes, literales y operadores del compilador condicionales, que se evalúa como `True` o `False` .

`statements`  
Requerido para el `#If` bloque de instrucciones, opcional en otro lugar. Visual Basic líneas de programa o directivas de compilador que se compilan si la expresión asociada se evalúa como `True` .

`#End If`  
Finaliza el `#If` bloque de instrucciones.

## <a name="remarks"></a>Observaciones

En la superficie, el comportamiento de las `#If...Then...#Else` directivas aparece igual que el de las `If...Then...Else` instrucciones. Sin embargo, las `#If...Then...#Else` directivas evalúan lo que compila el compilador, mientras que las `If...Then...Else` instrucciones evalúan las condiciones en tiempo de ejecución.

La compilación condicional se usa normalmente para compilar el mismo programa para distintas plataformas. También se usa para evitar que el código de depuración aparezca en un archivo ejecutable. El código excluido durante la compilación condicional se omite completamente del archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o el rendimiento.

Independientemente del resultado de cualquier evaluación, todas las expresiones se evalúan utilizando `Option Compare Binary` . La `Option Compare` instrucción no afecta a las expresiones de las `#If` `#ElseIf` instrucciones y.

> [!NOTE]
> No existe ninguna forma de una línea de las `#If` `#Else` directivas,, `#ElseIf` y `#End If` . No puede aparecer ningún otro código en la misma línea que ninguna de las directivas.

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

En este ejemplo se usa la `#If...Then...#Else` construcción para determinar si se deben compilar ciertas instrucciones.

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>Vea también

- [#Const (directiva)](const-directive.md)
- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
- [Compilación condicional](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>

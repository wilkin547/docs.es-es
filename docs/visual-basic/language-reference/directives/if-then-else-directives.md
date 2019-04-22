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
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823394"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else (Directivas)
Compila condicionalmente bloques seleccionados de código de Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 Necesario para `#If` y `#ElseIf` instrucciones, opcionales en otro lugar. Cualquier expresión, que consta únicamente de uno o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.  
  
 `statements`  
 Necesario para `#If` bloque de instrucción en otro lugar. Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.  
  
 `#End If`  
 Finaliza el `#If` bloque de instrucciones.  
  
## <a name="remarks"></a>Comentarios  
 En la superficie, el comportamiento de la `#If...Then...#Else` Else es el mismo que el de la `If...Then...Else` instrucciones. Sin embargo, el `#If...Then...#Else` directivas evaluación qué está compilado por el compilador, mientras que el `If...Then...Else` condiciones evalúan instrucciones en tiempo de ejecución.  
  
 Compilación condicional se utiliza normalmente para compilar el mismo programa para diferentes plataformas. También se utiliza para evitar que código de depuración aparezca en un archivo ejecutable. Código durante el proceso de compilación condicional se omite completamente en el archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o rendimiento.  
  
 Independientemente del resultado de la evaluación, todas las expresiones se evalúan mediante `Option Compare Binary`. El `Option Compare` instrucción no afecta a las expresiones de `#If` y `#ElseIf` instrucciones.  
  
> [!NOTE]
>  No hay forma de una línea de la `#If`, `#Else`, `#ElseIf`, y `#End If` directivas existe. Ningún otro código puede aparecer en la misma línea que ninguna de las directivas. 

Las instrucciones dentro de un bloque de compilación condicional deben ser completa lógico. Por ejemplo, no se puede compilar condicionalmente solo los atributos de una función, pero condicionalmente puede declarar la función junto con sus atributos:

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
 Este ejemplo se usa el `#If...Then...#Else` construcción para determinar si se debe compilar ciertas instrucciones.  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>

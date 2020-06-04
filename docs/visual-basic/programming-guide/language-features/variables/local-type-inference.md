---
title: Inferencia de tipo de variable local
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: 3979396d32aa5d3b853aa087d43f70d5987e510b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410404"
---
# <a name="local-type-inference-visual-basic"></a>Inferencia de tipo de variable local (Visual Basic)

El compilador Visual Basic usa la *inferencia de tipos* para determinar los tipos de datos de las variables locales declaradas sin una `As` cláusula. El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización. Esto le permite declarar variables sin indicar explícitamente un tipo, tal como se muestra en el ejemplo siguiente. Como resultado de las declaraciones, `num1` y `num2` están fuertemente tipadas como enteros.

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> Si no desea que `num2` en el ejemplo anterior se escriba como `Integer` , puede especificar otro tipo mediante una declaración como `Dim num3 As Object = 3` o `Dim num4 As Double = 3` .

> [!NOTE]
> La inferencia de tipos solo se puede usar para variables locales no estáticas; no se puede usar para determinar el tipo de campos de clase, propiedades o funciones.

La inferencia de tipo local se aplica en el nivel de procedimiento. No se puede usar para declarar variables en el nivel de módulo (dentro de una clase, una estructura, un módulo o una interfaz, pero no dentro de un procedimiento o un bloque). Si `num2` en el ejemplo anterior se tratara de un campo de una clase en lugar de una variable local en un procedimiento, la declaración produciría un error con `Option Strict` en y clasificaría `num2` como un `Object` con `Option Strict` OFF. Del mismo modo, la inferencia de tipo local no se aplica a las variables de nivel de procedimiento declaradas como `Static` .

## <a name="type-inference-vs-late-binding"></a>Inferencia de tipos frente a enlace en tiempo de ejecución

El código que usa la inferencia de tipos es similar al código que se basa en el enlace en tiempo de ejecución. Sin embargo, la inferencia de tipos fuertemente tipa la variable en lugar de pasarla como `Object` . El compilador usa un inicializador de variable para determinar el tipo de la variable en tiempo de compilación para generar código enlazado en tiempo de compilación. En el ejemplo anterior, `num2` , como `num1` , se escribe como `Integer` .

El comportamiento de las variables enlazadas en tiempo de compilación difiere del de las variables enlazadas en tiempo de ejecución, para las que solo se conoce el tipo en tiempo de ejecución. Conocer el tipo pronto permite al compilador identificar problemas antes de la ejecución, asignar la memoria con precisión y realizar otras optimizaciones. El enlace temprano también habilita el Visual Basic entorno de desarrollo integrado (IDE) para proporcionar ayuda de IntelliSense acerca de los miembros de un objeto. El enlace en tiempo de compilación también es preferible para el rendimiento. Esto se debe a que todos los datos almacenados en una variable enlazada en tiempo de ejecución deben ajustarse como de tipo `Object` y obtener acceso a los miembros del tipo en tiempo de ejecución hace que el programa sea más lento.

## <a name="examples"></a>Ejemplos

La inferencia de tipos se produce cuando se declara una variable local sin una `As` cláusula y se inicializa. El compilador usa el tipo del valor inicial asignado como el tipo de la variable. Por ejemplo, cada una de las siguientes líneas de código declara una variable de tipo `String` .

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

En el código siguiente se muestran dos formas equivalentes de crear una matriz de enteros.

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

Es conveniente usar la inferencia de tipos para determinar el tipo de una variable de control de bucle. En el código siguiente, el compilador deduce que `number` es una `Integer` porque `someNumbers2` el ejemplo anterior es una matriz de enteros.

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

La inferencia de tipo local se puede usar en `Using` instrucciones para establecer el tipo del nombre del recurso, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

El tipo de una variable también se puede inferir a partir de los valores devueltos de las funciones, como se muestra en el ejemplo siguiente. `pList1`Y `pList2` son matrices de procesos porque `Process.GetProcesses` devuelve una matriz de procesos.

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a>Option Infer

`Option Infer`permite especificar si se permite la inferencia de tipo de variable local en un archivo determinado. Para habilitar o para bloquear la opción, escriba una de las siguientes instrucciones al principio del archivo.

`Option Infer On`

`Option Infer Off`

Si no especifica un valor para `Option Infer` en el código, el valor predeterminado del compilador es `Option Infer On` .

Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.

Para obtener más información, vea [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) y [compilar Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

## <a name="see-also"></a>Consulte también

- [Tipos anónimos](../objects-and-classes/anonymous-types.md)
- [Enlace anticipado y en tiempo de ejecución](../early-late-binding/index.md)
- [Instrucción For Each...Next](../../../language-reference/statements/for-each-next-statement.md)
- [Instrucción For...Next](../../../language-reference/statements/for-next-statement.md)
- [Option Infer (instrucción)](../../../language-reference/statements/option-infer-statement.md)
- [-optioninfer](../../../reference/command-line-compiler/optioninfer.md)
- [Introducción a LINQ en Visual Basic](../linq/introduction-to-linq.md)

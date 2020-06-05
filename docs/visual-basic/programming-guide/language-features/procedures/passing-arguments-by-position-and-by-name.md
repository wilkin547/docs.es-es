---
title: Pasar argumentos por posición o por nombre
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 686b64977f086c8128e56298a0ed8c5aa0c51efa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364037"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Pasar argumentos por posición o por nombre (Visual Basic)

Cuando se llama a `Sub` un `Function` procedimiento o, se pueden pasar argumentos *por posición* , en el orden en que aparecen en la definición del procedimiento, o bien se pueden pasar *por nombre*, sin tener en cuenta la posición.

Cuando se pasa un argumento por nombre, se especifica el nombre declarado del argumento seguido de dos puntos y un signo igual ( `:=` ), seguido del valor del argumento. Puede proporcionar argumentos con nombre en cualquier orden.

Por ejemplo, el siguiente `Sub` procedimiento toma tres argumentos:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Al llamar a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una combinación de ambos.

## <a name="passing-arguments-by-position"></a>Pasar argumentos por posición

Puede llamar al `Display` método con sus argumentos pasados por posición y delimitados por comas, tal y como se muestra en el ejemplo siguiente:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Si omite un argumento opcional en una lista de argumentos posicionales, debe mantener su lugar con una coma. En el ejemplo siguiente se llama al `Display` método sin el `age` argumento:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Pasar argumentos por nombre

Como alternativa, puede llamar a `Display` con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Pasar argumentos por nombre de esta manera es especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional. Si proporciona argumentos por nombre, no tiene que usar comas consecutivas para indicar que faltan argumentos posicionales. Pasar argumentos por nombre también facilita la realización de un seguimiento de los argumentos que se superan y de los que se omiten.

## <a name="mixing-arguments-by-position-and-by-name"></a>Mezclar argumentos por posición y por nombre

Puede proporcionar argumentos por posición y por nombre en una única llamada de procedimiento, como se muestra en el ejemplo siguiente:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

En el ejemplo anterior, no es necesario disponer de una coma adicional para contener el lugar del argumento omitido `age` , ya que `birth` se pasa por nombre.

En las versiones de Visual Basic antes 15,5, cuando se proporcionan argumentos mediante una combinación de posición y nombre, los argumentos posicionales deben aparecer en primer lugar. Una vez que se proporciona un argumento por nombre, todos los argumentos restantes deben pasarse por nombre.  Por ejemplo, la siguiente llamada al `Display` método muestra el error del compilador [BC30241: se esperaba un argumento con nombre](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

A partir de Visual Basic 15,5, los argumentos posicionales pueden seguir los argumentos con nombre si los argumentos posicionales de final están en la posición correcta. Si se compila en Visual Basic 15,5, la llamada anterior al `Display` método se compila correctamente y ya no genera un error del compilador [BC30241](../../../misc/bc30241.md).

Esta capacidad de mezclar y coincidir con argumentos con nombre y posicionales en cualquier orden es especialmente útil cuando se desea usar un argumento con nombre para que el código sea más legible. Por ejemplo, el siguiente `Person` constructor de clase requiere dos argumentos de tipo `Person` , los cuales pueden ser `Nothing` .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

El uso de argumentos con nombre y posicionales mixtos ayuda a hacer que el código sea claro cuando el valor de los `father` `mother` argumentos y es `Nothing` :

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Para seguir los argumentos posicionales con argumentos con nombre, debe agregar el siguiente elemento al archivo de proyecto de Visual Basic ( \* . vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../../../language-reference/configure-language-version.md).

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restricciones en el suministro de argumentos por nombre

No se pueden pasar argumentos por nombre para evitar escribir argumentos necesarios. Solo se pueden omitir los argumentos opcionales.

No se puede pasar una matriz de parámetros por nombre. Esto se debe a que cuando se llama al procedimiento, se proporciona un número indefinido de argumentos separados por comas para la matriz de parámetros y el compilador no puede asociar más de un argumento con un nombre único.

## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Opcional](../../../language-reference/modifiers/optional.md)
- [ParamArray](../../../language-reference/modifiers/paramarray.md)

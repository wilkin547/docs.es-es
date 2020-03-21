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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401440"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Pasar argumentos por posición o por nombre (Visual Basic)

Cuando se `Sub` llama `Function` a un procedimiento o, se pueden pasar argumentos *por posición* (en el orden en que aparecen en la definición del procedimiento) o se pueden pasar *por nombre,* sin tener en cuenta la posición.

Cuando se pasa un argumento por nombre, se especifica el nombre declarado`:=`del argumento seguido de dos puntos y un signo igual ( ), seguido del valor del argumento. Puede proporcionar argumentos con nombre en cualquier orden.

Por ejemplo, `Sub` el siguiente procedimiento toma tres argumentos:

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

Cuando se llama a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una mezcla de ambos.

## <a name="passing-arguments-by-position"></a>Pasar argumentos por posición

Puede llamar `Display` al método con sus argumentos pasados por position y delimitados por comas, como se muestra en el ejemplo siguiente:

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

Si omite un argumento opcional en una lista de argumentos posicionales, debe mantener su lugar con una coma. En el ejemplo `Display` siguiente `age` se llama al método sin el argumento:

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a>Pasar argumentos por nombre

Como alternativa, puede `Display` llamar con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

Pasar argumentos por nombre de esta manera es especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional. Si proporciona argumentos por nombre, no tiene que utilizar comas consecutivas para denotar argumentos posicionales que faltan. Pasar argumentos por nombre también facilita el seguimiento de los argumentos que está pasando y cuáles está omitiendo.

## <a name="mixing-arguments-by-position-and-by-name"></a>Mezclar argumentos por posición y por nombre

Puede proporcionar argumentos tanto por posición como por nombre en una sola llamada a procedimiento, como se muestra en el ejemplo siguiente:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

En el ejemplo anterior, no es necesario ninguna coma `age` adicional `birth` para mantener el lugar del argumento omitido, ya que se pasa por nombre.

En las versiones de Visual Basic anteriores a 15.5, cuando se proporcionan argumentos por una mezcla de posición y nombre, los argumentos posicionales deben ser lo primero. Una vez que proporcione un argumento por nombre, los argumentos restantes deben pasarse por nombre.  Por ejemplo, la siguiente `Display` llamada al método muestra el error del compilador [BC30241: Se espera](../../../misc/bc30241.md)un argumento con nombre .

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

A partir de Visual Basic 15.5, los argumentos posicionales pueden seguir argumentos con nombre si los argumentos posicionales finales están en la posición correcta. Si se compila en Visual Basic 15.5, la llamada anterior al `Display` método se compila correctamente y ya no genera el error del compilador [BC30241](../../../misc/bc30241.md).

Esta capacidad de mezclar y hacer coincidir argumentos con nombre y posicionales en cualquier orden es especialmente útil cuando se desea usar un argumento con nombre para que el código sea más legible. Por ejemplo, `Person` el siguiente constructor de clase `Person`requiere dos argumentos de tipo , ambos de los cuales pueden ser `Nothing`.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

El uso de argumentos mixtos con nombre y posicionales ayuda `father` `mother` a que `Nothing`la intención del código sea clara cuando el valor de los argumentos y es:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

Para seguir argumentos posicionales con argumentos con nombre, debe agregar\*el siguiente elemento al archivo de proyecto de Visual Basic (.vbproj):

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

Para obtener más información, consulte [configuración de la versión](../../../language-reference/configure-language-version.md)del lenguaje Visual Basic .

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restricciones a la entrega de argumentos por nombre

No puede pasar argumentos por nombre para evitar escribir los argumentos necesarios. Solo puede omitir los argumentos opcionales.

No se puede pasar una matriz de parámetros por nombre. Esto se debe a que cuando se llama al procedimiento, se proporciona un número indefinido de argumentos separados por comas para la matriz de parámetros y el compilador no puede asociar más de un argumento con un solo nombre.

## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Opcional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)

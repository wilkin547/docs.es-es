---
title: "Pasar argumentos por posición o por nombre (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Pasar argumentos por posición o por nombre (Visual Basic)
Cuando se llama a un `Sub` o `Function` procedimiento, puede pasar argumentos *por posición* : en el orden en que aparecen en la definición del procedimiento, o se les pueden pasar *por su nombre*, sin tener en cuenta para colocar.  
  
 Cuando se pasa un argumento por nombre, especifique el declarado del argumento nombre seguido de dos puntos y un signo igual (`:=`), seguido por el valor del argumento. Puede proporcionar argumentos con nombre en cualquier orden.  
  
 Por ejemplo, la siguiente `Sub` procedimiento toma tres argumentos:  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 Cuando se llama a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una combinación de ambos.  
  
## <a name="passing-arguments-by-position"></a>Pasar argumentos por posición  
 Puede llamar a la `Display` método con los argumentos pasados por posición y delimitados por comas, como se muestra en el ejemplo siguiente:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 Si se omite un argumento opcional de una lista de argumentos posicionales, debe mantener su posición mediante una coma. El ejemplo siguiente se llama el `Display` método sin el `age` argumento:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>Pasar argumentos por nombre  
 Como alternativa, puede llamar a `Display` con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 Pasar argumentos por nombre de esta forma resulta especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional. Si proporciona argumentos por nombre, no es necesario utilizar comas consecutivas para denotar falta argumentos posicionales. Pasar argumentos por nombre también resulta más fácil realizar un seguimiento de los argumentos que se pasan y cuáles se omiten.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Pasar argumentos por posición o por nombre  

Puede proporcionar argumentos por posición o por su nombre en una llamada de procedimiento único, como se muestra en el ejemplo siguiente:  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 En el ejemplo anterior, no hay ninguna coma adicional es necesaria para mantener la posición de la omitido `age` argumento, ya que `birth` se pasó por nombre.  
  
En las versiones de Visual Basic anteriores 15,5, al proporcionar argumentos, una mezcla de posición y el nombre, los argumentos posicionales deben preceder al resto. Una vez que se proporciona un argumento por nombre, los argumentos restantes deben todos pasarse por nombre.  Por ejemplo, la siguiente llamada a la `Display` método muestra el error del compilador [BC30241: se esperaba un argumento con el nombre](../../../misc/bc30241.md).

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

A partir de Visual Basic 15,5, los argumentos posicionales pueden seguir argumentos con nombre si los argumentos posicionales finales están en la posición correcta. Si se compilan en 15,5 de Visual Basic, la llamada anterior a la `Display` método se compila correctamente y ya no se genera el error del compilador [BC30241](../../../misc/bc30241.md).  

Esta capacidad de mezclar y combinar los argumentos posicionales y con nombre en cualquier orden es especialmente útil cuando desea usar un argumento con nombre para que el código sea más legible. Por ejemplo, la siguiente `Person` constructor de clase requiere dos argumentos de tipo `Person`, ambos de los cuales pueden ser `Nothing`. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

Uso mixtos argumentos posicionales y con nombre ayuda a aclarar la intención del código borrar cuando el valor de la `father` y `mother` argumentos es `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

Para seguir argumentos posicionales con argumentos con nombre, debe agregar el siguiente elemento a su proyecto de Visual Basic (\*.vbproj) archivo:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a>Restricciones sobre cómo proporcionar argumentos por nombre  

No se puede pasar argumentos por nombre para evitar especificar argumentos requeridos. Puede omitir solo los argumentos opcionales.  
  
No se puede pasar una matriz de parámetros por nombre. Esto es porque cuando se llama al procedimiento, se proporciona un número indefinido de argumentos separados por comas para la matriz de parámetros, y el compilador no puede asociar más de un argumento con un nombre único.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Parámetros opcionales](./optional-parameters.md)  
 [Matrices de parámetros](./parameter-arrays.md)  
 [Opcional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)

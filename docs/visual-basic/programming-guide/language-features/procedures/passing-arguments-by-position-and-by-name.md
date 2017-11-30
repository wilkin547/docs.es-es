---
title: "Pasar argumentos por posición o por nombre (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Pasar argumentos por posición o por nombre (Visual Basic)
Cuando se llama a un `Sub` o `Function` procedimiento, puede pasar argumentos *por posición* : en el orden en que aparecen en la definición del procedimiento, o se les pueden pasar *por su nombre*, sin tener en cuenta para colocar.  
  
 Cuando se pasa un argumento por nombre, especifique el declarado del argumento nombre seguido de dos puntos y un signo igual (`:=`), seguido por el valor del argumento. Puede proporcionar argumentos con nombre en cualquier orden.  
  
 Por ejemplo, la siguiente `Sub` procedimiento toma tres argumentos:  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 Cuando se llama a este procedimiento, puede proporcionar los argumentos por posición, por nombre o mediante una combinación de ambos.  
  
## <a name="passing-arguments-by-position"></a>Pasar argumentos por posición  
 Puede llamar al procedimiento `studentInfo` con los argumentos pasados por posición y delimitados por comas, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Si se omite un argumento opcional de una lista de argumentos posicionales, debe mantener su posición mediante una coma. El ejemplo siguiente se llama `studentInfo` sin el `age` argumento:  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>Pasar argumentos por nombre  
 Como alternativa, puede llamar a `studentInfo` con los argumentos pasados por nombre, también delimitados por comas, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Pasar argumentos por posición o por nombre  
 Puede proporcionar argumentos por posición o por su nombre en una llamada de procedimiento único, como se muestra en el ejemplo siguiente:  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 En el ejemplo anterior, no hay ninguna coma adicional es necesaria para mantener la posición de la omitido `age` argumento, ya que `birth` se pasó por nombre.  
  
 Al proporcionar argumentos, una mezcla de posición y el nombre, los argumentos posicionales deben preceder al resto. Una vez que se proporciona un argumento por nombre, los argumentos restantes deben ser por su nombre.  
  
## <a name="supplying-optional-arguments-by-name"></a>Proporcionar argumentos opcionales por nombre  
 Pasar argumentos por nombre es especialmente útil cuando se llama a un procedimiento que tiene más de un argumento opcional. Si proporciona argumentos por nombre, no es necesario utilizar comas consecutivas para denotar falta argumentos posicionales. Pasar argumentos por nombre también resulta más fácil realizar un seguimiento de los argumentos que se pasan y cuáles se omiten.  
  
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

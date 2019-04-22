---
title: Diferencias entre parámetros y argumentos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a69b956c7cffcc2a26916d6fc92f23dd4e2322d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838981"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Diferencias entre parámetros y argumentos (Visual Basic)
En la mayoría de los casos, un procedimiento debe tener cierta información sobre las circunstancias en que se ha llamado. Un procedimiento que realiza tareas repetitivas o compartidas utiliza información diferente para cada llamada. Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama al método.  
  
 Para comunicar esta información para el procedimiento, el procedimiento define un *parámetro*, y el código que realiza la llamada pasa una *argumento* a ese parámetro. Puede pensar en el parámetro como una plaza de aparcamiento y el argumento como un automóvil. Modo que diferentes automóviles pueden aparcan en un espacio de estacionamiento en momentos diferentes, el código de llamada puede pasar un argumento distinto al mismo parámetro cada vez que llama al procedimiento.  
  
## <a name="parameters"></a>Parámetros  
 Un *parámetro* representa un valor que el procedimiento espera que se pase al llamarla. La declaración del procedimiento define sus parámetros.  
  
 Al definir un `Function` o `Sub` procedimiento, especifica un *lista de parámetros* entre paréntesis inmediatamente después del nombre de procedimiento. Para cada parámetro, especifica un nombre, un tipo de datos y un mecanismo de paso ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)). También puede indicar que un parámetro es opcional. Esto significa que el código de llamada no tiene que pasar un valor para él.  
  
 El nombre de cada parámetro actúa como un *variable local* en el procedimiento. Utilice el nombre del parámetro de la misma manera que usa cualquier otra variable.  
  
## <a name="arguments"></a>Argumentos  
 Un *argumento* representa el valor que se pasa a un parámetro de procedimiento cuando se llama al procedimiento. El código de llamada proporciona los argumentos cuando llama al procedimiento.  
  
 Cuando se llama a un `Function` o `Sub` procedimiento, incluye un *lista de argumentos* entre paréntesis inmediatamente después del nombre de procedimiento. Cada argumento se corresponde con el parámetro en la misma posición en la lista.  
  
 A diferencia de la definición de parámetro, argumentos no tienen nombres. Cada argumento es una expresión, que puede contener cero o más variables, constantes y literales. El tipo de datos de la expresión evaluada normalmente debe coincidir con el tipo de datos definido para el parámetro correspondiente, y en cualquier caso, debe poder convertirse al tipo de parámetro.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)

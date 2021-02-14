---
description: 'Más información sobre: diferencias entre parámetros y argumentos (Visual Basic)'
title: Diferencias entre parámetros y argumentos
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
ms.openlocfilehash: 01efc7dc3f451d6aae20cfd091355f531af4431c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100438767"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a>Diferencias entre parámetros y argumentos (Visual Basic)

En la mayoría de los casos, un procedimiento debe tener información sobre las circunstancias en las que se ha llamado. Un procedimiento que realiza tareas repetidas o compartidas utiliza información diferente para cada llamada. Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama.  
  
 Para comunicar esta información al procedimiento, el procedimiento define un *parámetro* y el código de llamada pasa un *argumento* a ese parámetro. Puede pensar en el parámetro como un espacio de estacionamiento y el argumento como un automóvil. Del mismo modo que los diferentes automóviles pueden detenerse en un espacio de estacionamiento en momentos diferentes, el código de llamada puede pasar un argumento diferente al mismo parámetro cada vez que llama al procedimiento.  
  
## <a name="parameters"></a>Parámetros  

 Un *parámetro* representa un valor que el procedimiento espera que pase al llamarlo. La declaración del procedimiento define sus parámetros.  
  
 Al definir un `Function` procedimiento o `Sub` , se especifica una *lista de parámetros* entre paréntesis inmediatamente después del nombre del procedimiento. Para cada parámetro, se especifica un nombre, un tipo de datos y un mecanismo de paso ([ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md)). También puede indicar que un parámetro es opcional. Esto significa que el código de llamada no tiene que pasar un valor para él.  
  
 El nombre de cada parámetro actúa como una *variable local* en el procedimiento. El nombre del parámetro se utiliza de la misma manera que cualquier otra variable.  
  
## <a name="arguments"></a>Argumentos  

 Un *argumento* representa el valor que se pasa a un parámetro de procedimiento cuando se llama al procedimiento. El código de llamada proporciona los argumentos cuando llama al procedimiento.  
  
 Cuando se llama a `Function` un `Sub` procedimiento o, se incluye una *lista de argumentos* entre paréntesis inmediatamente después del nombre del procedimiento. Cada argumento corresponde al parámetro en la misma posición en la lista.  
  
 A diferencia de la definición de parámetros, los argumentos no tienen nombres. Cada argumento es una expresión, que puede contener cero o más variables, constantes y literales. El tipo de datos de la expresión evaluada debe coincidir normalmente con el tipo de datos definido para el parámetro correspondiente y, en cualquier caso, debe ser convertible en el tipo de parámetro.  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Procedimientos recursivos](./recursive-procedures.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)

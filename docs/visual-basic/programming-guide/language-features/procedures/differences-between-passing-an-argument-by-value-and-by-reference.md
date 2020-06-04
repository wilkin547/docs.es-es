---
title: Diferencias entre pasar un argumento por valor y por referencia
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: bd316ae2239ad85e4ef6dadbb8a634d5fe7ecf02
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403335"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Diferencias entre pasar un argumento por valor y por referencia (Visual Basic)
Al pasar uno o varios argumentos a un procedimiento, cada argumento corresponde a un elemento de programación subyacente en el código de llamada. Puede pasar el valor de este elemento subyacente o una referencia a él. Esto se conoce como *mecanismo de paso*.  
  
## <a name="passing-by-value"></a>Pasar por valor  
 Para pasar un argumento *por valor* , especifique la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) para el parámetro correspondiente en la definición de procedimiento. Cuando se utiliza este mecanismo de paso, Visual Basic copia el valor del elemento de programación subyacente en una variable local en el procedimiento. El código de procedimiento no tiene ningún acceso al elemento subyacente en el código de llamada.  
  
## <a name="passing-by-reference"></a>Pasar por referencia  
 Para pasar un argumento *por referencia* , especifique la palabra clave [ByRef](../../../language-reference/modifiers/byref.md) para el parámetro correspondiente en la definición de procedimiento. Cuando se utiliza este mecanismo de paso, Visual Basic proporciona al procedimiento una referencia directa al elemento de programación subyacente en el código de llamada.  
  
## <a name="passing-mechanism-and-element-type"></a>Pasando el mecanismo y el tipo de elemento  
 La elección del mecanismo de paso no es igual que la clasificación del tipo de elemento subyacente. Pasar por valor o por referencia hace referencia a lo que proporciona Visual Basic al código de procedimiento. Un tipo de valor o un tipo de referencia hace referencia a cómo se almacena un elemento de programación en la memoria.  
  
 Sin embargo, el mecanismo de paso y el tipo de elemento están interrelacionados. El valor de un tipo de referencia es un puntero a los datos en otra parte de la memoria. Esto significa que cuando se pasa un tipo de referencia por valor, el código de procedimiento tiene un puntero a los datos del elemento subyacente, aunque no puede tener acceso al propio elemento subyacente. Por ejemplo, si el elemento es una variable de matriz, el código de procedimiento no tiene acceso a la variable en sí, pero puede tener acceso a los miembros de la matriz.  
  
## <a name="ability-to-modify"></a>Capacidad de modificar  
 Cuando se pasa un elemento no modificable como argumento, el procedimiento no puede modificarlo nunca en el código de llamada, tanto si se pasa como si es `ByVal` `ByRef` .  
  
 En el caso de un elemento modificable, en la tabla siguiente se resume la interacción entre el tipo de elemento y el mecanismo de paso.  
  
|Tipo de elemento|Ha`ByVal`|Ha`ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo de valor (solo contiene un valor)|El procedimiento no puede cambiar la variable ni ninguno de sus miembros.|El procedimiento puede cambiar la variable y sus miembros.|  
|Tipo de referencia (contiene un puntero a una instancia de clase o estructura)|El procedimiento no puede cambiar la variable, pero puede cambiar los miembros de la instancia a la que señala.|El procedimiento puede cambiar la variable y los miembros de la instancia a la que señala.|  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Procedimiento para cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedimiento para proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedimiento para forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md)

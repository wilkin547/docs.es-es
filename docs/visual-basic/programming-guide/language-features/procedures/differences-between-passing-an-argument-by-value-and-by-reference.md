---
title: Diferencias entre pasar un argumento por valor y por referencia (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8f733b4fd50612292c0c4ac7195304d99ae2dbea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Diferencias entre pasar un argumento por valor y por referencia (Visual Basic)
Al pasar uno o más argumentos a un procedimiento, cada argumento corresponde a un elemento de programación subyacente en el código de llamada. Puede pasar el valor de este elemento subyacente, o bien una referencia a él. Esto se conoce como el *mecanismo para pasar argumentos*.  
  
## <a name="passing-by-value"></a>Pasar por valor  
 Se pasa un argumento *por valor* especificando la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) palabra clave para el parámetro correspondiente en la definición del procedimiento. Cuando se utiliza este mecanismo para pasar argumentos, Visual Basic copia el valor del elemento de programación subyacente en una variable local en el procedimiento. El código del procedimiento no tiene acceso al elemento subyacente en el código de llamada.  
  
## <a name="passing-by-reference"></a>Pasar por referencia  
 Se pasa un argumento *por referencia* especificando la [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave para el parámetro correspondiente en la definición del procedimiento. Cuando se utiliza este mecanismo para pasar argumentos, Visual Basic proporciona el procedimiento una referencia directa al elemento de programación subyacente en el código de llamada.  
  
## <a name="passing-mechanism-and-element-type"></a>Mecanismo para pasar argumentos y el tipo de elemento  
 La elección del mecanismo para pasar argumentos no es igual que la clasificación del tipo de elemento subyacente. Pasar por valor o por referencia hace referencia a lo que proporciona Visual Basic en el código de procedimiento. Un tipo de valor o tipo de referencia hace referencia a cómo se almacena un elemento de programación en la memoria.  
  
 Sin embargo, el mecanismo para pasar argumentos y el tipo de elemento están relacionados entre sí. El valor de un tipo de referencia es un puntero a los datos en otra ubicación en la memoria. Esto significa que, cuando se pasa un tipo de referencia por valor, el código de procedimiento tiene un puntero a datos del elemento subyacente, aunque no tiene acceso al propio elemento subyacente. Por ejemplo, si el elemento es una variable de matriz, el código del procedimiento no tiene acceso a la variable en Sí, pero pueden tener acceso a los miembros de la matriz.  
  
## <a name="ability-to-modify"></a>Capacidad de modificar  
 Cuando se pasa un elemento no modificable como argumento, el procedimiento no podrá modificarlo nunca en el código que realiza la llamada, si se pasa `ByVal` o `ByRef`.  
  
 Para un elemento modificable, la tabla siguiente resume la interacción entre el tipo de elemento y el mecanismo de paso.  
  
|Tipo de elemento|Pasado `ByVal`|Pasado `ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo de valor (contiene un solo valor)|El procedimiento no puede cambiar la variable o cualquiera de sus miembros.|El procedimiento puede cambiar la variable y sus miembros.|  
|Tipo de referencia (contiene un puntero a una instancia de clase o estructura)|El procedimiento no puede cambiar la variable, pero puede cambiar los miembros de la instancia a la que señala.|El procedimiento puede cambiar la variable y los miembros de la instancia a la que señala.|  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Forzar un argumento para que pase como un valor](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

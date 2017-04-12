---
title: Diferencias entre pasar un argumento por valor y por referencia (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 93c515dd8524cde85555a27879baee00185f78e3
ms.lasthandoff: 03/13/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Diferencias entre pasar un argumento por valor y por referencia (Visual Basic)
Cuando se pasan uno o varios argumentos a un procedimiento, cada argumento corresponde a un elemento de programación subyacente en el código de llamada. Puede pasar el valor de este elemento subyacente, o bien una referencia a él. Esto se conoce como el *mecanismo para pasar argumentos*.  
  
## <a name="passing-by-value"></a>Pasar por valor  
 Se pasa un argumento *por valor* especificando la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) palabra clave para el parámetro correspondiente en la definición del procedimiento. Cuando se utiliza este mecanismo, que pasa [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copia el valor del elemento de programación subyacente en una variable local en el procedimiento. El código de procedimiento no tiene acceso al elemento subyacente en el código de llamada.  
  
## <a name="passing-by-reference"></a>Pasar por referencia  
 Se pasa un argumento *por referencia* especificando la [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave para el parámetro correspondiente en la definición del procedimiento. Cuando se utiliza este mecanismo, que pasa [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona el procedimiento una referencia directa al elemento de programación subyacente en el código de llamada.  
  
## <a name="passing-mechanism-and-element-type"></a>Mecanismo para pasar argumentos y el tipo de elemento  
 La elección del mecanismo para pasar argumentos no es igual que la clasificación del tipo de elemento subyacente. Pasar por valor o por referencia hace referencia a lo que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona al código de procedimiento. Un tipo de valor o tipo de referencia se refiere a cómo se almacena un elemento de programación en la memoria.  
  
 Sin embargo, el mecanismo para pasar argumentos y el tipo de elemento están interrelacionadas. El valor de un tipo de referencia es un puntero a los datos en otra parte de la memoria. Esto significa que, cuando se pasa un tipo de referencia por valor, el código del procedimiento tiene un puntero a los datos del elemento subyacente, aunque no tiene acceso el propio elemento subyacente. Por ejemplo, si el elemento es una variable de matriz, el código de procedimiento no tiene acceso a la propia variable, pero pueden tener acceso a los miembros de la matriz.  
  
## <a name="ability-to-modify"></a>Capacidad de modificar  
 Cuando se pasa un elemento no modificable como argumento, el procedimiento no puede modificarlo nunca en el código de llamada, si se pasa `ByVal` o `ByRef`.  
  
 Para un elemento modificable, la tabla siguiente resume la interacción entre el tipo de elemento y el mecanismo de paso.  
  
|Tipo de elemento|Pasado`ByVal`|Pasado`ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo de valor (sólo contiene un valor)|El procedimiento no puede cambiar la variable o cualquiera de sus miembros.|El procedimiento puede cambiar la variable y sus miembros.|  
|Tipo de referencia (contiene un puntero a una instancia de clase o estructura)|El procedimiento no puede cambiar la variable, pero puede cambiar los miembros de la instancia a la que señala.|El procedimiento puede cambiar la variable y los miembros de la instancia a la que señala.|  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Cómo: cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: proteger un argumento de procedimiento realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)   
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

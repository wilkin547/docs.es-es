---
title: No se puede hacer referencia a un miembro de instancia de una clase desde un método compartido o un inicializador de método compartido sin una instancia explícita de la clase
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: fc54bbf8053c07cc3b48a762b6f1c60344de9921
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822579"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>No se puede hacer referencia a un miembro de instancia de una clase desde un método compartido o un inicializador de método compartido sin una instancia explícita de la clase
Ha intentado hacer referencia a un miembro no compartido de una clase desde un procedimiento compartido. El ejemplo siguiente muestra esta situación.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 En el ejemplo anterior, la instrucción de asignación `x = 10` genera este mensaje de error. Esto es porque un procedimiento compartido está intentando obtener acceso a una variable de instancia.  
  
 La variable `x` es un miembro de instancia porque no está declarado como [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Cada instancia de clase `sample` contiene su propia variable individual `x`. Cuando una instancia establece o cambia el valor de `x`, no afecta al valor de `x` en cualquier otra instancia.  
  
 Sin embargo, el procedimiento `setX` es `Shared` entre todas las instancias de clase `sample`. Esto significa no está asociado a ninguna instancia de la clase, sino que funciona independientemente de las instancias individuales. Porque no tiene ninguna conexión con una instancia concreta, `setX` no puede tener acceso a una variable de instancia. Debe funcionar solo en `Shared` variables. Cuando `setX` establece o cambia el valor de una variable compartida, que el nuevo valor está disponible para todas las instancias de la clase.  
  
 **Identificador de error:** BC30369  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Decida si desea que el miembro que se comparte entre todas las instancias de la clase o mantienen individuales para cada instancia.  
  
2.  Si desea una copia única del miembro que se comparte entre todas las instancias, agregue el `Shared` palabra clave para la declaración del miembro. Conservar la `Shared` palabra clave en la declaración de procedimiento.  
  
3.  Si desea que cada instancia tiene su propia copia individual del miembro, no especifique `Shared` para la declaración del miembro. Quitar el `Shared` palabra clave de la declaración de procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)

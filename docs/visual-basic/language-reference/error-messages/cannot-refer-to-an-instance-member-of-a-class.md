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
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701172"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a>No se puede hacer referencia a un miembro de instancia de una clase desde un método compartido o un inicializador de método compartido sin una instancia explícita de la clase
Ha intentado hacer referencia a un miembro no compartido de una clase desde un procedimiento compartido. En el ejemplo siguiente se muestra este tipo de situación.  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 En el ejemplo anterior, la instrucción de asignación `x = 10` genera este mensaje de error. Esto se debe a que un procedimiento compartido está intentando obtener acceso a una variable de instancia.  
  
 La variable `x` es un miembro de instancia porque no se ha declarado como [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Cada instancia de la clase `sample` contiene su propia variable individual `x`. Cuando una instancia establece o cambia el valor de `x`, no afecta al valor de `x` en ninguna otra instancia.  
  
 Sin embargo, el procedimiento `setX` es `Shared` entre todas las instancias de la clase `sample`. Esto significa que no está asociado a ninguna instancia de la clase, sino que funciona independientemente de las instancias individuales. Dado que no tiene conexión con una instancia determinada, `setX` no puede tener acceso a una variable de instancia. Debe funcionar solo en variables `Shared`. Cuando `setX` establece o cambia el valor de una variable compartida, el nuevo valor está disponible para todas las instancias de la clase.  
  
 **IDENTIFICADOR de error:** BC30369  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Decida si desea que el miembro se comparta entre todas las instancias de la clase o que se mantenga individual para cada instancia.  
  
2. Si desea que se comparta una sola copia del miembro entre todas las instancias, agregue la palabra clave `Shared` a la declaración de miembro. Conserve la palabra clave `Shared` en la declaración de procedimiento.  
  
3. Si desea que cada instancia tenga su propia copia individual del miembro, no especifique `Shared` para la declaración de miembro. Quite la palabra clave `Shared` de la declaración de procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)

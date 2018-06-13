---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599917"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Especifica que una variable o propiedad se puede leer pero no se han escrito.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Solo se puede usar `ReadOnly` en un nivel de módulo. Esto significa que el contexto de la declaración de un `ReadOnly` elemento debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
-   **Modificadores combinados.** No se puede especificar `ReadOnly` junto con `Static` en la misma declaración.  
  
-   **Asignar un valor.** Código consumir un `ReadOnly` propiedad no puede establecer su valor. Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.  
  
     Puede asignar un valor a un `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en la que está definido.  
  
## <a name="when-to-use-a-readonly-variable"></a>Cuándo se debe utilizar una Variable de solo lectura  
 Hay situaciones en las que no se puede usar un [instrucción Const](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante. Por ejemplo, el `Const` instrucción no puede aceptar el tipo de datos que desea asignar o es posible que no pueda calcular el valor en tiempo de compilación con una expresión constante. Podría no incluso conoce el valor en tiempo de compilación. En estos casos, puede usar un `ReadOnly` variable para que contenga un valor constante.  
  
> [!IMPORTANT]
>  Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros incluso si la propia variable sea `ReadOnly`. Esto se ilustra en el siguiente ejemplo:  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Cuando se inicializa, la matriz señalada por `characterArray()` alberga "x", "y" y "z". Dado que la variable `characterArray` es `ReadOnly`, no se puede cambiar su valor una vez que se ha inicializado; que es, no se puede asignar una nueva matriz a él. Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz. Después de una llamada al procedimiento `changeArrayElement`, la matriz señalada por `characterArray()` alberga "x", "M" y "z".  
  
 Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), lo que impide que el procedimiento cambie el argumento de llamada, pero le permite cambiar sus miembros.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `ReadOnly` propiedad para la fecha en que se contrató a un empleado. La clase almacena el valor de propiedad internamente como una `Private` variable y solo el código dentro de la clase puede cambiar ese valor. Sin embargo, la propiedad es `Public`, y cualquier código que puede tener acceso a la clase puede leer la propiedad.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 El modificador `ReadOnly` se puede utilizar en los contextos siguientes:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)

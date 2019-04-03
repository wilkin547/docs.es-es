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
ms.openlocfilehash: 6e361cbe89f4c51f28199b008de817c2d48ef326
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825396"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Especifica que una variable o propiedad se puede leer pero no se escribe.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Solo se puede usar `ReadOnly` en un nivel de módulo. Esto significa que el contexto de declaración de un `ReadOnly` elemento debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.  
  
-   **Modificadores combinados.** No puede especificar `ReadOnly` junto con `Static` en la misma declaración.  
  
-   **Asignar un valor.** Código consume un `ReadOnly` propiedad no puede establecer su valor. Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.  
  
     Puede asignar un valor a un `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en el que está definida.  
  
## <a name="when-to-use-a-readonly-variable"></a>Cuándo usar una Variable ReadOnly  
 Hay situaciones en las que no se puede usar un [instrucción Const](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante. Por ejemplo, el `Const` instrucción no puede aceptar el tipo de datos que desea asignar, o es posible que no pueda calcular el valor en tiempo de compilación con una expresión constante. Es posible que ni siquiera sepa el valor en tiempo de compilación. En estos casos, puede usar un `ReadOnly` variable que contenga un valor constante.  
  
> [!IMPORTANT]
>  Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros incluso si es la propia variable `ReadOnly`. Esto se ilustra en el siguiente ejemplo:  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Cuando se inicializa, la matriz señalada por `characterArray()` alberga "x", "y" y "z". Dado que la variable `characterArray` es `ReadOnly`, no se puede cambiar su valor una vez que se ha inicializado; que es, no se puede asignar una nueva matriz a él. Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz. Después de una llamada al procedimiento `changeArrayElement`, la matriz señalada por `characterArray()` alberga "x", "M" y "z".  
  
 Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), lo que impide que el procedimiento cambia el argumento de llamada, pero le permite cambiar sus miembros.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `ReadOnly` propiedad para la fecha en que se contrató a un empleado. La clase almacena internamente de la propiedad como valor un `Private` variable y solo el código dentro de la clase puede cambiar ese valor. Sin embargo, la propiedad es `Public`, y cualquier código que puede tener acceso a la clase puede leer la propiedad.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 El modificador `ReadOnly` se puede utilizar en los contextos siguientes:  
  
 [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)

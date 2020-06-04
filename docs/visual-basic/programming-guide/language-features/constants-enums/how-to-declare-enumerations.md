---
title: Procedimiento para declarar enumeraciones
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c8f228c205c93adf7f2f555dc840a7daac61950b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414458"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Cómo: Declarar enumeraciones (Visual Basic)
Cree una enumeración con la `Enum` instrucción en la sección de declaraciones de una clase o módulo. No se puede declarar una enumeración dentro de un método. Para especificar el nivel de acceso adecuado, use `Private` , `Protected` , `Friend` o `Public` .  
  
 Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante. El nombre debe ser un calificador de .NET Visual Basic válido. El tipo subyacente debe ser uno de los tipos enteros ( `Byte` , `Short` o) `Long` `Integer` . `Integer` es el valor predeterminado. Las enumeraciones siempre tienen un tipo seguro y no son intercambiables con tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si se asigna un valor de punto flotante a una enumeración con `Option Strict On` , se producirá un error del compilador. Si `Option Strict` es `Off` , el valor se convierte automáticamente al `Enum` tipo.  
  
 Para obtener información sobre los nombres y el uso de la `Imports` instrucción para que la calificación de nombres sea innecesaria, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Para declarar una enumeración  
  
1. Escriba una declaración que incluya un nivel de acceso de código, la `Enum` palabra clave y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara un diferente `Enum` .  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Defina las constantes en la enumeración. De forma predeterminada, la primera constante de una enumeración se inicializa en `0` y las constantes subsiguientes se inicializan en un valor de uno más que la constante anterior. Por ejemplo, la enumeración siguiente, `Days` , contiene una constante denominada `Sunday` con el valor `0` , una constante denominada `Monday` con el valor `1` , una constante denominada `Tuesday` con el valor de `2` , etc.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Puede asignar valores explícitamente a constantes en una enumeración mediante una instrucción de asignación. Puede asignar cualquier valor entero, incluidos los números negativos. Por ejemplo, puede que desee usar constantes con valores inferiores a cero para representar condiciones de error. En la enumeración siguiente, a la constante `Invalid` se le asigna explícitamente el valor `–1` y se asigna el valor a la constante `Sunday` `0` . Dado que es la primera constante de la enumeración, `Saturday` también se inicializa en el valor `0` . El valor de `Monday` es `1` (uno más que el valor de `Sunday` ); el valor de `Tuesday` es `2` , etc.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Para declarar una enumeración como un tipo explícito  
  
- Especifique el tipo de la enumeración mediante la `As` cláusula, tal como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Procedimiento para hacer referencia al miembro de una enumeración](how-to-refer-to-an-enumeration-member.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Procedimiento para determinar la cadena asociada a un valor de enumeración](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](when-to-use-an-enumeration.md)
- [Información general sobre las constantes](constants-overview.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md)

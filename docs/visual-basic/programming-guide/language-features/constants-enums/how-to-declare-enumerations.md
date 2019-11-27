---
title: 'Cómo: declarar enumeraciones'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354046"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Cómo: Declarar enumeraciones (Visual Basic)
Cree una enumeración con la instrucción `Enum` en la sección de declaraciones de una clase o módulo. No se puede declarar una enumeración dentro de un método. Para especificar el nivel de acceso adecuado, utilice `Private`, `Protected`, `Friend`o `Public`.  
  
 Un tipo de `Enum` tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante. El nombre debe ser un calificador de .NET Visual Basic válido. El tipo subyacente debe ser uno de los tipos enteros (`Byte`, `Short`, `Long` o `Integer`. `Integer` es el valor predeterminado. Las enumeraciones siempre tienen un tipo seguro y no son intercambiables con tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si a una enumeración se le asigna un valor de punto flotante con `Option Strict On`, se producirá un error del compilador. Si `Option Strict` es `Off`, el valor se convierte automáticamente al tipo `Enum`.  
  
 Para obtener información sobre los nombres y el uso de la instrucción `Imports` para que la calificación de nombres sea innecesaria, vea [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Para declarar una enumeración  
  
1. Escriba una declaración que incluya un nivel de acceso de código, la palabra clave `Enum` y un nombre válido, como en los ejemplos siguientes, cada uno de los cuales declara un `Enum`diferente.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Defina las constantes en la enumeración. De forma predeterminada, la primera constante de una enumeración se inicializa en `0`y las constantes subsiguientes se inicializan en un valor de uno más que la constante anterior. Por ejemplo, la enumeración siguiente, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor de `2`, etc.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Puede asignar valores explícitamente a constantes en una enumeración mediante una instrucción de asignación. Puede asignar cualquier valor entero, incluidos los números negativos. Por ejemplo, puede que desee usar constantes con valores inferiores a cero para representar condiciones de error. En la enumeración siguiente, a la constante `Invalid` se le asigna explícitamente el valor `–1`y se asigna a la `Sunday` constante el valor `0`. Dado que es la primera constante de la enumeración, `Saturday` también se inicializa en el valor `0`. El valor de `Monday` es `1` (uno más que el valor de `Sunday`); el valor de `Tuesday` es `2`, etc.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Para declarar una enumeración como un tipo explícito  
  
- Especifique el tipo de la enumeración mediante la cláusula `As`, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Hacer referencia al miembro de una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Cómo: recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Determinar la cadena asociada a un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)

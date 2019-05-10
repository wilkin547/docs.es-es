---
title: Procedimiento Declarar enumeraciones (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: c74b75adf0f56dd198375cb1ff24656d39ec074c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610576"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Procedimiento Declarar enumeraciones (Visual Basic)
Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o módulo. No se puede declarar una enumeración dentro de un método. Para especificar el nivel adecuado de acceso, use `Private`, `Protected`, `Friend`, o `Public`.  
  
 Un `Enum` tipo tiene un nombre, un tipo subyacente y un conjunto de campos, cada uno de los cuales representa una constante. El nombre debe ser un calificador válido de Visual Basic. NET. El tipo subyacente debe ser uno de los tipos de enteros:`Byte`, `Short`, `Long` o `Integer`. `Integer` es el valor predeterminado. Las enumeraciones son siempre establecimiento inflexible de tipos y no son intercambiables con tipos de números enteros.  
  
 Las enumeraciones no pueden tener valores de punto flotante. Si se asigna un valor de punto flotante con una enumeración `Option Strict On`, produce un error de compilador. Si `Option Strict` es `Off`, el valor se convierte automáticamente en el `Enum` tipo.  
  
 Para obtener información sobre nombres y cómo usar el `Imports` instrucción para asegurarse de calificación de nombres innecesarios, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Para declarar una enumeración  
  
1. Escriba una declaración que incluye un nivel de acceso del código, el `Enum` palabra clave y un nombre válido, como se muestra en los ejemplos siguientes, cada uno de los cuales declara otro `Enum`.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Defina las constantes en la enumeración. De forma predeterminada, se inicializa la primera constante de enumeración en `0`, y posteriores se inicializan con un valor de la constante anterior más uno. Por ejemplo, la siguiente enumeración, `Days`, contiene una constante denominada `Sunday` con el valor `0`, una constante denominada `Monday` con el valor `1`, una constante denominada `Tuesday` con el valor de `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Puede asignar explícitamente valores a las constantes de enumeración mediante el uso de una instrucción de asignación. Puede asignar cualquier valor entero, incluidos los números negativos. Por ejemplo, es posible que desee constantes con valores inferiores a cero para representar las condiciones de error. En la siguiente enumeración, la constante `Invalid` se asigna explícitamente el valor `–1`y la constante `Sunday` se asigna el valor `0`. Porque es la primera constante de la enumeración, `Saturday` también se inicializa con el valor `0`. El valor de `Monday` es `1` (uno más que el valor de `Sunday`); el valor de `Tuesday` es `2`, y así sucesivamente.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Para declarar una enumeración como un tipo explícito  
  
- Especificar el tipo de la enumeración mediante el `As` cláusula, tal como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Cómo: Hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Cómo: Determinar la cadena asociada con un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Cuándo se debe utilizar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)

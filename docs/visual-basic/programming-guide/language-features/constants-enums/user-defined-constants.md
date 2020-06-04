---
title: Constantes definidas por el usuario
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 14f3de39eb8d8e6820e2b40792a8e8e57217e410
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414381"
---
# <a name="user-defined-constants-visual-basic"></a>Constantes definidas por el usuario (Visual Basic)
Una constante es un nombre significativo que ocupa el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación. Puede usar constantes definidas por los controles o componentes con los que trabaja, o puede crear las suyas propias. Las constantes que se crean se describen como *definidas por el usuario*.  
  
 Declare una constante con la `Const` instrucción, con las mismas instrucciones que para crear un nombre de variable. Si `Option Strict` es `On` , debe declarar explícitamente el tipo de constante.  
  
## <a name="const-statement-usage"></a>Uso de la instrucción const  
 Una `Const` instrucción puede representar una cantidad matemática o de fecha y hora:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 También puede definir `String` constantes:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 La expresión del lado derecho del signo igual ( `=` ) suele ser un número o una cadena literal, pero también puede ser una expresión que da como resultado un número o una cadena (aunque esa expresión no puede contener llamadas a funciones). Incluso puede definir constantes en términos de constantes definidas previamente:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Ámbito de las constantes definidas por el usuario  
 `Const`El ámbito de una instrucción es el mismo que el de una variable declarada en la misma ubicación. Puede especificar el ámbito de cualquiera de las maneras siguientes:  
  
- Para crear una constante que solo existe dentro de un procedimiento, declárela en ese procedimiento.  
  
- Para crear una constante disponible para todos los procedimientos dentro de una clase, pero no para cualquier código fuera de ese módulo, declárelo en la sección declaraciones de la clase.  
  
- Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para los clientes externos del ensamblado, declare el uso de la `Friend` palabra clave en la sección de declaraciones de la clase.  
  
- Para crear una constante disponible en toda la aplicación, declárela mediante la `Public` palabra clave en la sección declaraciones de la clase.  
  
 Para obtener más información, vea [Cómo: declarar una constante](how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Evitar referencias circulares  
 Dado que las constantes se pueden definir en términos de otras constantes, es posible crear accidentalmente un *ciclo*o una referencia circular entre dos o más constantes. Un ciclo se produce cuando hay dos o más constantes públicas, cada una de las cuales se define en términos del otro, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 Si se produce un ciclo, Visual Basic genera un error del compilador.  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Const](../../../language-reference/statements/const-statement.md)
- [Tipos de datos constantes y literales](constant-and-literal-data-types.md)
- [Constantes y enumeraciones](index.md)
- [Constantes y enumeraciones](../../../language-reference/constants-and-enumerations.md)
- [Información general sobre las enumeraciones](enumerations-overview.md)
- [Información general sobre las constantes](constants-overview.md)
- [Cómo: Declarar una enumeración](how-to-declare-enumerations.md)
- [Enumeraciones y calificación de nombres](enumerations-and-name-qualification.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)

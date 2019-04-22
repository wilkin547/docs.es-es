---
title: Constantes definidas por el usuario (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: f0196457235ad77df545a367573f62b43209269d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813917"
---
# <a name="user-defined-constants-visual-basic"></a>Constantes definidas por el usuario (Visual Basic)
Una constante es un nombre descriptivo que ocupa el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación. Puede usar las constantes que se definen mediante los controles o componentes que funciona con, o puede crear sus propios. Se describen las constantes que crea usted mismo como *definido por el usuario*.  
  
 Declarar una constante con el `Const` instrucción, utilizando las mismas directrices que lo haría para crear un nombre de variable. Si `Option Strict` es `On`, debe declarar explícitamente el tipo de constante.  
  
## <a name="const-statement-usage"></a>Utilización de la instrucción const  
 Un `Const` instrucción puede representar un matemáticas o cantidad de fecha y hora:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 También puede definir `String` constantes:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 La expresión en el lado derecho del signo igual ( `=` ) suele ser un número o una cadena literal, pero también puede ser una expresión que da como resultado un número o una cadena (aunque esa expresión no puede contener las llamadas a funciones). Puede incluso definir constantes en términos de constantes definidas previamente:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Ámbito de las constantes definidas por el usuario  
 Un `Const` ámbito de la instrucción es el mismo que el de una variable declarada en la misma ubicación. Puede especificar el ámbito en cualquiera de las maneras siguientes:  
  
-   Para crear una constante que sólo existe dentro de un procedimiento, declarar dentro de ese procedimiento.  
  
-   Para crear una constante disponible para todos los procedimientos dentro de una clase, pero no para el código fuera de ese módulo, declárelo en la sección de declaraciones de la clase.  
  
-   Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para los clientes fuera del ensamblado, declare mediante el `Friend` palabra clave en la sección de declaraciones de la clase.  
  
-   Para crear una constante disponible en toda la aplicación, declare mediante el `Public` palabra clave en las declaraciones de sección de la clase.  
  
 Para obtener más información, vea [Cómo: Declare una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Evitar referencias circulares  
 Dado que las constantes se pueden definir en términos de otras constantes, es posible crear accidentalmente un *ciclo*, o una referencia circular, entre dos o más constantes. Cuando haya dos o más constantes públicas, cada uno de los cuales se define en términos de la otra, como en el ejemplo siguiente, se produce un ciclo:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 Si se produce un ciclo, Visual Basic genera un error del compilador.  
  
## <a name="see-also"></a>Vea también

- [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Constantes y enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

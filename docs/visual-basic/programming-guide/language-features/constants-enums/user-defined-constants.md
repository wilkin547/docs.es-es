---
title: Constantes definidas por el usuario (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce839c3e843a52b31e40c13cb765f8eaf9959ea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-constants-visual-basic"></a>Constantes definidas por el usuario (Visual Basic)
Una constante es un nombre descriptivo que ocupa el lugar de un número o una cadena que no cambia. Las constantes almacenan valores que, como su nombre indica, permanecen constantes durante la ejecución de una aplicación. Puede usar constantes definidas por los controles o componentes con los que trabaja, o puede crear los suyos propios. Se describen las constantes que crea usted mismo como *definido por el usuario*.  
  
 Declarar una constante con el `Const` instrucción, utilizando las mismas directrices que lo haría para crear un nombre de variable. Si `Option Strict` es `On`, debe declarar explícitamente el tipo de constante.  
  
## <a name="const-statement-usage"></a>Utilización de la instrucción const  
 Un `Const` instrucción puede representar un matemáticas o cantidad de fecha y hora:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 También puede definir `String` constantes:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 La expresión del lado derecho del signo igual ( `=` ) suele ser un número o una cadena literal, pero también puede ser una expresión que da como resultado un número o una cadena (aunque esa expresión no puede contener llamadas a funciones). Incluso puede definir constantes en términos de constantes definidas anteriormente:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Ámbito de las constantes definidas por el usuario  
 Un `Const` ámbito de la instrucción es el mismo que el de una variable declarada en la misma ubicación. Puede especificar el ámbito en cualquiera de las maneras siguientes:  
  
-   Para crear una constante que sólo existe dentro de un procedimiento, declárela dentro de ese procedimiento.  
  
-   Para crear una constante disponible para todos los procedimientos dentro de una clase, pero no para el código fuera de ese módulo, declárelo en la sección de declaraciones de la clase.  
  
-   Para crear una constante que esté disponible para todos los miembros de un ensamblado, pero no para clientes fuera del ensamblado, declárela mediante la `Friend` palabra clave en la sección de declaraciones de la clase.  
  
-   Para crear una constante disponible en toda la aplicación, declárela con la `Public` palabra clave en las declaraciones de sección de la clase.  
  
 Para obtener más información, consulte [Cómo: declarar una constante](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Evitar referencias circulares  
 Dado que constantes pueden definirse en términos de otras constantes, es posible crear inadvertidamente un *ciclo*, o una referencia circular, entre dos o más constantes. Un ciclo se produce cuando hay dos o más constantes públicas, cada uno de los cuales se define en términos de la otra, como en el ejemplo siguiente:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 Si se produce un ciclo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] genera un error del compilador.  
  
## <a name="see-also"></a>Vea también  
 [Const (instrucción)](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Tipos de datos constantes y literales](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Constantes y enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Información general sobre las enumeraciones](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Información general sobre las constantes](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)

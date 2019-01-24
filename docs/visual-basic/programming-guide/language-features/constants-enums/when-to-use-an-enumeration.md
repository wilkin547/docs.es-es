---
title: Cuándo se debe usar una enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 826f8fffedb8c983423fbef0fbf1f4014d93be91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535026"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Cuándo se debe usar una enumeración (Visual Basic)
Las enumeraciones ofrecen una manera fácil de trabajar con conjuntos de constantes relacionadas. Una enumeración, o `Enum`, es un nombre simbólico para un conjunto de valores. Las enumeraciones se tratan como tipos de datos, y puede usarlos para crear conjuntos de constantes para su uso con variables y propiedades.  
  
## <a name="when-to-use-an-enumeration"></a>Cuándo se debe utilizar una enumeración  
 Cada vez que un procedimiento acepta un conjunto limitado de variables, considere el uso de una enumeración. Asegúrese de enumeraciones para el código más claro y legible, especialmente cuando se usan nombres descriptivos.  
  
 Las ventajas del uso de las enumeraciones son:  
  
-   Reduce los errores causados por números transpuestos o.  
  
-   Es fácil cambiar los valores en el futuro.  
  
-   Hace el código más fácil de leer, lo que significa que es menos probable que los errores se cuelen en él.  
  
-   Garantiza la compatibilidad con versiones posteriores. Con enumeraciones, el código es menos probable que un error si en el futuro que alguien cambia los valores correspondientes a los nombres de miembro.  
  
## <a name="naming-enumerations"></a>Enumeraciones de nomenclatura  
 Utilice una convención de nomenclatura para los miembros de enumeración. Cuando Visual Basic encuentra un nombre de miembro de enumeración, se puede producir una excepción si otras bibliotecas de tipos que se hace referencia contienen el mismo nombre. Use un prefijo único que identifica los valores de la aplicación o componente.  
  
 Cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración, o bien usar la `Imports` instrucción. Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Enumeraciones predefinidas  
 Visual Basic proporciona una serie de enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult`, para facilitar el código. Para obtener una lista de estos, consulte [constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Vea también
- [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Cómo: Hacer referencia a un miembro de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Cómo: Recorrer en iteración una enumeración en Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Cómo: Determinar la cadena asociada con un valor de enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Enum (instrucción)](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md)

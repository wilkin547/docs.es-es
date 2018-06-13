---
title: 'Cómo: Declarar una estructura (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650032"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Cómo: Declarar una estructura (Visual Basic)
Comenzar una declaración de estructura con la [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md), una letra y terminar con la `End` `Structure` instrucción. Entre estas dos instrucciones debe declararse al menos una *elemento*. Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no compartido y.  
  
 No se puede inicializar cualquiera de los elementos de la estructura en la declaración de estructura. Cuando se declara una variable de un tipo de estructura, asignar valores a los elementos mediante el acceso a ellos a través de la variable.  
  
 Para obtener una explicación de las diferencias entre las estructuras y clases, vea [estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Con fines de demostración, considere la posibilidad de una situación en la que desea realizar un seguimiento del nombre de un empleado, una extensión de teléfono y sueldo. Una estructura le permite hacer esto en una única variable.  
  
### <a name="to-declare-a-structure"></a>Para declarar una estructura  
  
1.  Cree el comienzo y finalización de instrucciones para la estructura.  
  
     Puede especificar el nivel de acceso de una estructura mediante la [público](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, o puede dejar de forma predeterminada `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Agregar elementos al cuerpo de la estructura.  
  
     Una estructura debe tener al menos un elemento. Debe declarar cada elemento y especificar un nivel de acceso para él. Si usas el [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) sin palabras clave, valores predeterminados de la accesibilidad a `Public`.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     El `salary` campo en el ejemplo anterior es `Private`, lo que significa que no es accesible fuera de la estructura, incluso desde la clase contenedora. Sin embargo, el `giveRaise` procedimiento es `Public`, por lo que se puede llamar desde fuera de la estructura. De forma similar, puede aumentar la `salaryReviewTime` evento desde fuera de la estructura.  
  
     Además de las variables, `Sub` procedimientos y los eventos, también puede definir constantes, `Function` procedimientos y propiedades en una estructura. Puede designar a lo sumo una propiedad como el *propiedad predeterminada*, siempre que admita al menos un argumento. Puede controlar un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento. Para obtener más información, consulte [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Variables de estructura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Tipo de datos definido por el usuario](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
